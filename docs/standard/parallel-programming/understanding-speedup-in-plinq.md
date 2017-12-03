---
title: "PLINQ'te Hızlandırmayı Anlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a><span data-ttu-id="b7bb8-102">PLINQ'te Hızlandırmayı Anlama</span><span class="sxs-lookup"><span data-stu-id="b7bb8-102">Understanding Speedup in PLINQ</span></span>
<span data-ttu-id="b7bb8-103">PLINQ birincil amacı, çok çekirdekli bilgisayarlarda paralel sorgu temsilcileri yürüterek nesneleri sorgularında LINQ yürütme hızlandırmak olmaktır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-103">The primary purpose of PLINQ is to speed up the execution of LINQ to Objects queries by executing the query delegates in parallel on multi-core computers.</span></span> <span data-ttu-id="b7bb8-104">Kaynak koleksiyondaki her öğe işleme bağımsız duruma sahip olmayan paylaşılan arasında tek tek temsilcileri söz konusu olduğunda PLINQ en iyi şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-104">PLINQ performs best when the processing of each element in a source collection is independent, with no shared state involved among the individual delegates.</span></span> <span data-ttu-id="b7bb8-105">Bu tür işlemler LINQ nesneleri ve PLINQ için ortak olan ve genellikle denir "*delightfully paralel*" bunlar kendilerini kolayca üzerinde birden çok iş parçacıklarını zamanlama için ödünç vermek için.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-105">Such operations are common in LINQ to Objects and PLINQ, and are often called "*delightfully parallel*" because they lend themselves easily to scheduling on multiple threads.</span></span> <span data-ttu-id="b7bb8-106">Ancak, tüm sorguları tamamen delightfully paralel işlemleri oluşur; Çoğu durumda, bir sorgu, ya da paralel birkaç ölçeklendirin olamaz veya paralel yürütme yavaş bazı işleçleri içerir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-106">However, not all queries consist entirely of delightfully parallel operations; in most cases, a query involves some operators that either cannot be parallelized, or that slow down parallel execution.</span></span> <span data-ttu-id="b7bb8-107">Ve tamamen delightfully paralel bile sorgular ile PLINQ gerekir hala veri kaynağı bölüm ve iş parçacığı üzerinde çalışması zamanlamak ve sorgu tamamlandığında genellikle birleştirme sonuçları.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-107">And even with queries that are entirely delightfully parallel, PLINQ must still partition the data source and schedule the work on the threads, and usually merge the results when the query completes.</span></span> <span data-ttu-id="b7bb8-108">Bu işlemler paralelleştirme hesaplama maliyetine ekleyin; paralelleştirme ekleme, bu maliyetlerini adlı *yükünü*.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-108">All these operations add to the computational cost of parallelization; these costs of adding parallelization are called *overhead*.</span></span> <span data-ttu-id="b7bb8-109">PLINQ sorgusunda en iyi performansı elde etmek için delightfully paralel bölümleri en üst düzeye çıkarmak ve ek yükü gerektiren bölümleri en aza indirmek için belirtilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-109">To achieve optimum performance in a PLINQ query, the goal is to maximize the parts that are delightfully parallel and minimize the parts that require overhead.</span></span> <span data-ttu-id="b7bb8-110">Bu makale, hala doğru sonuçlar verir sırasında olabildiğince etkili PLINQ sorguları yazmanıza yardımcı olacak bilgiler sağlar.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-110">This article provides information that will help you write PLINQ queries that are as efficient as possible while still yielding correct results.</span></span>  
  
## <a name="factors-that-impact-plinq-query-performance"></a><span data-ttu-id="b7bb8-111">PLINQ sorgu performansını etkileyen faktörler</span><span class="sxs-lookup"><span data-stu-id="b7bb8-111">Factors that Impact PLINQ Query Performance</span></span>  
 <span data-ttu-id="b7bb8-112">Aşağıdaki bölümlerde listelenmiştir bazı en önemli faktörlerin etkisi paralel sorgu performans.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-112">The following sections lists some of the most important factors that impact parallel query performance.</span></span> <span data-ttu-id="b7bb8-113">Tüm durumlarda sorgu performansı tahmin etmek yeterli değil, kendilerini tarafından genel deyimleri bunlar.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-113">These are general statements that by themselves are not sufficient to predict query performance in all cases.</span></span> <span data-ttu-id="b7bb8-114">Her zaman olduğu gibi bir dizi temsilcisi yapılandırmaları ve yükleri ile olan bilgisayarlarda belirli sorgu gerçek performansını ölçmek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-114">As always, it is important to measure actual performance of specific queries on computers with a range of representative configurations and loads.</span></span>  
  
1.  <span data-ttu-id="b7bb8-115">Genel İş hesaplama maliyeti.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-115">Computational cost of the overall work.</span></span>  
  
     <span data-ttu-id="b7bb8-116">Speedup elde etmek için bir PLINQ sorgusu yeterli delightfully paralel iş yükünü dengelemek için olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-116">To achieve speedup, a PLINQ query must have enough delightfully parallel work to offset the overhead.</span></span> <span data-ttu-id="b7bb8-117">İş kaynak koleksiyondaki öğe sayısı ile çarpılır her temsilci hesaplama maliyeti olarak ifade edilebilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-117">The work can be expressed as the computational cost of each delegate multiplied by the number of elements in the source collection.</span></span> <span data-ttu-id="b7bb8-118">Bir işlem, daha pkı'ya paralel birkaç ölçeklendirin varsayarak, pahalıdır, büyük fırsat speedup için.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-118">Assuming that an operation can be parallelized, the more computationally expensive it is, the greater the opportunity for speedup.</span></span> <span data-ttu-id="b7bb8-119">Örneğin, bir işlev yürütmek için bir milisaniyelik alırsa, paralel sorgu ancak farklı bir bilgisayarda dört çekirdek ile 1000'den öğeleri bu işlemi gerçekleştirmek için bir saniye sürer sıralı bir sorgu yalnızca 250 milisaniye alabilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-119">For example, if a function takes one millisecond to execute, a sequential query over 1000 elements will take one second to perform that operation, whereas a parallel query on a computer with four cores might take only 250 milliseconds.</span></span> <span data-ttu-id="b7bb8-120">750 milisaniye speedup verir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-120">This yields a speedup of 750 milliseconds.</span></span> <span data-ttu-id="b7bb8-121">Her öğe için yürütmek bir saniye işlevi gerekli olursa speedup 750 saniye olacaktır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-121">If the function required one second to execute for each element, then the speedup would be 750 seconds.</span></span> <span data-ttu-id="b7bb8-122">Temsilci çok pahalı ise, PLINQ öğeleriyle yalnızca birkaç kaynak koleksiyondaki önemli speedup sunabilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-122">If the delegate is very expensive, then PLINQ might offer significant speedup with only a few items in the source collection.</span></span> <span data-ttu-id="b7bb8-123">Buna karşılık, Önemsiz temsilciler küçük kaynak koleksiyonlarla genellikle PLINQ için iyi bir aday değildir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-123">Conversely, small source collections with trivial delegates are generally not good candidates for PLINQ.</span></span>  
  
     <span data-ttu-id="b7bb8-124">Aşağıdaki örnekte, queryA büyük olasılıkla bir iyi Select işlevi çok fazla iş içerdiğini varsayarak PLINQ adaydır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-124">In the following example, queryA is probably a good candidate for PLINQ, assuming that its Select function involves a lot of work.</span></span> <span data-ttu-id="b7bb8-125">queryB iyi bir aday paralelleştirme yükü çoğu veya tümü speedup uzaklığı ve Select deyiminde yeterli iş olmadığından büyük olasılıkla değil.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-125">queryB is probably not a good candidate because there is not enough work in the Select statement, and the overhead of parallelization will offset most or all of the speedup.</span></span>  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
    ```  
  
2.  <span data-ttu-id="b7bb8-126">(Paralellik derecesini) sisteminde mantıksal çekirdeklerinin sayısı.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-126">The number of logical cores on the system (degree of parallelism).</span></span>  
  
     <span data-ttu-id="b7bb8-127">Bu noktadan önceki bölüme belirgin bir corollary, iş daha fazla eşzamanlı iş parçacıkları arasında bölünebilir çünkü delightfully paralel sorgular makinelerde daha fazla çekirdeğiyle daha hızlı çalışır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-127">This point is an obvious corollary to the previous section, queries that are delightfully parallel run faster on machines with more cores because the work can be divided among more concurrent threads.</span></span> <span data-ttu-id="b7bb8-128">Speedup genel miktarını sorgunun genel iş yüzdesini paralelleştirilebilir olduğuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-128">The overall amount of speedup depends on what percentage of the overall work of the query is parallelizable.</span></span> <span data-ttu-id="b7bb8-129">Ancak, tüm sorguları iki kez olarak çalışacağını varsayın değil hızlı bir bilgisayarda sekiz çekirdeği dört çekirdek bilgisayar olarak.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-129">However, do not assume that all queries will run twice as fast on an eight core computer as a four core computer.</span></span> <span data-ttu-id="b7bb8-130">En iyi performans için sorgular ayarlama, çeşitli sayıda çekirdek olan bilgisayarlarda gerçek sonuçları ölçmek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-130">When tuning queries for optimal performance, it is important to measure actual results on computers with various numbers of cores.</span></span> <span data-ttu-id="b7bb8-131">Bu noktaya #1 işaret edecek şekilde ilişkilidir: büyük veri kümeleri, daha fazla bilgi işlem kaynakları yararlanmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-131">This point is related to point #1: larger datasets are required to take advantage of greater computing resources.</span></span>  
  
3.  <span data-ttu-id="b7bb8-132">Sayısı ve işlemleri tür.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-132">The number and kind of operations.</span></span>  
  
     <span data-ttu-id="b7bb8-133">PLINQ AsOrdered işleci kaynak sıradaki öğelerin sırasını korumak için gerekli olduğu durumlar için sağlar.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-133">PLINQ provides the AsOrdered operator for situations in which it is necessary to maintain the order of elements in the source sequence.</span></span> <span data-ttu-id="b7bb8-134">Sıralama ile ilişkili bir maliyeti yoktur, ancak bu maliyet genellikle düşüktür.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-134">There is a cost associated with ordering, but this cost is usually modest.</span></span> <span data-ttu-id="b7bb8-135">GroupBy ve birleştirme işlemlerinin benzer şekilde zahmetine.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-135">GroupBy and Join operations likewise incur overhead.</span></span> <span data-ttu-id="b7bb8-136">Herhangi bir sırada kaynak koleksiyondaki öğelerin işlemek ve yükleyebileceğinizden hazır olduğunuzda İleri işleci bunları geçirmek için izin verildiğinde PLINQ en iyi şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-136">PLINQ performs best when it is allowed to process elements in the source collection in any order, and pass them to the next operator as soon as they are ready.</span></span> <span data-ttu-id="b7bb8-137">Daha fazla bilgi için bkz: [plınq'te sıra koruma](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-137">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
4.  <span data-ttu-id="b7bb8-138">Sorgu yürütme formu.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-138">The form of query execution.</span></span>  
  
     <span data-ttu-id="b7bb8-139">Bir sorgunun sonuçlarını ToArray veya ToList çağırarak depoluyorsanız tüm paralel iş parçacıklarını sonuçlarından tek veri yapısına birleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-139">If you are storing the results of a query by calling ToArray or ToList, then the results from all parallel threads must be merged into the single data structure.</span></span> <span data-ttu-id="b7bb8-140">Bu kaçınılmaz hesaplama maliyet içerir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-140">This involves an unavoidable computational cost.</span></span> <span data-ttu-id="b7bb8-141">(Her biri için Visual Basic) foreach döngüsü kullanarak sonuçları yinelemek varsa, benzer şekilde, çalışan iş parçacığı sonuçlarından Numaralandırıcı iş parçacığı serileştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-141">Likewise, if you iterate the results by using a foreach (For Each in Visual Basic) loop, the results from the worker threads need to be serialized onto the enumerator thread.</span></span> <span data-ttu-id="b7bb8-142">Ancak yalnızca her bir iş parçacığı sonucundan temel bazı eylemleri gerçekleştirmek istiyorsanız, bu iş üzerinde birden çok iş parçacığı gerçekleştirmek için ForAll yöntemi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-142">But if you just want to perform some action based on the result from each thread, you can use the ForAll method to perform this work on multiple threads.</span></span>  
  
5.  <span data-ttu-id="b7bb8-143">Birleştirme seçeneklerini türü.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-143">The type of merge options.</span></span>  
  
     <span data-ttu-id="b7bb8-144">PLINQ çıktısını arabelleğe ve bunlar üretilen gibi tüm sonuç kümesi, veya başka akış tek tek sonuçları üretilen sonra öbekleri veya tümünü bir defada onu üretmek için yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-144">PLINQ can be configured to either buffer its output, and produce it in chunks or all at once after the entire result set is produced, or else to stream individual results as they are produced.</span></span> <span data-ttu-id="b7bb8-145">Eski azalmasına genel yürütme süresi ve ikinci sonuçları verdiğini öğeler arasında azalmasına gecikme sonucudur.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-145">The former result is decreased overall execution time and the latter results in decreased latency between yielded elements.</span></span>  <span data-ttu-id="b7bb8-146">Birleştirme seçeneklerini her zaman büyük bir etkisi genel sorgu performansı üzerinde değil olsa da, ne kadar kullanıcı kontrol çünkü bunlar algılanan performansı etkileyebilir sonuçları görmek için beklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-146">While the merge options do not always have a major impact on overall query performance, they can impact perceived performance because they control how long a user must wait to see results.</span></span> <span data-ttu-id="b7bb8-147">Daha fazla bilgi için bkz: [plınq'te Birleştirme Seçenekleri](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-147">For more information, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
6.  <span data-ttu-id="b7bb8-148">Bölümleme türü.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-148">The kind of partitioning.</span></span>  
  
     <span data-ttu-id="b7bb8-149">Bazı durumlarda, bir PLINQ sorgusu bir dizine kaynak koleksiyonu üzerinden bir dengesiz iş yükü neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-149">In some cases, a PLINQ query over an indexable source collection may result in an unbalanced work load.</span></span> <span data-ttu-id="b7bb8-150">Bu durumda, özel bir bölümleyici oluşturarak sorgu performansını artırmak olabilir.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-150">When this occurs, you might be able to increase the query performance by creating a custom partitioner.</span></span> <span data-ttu-id="b7bb8-151">Daha fazla bilgi için bkz: [PLINQ ve TPL için özel Bölümleyiciler](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-151">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="when-plinq-chooses-sequential-mode"></a><span data-ttu-id="b7bb8-152">PLINQ sıralı modu zaman seçer</span><span class="sxs-lookup"><span data-stu-id="b7bb8-152">When PLINQ Chooses Sequential Mode</span></span>  
 <span data-ttu-id="b7bb8-153">PLINQ sorgu sırayla çalışır gibi en az olarak hızlı bir sorguyu yürütmek her zaman deneyecek.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-153">PLINQ will always attempt to execute a query at least as fast as the query would run sequentially.</span></span> <span data-ttu-id="b7bb8-154">PLINQ ne pkı'ya aramaz rağmen pahalı kullanıcı temsilcileri veya ne kadar büyük giriş kaynağı olduğundan, "şekiller." için belirli sorgu arayın</span><span class="sxs-lookup"><span data-stu-id="b7bb8-154">Although PLINQ does not look at how computationally expensive the user delegates are, or how big the input source is, it does look for certain query "shapes."</span></span> <span data-ttu-id="b7bb8-155">Özellikle, sorgu işleçleri veya genel olarak daha yavaş paralel modunda yürütülmek bir sorgu neden işleçleri birleşimleri arar.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-155">Specifically, it looks for query operators or combinations of operators that typically cause a query to execute more slowly in parallel mode.</span></span> <span data-ttu-id="b7bb8-156">Tür şekilleri bulduğunda, varsayılan olarak PLINQ sıralı moduna geri döner.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-156">When it finds such shapes, PLINQ by default falls back to sequential mode.</span></span>  
  
 <span data-ttu-id="b7bb8-157">Ancak, belirli bir sorgu performansını ölçmek sonra gerçekte daha hızlı paralel modunda çalıştığını belirlemek.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-157">However, after measuring a specific query's performance, you may determine that it actually runs faster in parallel mode.</span></span> <span data-ttu-id="b7bb8-158">Bu gibi durumlarda kullandığınız <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> aracılığıyla bayrak <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> sorguyu paralel hale PLINQ istemek üzere yöntemi.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-158">In such cases you can use the <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> flag via the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method to instruct PLINQ to parallelize the query.</span></span> <span data-ttu-id="b7bb8-159">Daha fazla bilgi için bkz: [nasıl yapılır: PLINQ'te yürütme modunu belirtme](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-159">For more information, see [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).</span></span>  
  
 <span data-ttu-id="b7bb8-160">Aşağıdaki listede varsayılan olarak PLINQ sıralı modunda yürütülür sorgu şekilleri açıklanmaktadır:</span><span class="sxs-lookup"><span data-stu-id="b7bb8-160">The following list describes the query shapes that PLINQ by default will execute in sequential mode:</span></span>  
  
-   <span data-ttu-id="b7bb8-161">Bir Select içeren sorgular dizine nerede, dizinli SelectMany veya kaldırılan veya özgün dizinlerini düzenlenmeyecek bir sıralama veya filtreleme işleç sonra ElementAt yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-161">Queries that contain a Select, indexed Where, indexed SelectMany, or ElementAt clause after an ordering or filtering operator that has removed or rearranged original indices.</span></span>  
  
-   <span data-ttu-id="b7bb8-162">SkipWhile işleci bir Al ' TakeWhile, Atla içeren ve burada dizinlerini kaynak sıradaki özgün sırayla değil sorgular.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-162">Queries that contain a Take, TakeWhile, Skip, SkipWhile operator and where indices in the source sequence are not in the original order.</span></span>  
  
-   <span data-ttu-id="b7bb8-163">ZIP veya SequenceEquals, veri kaynaklarından biri başlangıçta sıralı bir dizine sahip ve başka bir veri kaynağını dizine sürece içeren sorgular (yani bir dizi veya IList(T)).</span><span class="sxs-lookup"><span data-stu-id="b7bb8-163">Queries that contain Zip or SequenceEquals, unless one of the data sources has an originally ordered index and the other data source is indexable (i.e. an array or IList(T)).</span></span>  
  
-   <span data-ttu-id="b7bb8-164">Concat, dizine veri kaynaklarına uygulanır sürece içeren sorgular.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-164">Queries that contain Concat, unless it is applied to indexable data sources.</span></span>  
  
-   <span data-ttu-id="b7bb8-165">Bir dizine veri kaynağına uygulanan sürece içeren sorgular ters.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-165">Queries that contain Reverse, unless applied to an indexable data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bb8-166">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-166">See Also</span></span>  
 [<span data-ttu-id="b7bb8-167">Paralel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="b7bb8-167">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)