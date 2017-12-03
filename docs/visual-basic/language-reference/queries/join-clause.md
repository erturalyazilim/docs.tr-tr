---
title: "Join Tümcesi (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb25c9dac8994e7f975539c1d036f0f0d9d239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="303d9-102">Join Tümcesi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="303d9-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="303d9-103">Tek bir koleksiyon iki koleksiyonlara birleştirir.</span><span class="sxs-lookup"><span data-stu-id="303d9-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="303d9-104">Birleştirme işlemi anahtarları eşleşmesini temel alan ve kullandığı `Equals` işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="303d9-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="303d9-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="303d9-106">Bölümler</span><span class="sxs-lookup"><span data-stu-id="303d9-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="303d9-107">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="303d9-107">Required.</span></span> <span data-ttu-id="303d9-108">Denetim değişkeni birleştirilen koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="303d9-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="303d9-109">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="303d9-109">Required.</span></span> <span data-ttu-id="303d9-110">Sol tarafında tanımlanan derlemesiyle birleştirmek için koleksiyon `Join` işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="303d9-111">A `Join` yan tümcesi iç içe geçirilemez başka bir programda `Join` yan tümcesi veya bir `Group Join` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="303d9-112">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="303d9-112">Optional.</span></span> <span data-ttu-id="303d9-113">Bir veya daha fazla ek `Join` daha da fazla yan tümceleri sorgu daraltın.</span><span class="sxs-lookup"><span data-stu-id="303d9-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="303d9-114">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="303d9-114">Optional.</span></span> <span data-ttu-id="303d9-115">Bir veya daha fazla ek `Group Join` daha da fazla yan tümceleri sorgu daraltın.</span><span class="sxs-lookup"><span data-stu-id="303d9-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="303d9-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="303d9-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="303d9-117">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="303d9-117">Required.</span></span> <span data-ttu-id="303d9-118">Birleştirilen koleksiyonları tuşları tanımlar.</span><span class="sxs-lookup"><span data-stu-id="303d9-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="303d9-119">Kullanmalısınız `Equals` birleştirilen koleksiyonları anahtarlarından Karşılaştırılacak işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="303d9-120">Kullanarak birleştirme koşulları birleştirebilirsiniz `And` birden çok anahtar tanımlamak için işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="303d9-121">`key1`sol tarafındaki koleksiyonundan olmalıdır `Join` işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="303d9-122">`key2`sağ tarafında koleksiyonundan olmalıdır `Join` işleci.</span><span class="sxs-lookup"><span data-stu-id="303d9-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="303d9-123">Birleşim koşulu kullanılan anahtarları koleksiyonundan birden çok öğe içeren bir ifade olabilir.</span><span class="sxs-lookup"><span data-stu-id="303d9-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="303d9-124">Bununla birlikte, her anahtar ifadesi yalnızca kendi ilgili koleksiyonundan öğeleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="303d9-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="303d9-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="303d9-125">Remarks</span></span>  
 <span data-ttu-id="303d9-126">`Join` Yan tümcesi anahtar değerleri birleştirilen koleksiyonlardan eşleşmesini temel alan iki koleksiyon birleştirir.</span><span class="sxs-lookup"><span data-stu-id="303d9-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="303d9-127">Sonuçta elde edilen koleksiyon sol tarafında tanımlanan koleksiyondan değerler herhangi bir birleşimini içerebilir `Join` işleci ve tanımlanan koleksiyonu `Join` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="303d9-128">Sorguyu yalnızca tarafından koşul için belirtilen sonuç döndürür `Equals` işleci karşılanıyorsa.</span><span class="sxs-lookup"><span data-stu-id="303d9-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="303d9-129">Bu eşdeğer olan bir `INNER JOIN` SQL.</span><span class="sxs-lookup"><span data-stu-id="303d9-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="303d9-130">Birden çok kullanabilirsiniz `Join` tek bir koleksiyon iki veya daha fazla koleksiyonlara katılmak için bir sorgu yan tümcelerinde.</span><span class="sxs-lookup"><span data-stu-id="303d9-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="303d9-131">Koleksiyonları olmadan birleştirmek için örtük bir birleşim gerçekleştirebilirsiniz `Join` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="303d9-132">Bunu yapmak için birden çok dahil `In` yan tümcelerinde, `From` yan tümcesi ve belirtin bir `Where` birleştirme için kullanmak istediğiniz anahtarları tanımlayan yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="303d9-133">Kullanabileceğiniz `Group Join` tek hiyerarşik derlemeye koleksiyonları birleştirme yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="303d9-134">Bu benzer bir `LEFT OUTER JOIN` SQL.</span><span class="sxs-lookup"><span data-stu-id="303d9-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="303d9-135">Örnek</span><span class="sxs-lookup"><span data-stu-id="303d9-135">Example</span></span>  
 <span data-ttu-id="303d9-136">Aşağıdaki kod örneğinde, emirleri ile müşteriler listesini birleştirmek için örtük bir birleştirme gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="303d9-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="303d9-137">Örnek</span><span class="sxs-lookup"><span data-stu-id="303d9-137">Example</span></span>  
 <span data-ttu-id="303d9-138">Aşağıdaki kod örneği iki koleksiyonları kullanarak birleştirir `Join` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="303d9-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="303d9-139">Bu örnek, aşağıdakine benzer bir çıktı üretir:</span><span class="sxs-lookup"><span data-stu-id="303d9-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="303d9-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="303d9-140">Example</span></span>  
 <span data-ttu-id="303d9-141">Aşağıdaki kod örneği iki koleksiyonları kullanarak birleştirir `Join` yan tümcesiyle birlikte iki anahtar sütun.</span><span class="sxs-lookup"><span data-stu-id="303d9-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="303d9-142">Örneğin, aşağıdakine benzer bir çıktı üretir:</span><span class="sxs-lookup"><span data-stu-id="303d9-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="303d9-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="303d9-143">See Also</span></span>  
 [<span data-ttu-id="303d9-144">Visual Basic'de LINQ'e giriş</span><span class="sxs-lookup"><span data-stu-id="303d9-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="303d9-145">Sorguları</span><span class="sxs-lookup"><span data-stu-id="303d9-145">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="303d9-146">Select tümcesi</span><span class="sxs-lookup"><span data-stu-id="303d9-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="303d9-147">From yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="303d9-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="303d9-148">Group Join tümcesi</span><span class="sxs-lookup"><span data-stu-id="303d9-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="303d9-149">Burada yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="303d9-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)