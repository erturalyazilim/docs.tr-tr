---
title: invalidCERCall MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c051e1513f8e8ad1735085cb93f106b4fb9b0d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="invalidcercall-mda"></a><span data-ttu-id="8861a-102">invalidCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="8861a-102">invalidCERCall MDA</span></span>
<span data-ttu-id="8861a-103">`invalidCERCall` Yönetilen hata ayıklama Yardımcısı (MDA) kısıtlı yürütme bölge (CER) grafik içinde hiçbir güvenilirlik sözleşme veya aşırı zayıf bir sözleşme içeren bir yöntem çağrısı olduğunda etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="8861a-103">The `invalidCERCall` managed debugging assistant (MDA) is activated when there is a call within the constrained execution region (CER) graph to a method that has no reliability contract or an excessively weak contract.</span></span> <span data-ttu-id="8861a-104">Zayıf bir sözleşme çağrısı, diğer bir deyişle, geçirilen örneği daha büyük kapsamının en kötü durumu case bozulması olduğunu bildiren bir sözleşmedir <xref:System.AppDomain> işlem durumu bozuksa veya sonucu her zaman belirleyici biçimde computable olmayan içinde bir CER çağrıldığında.</span><span class="sxs-lookup"><span data-stu-id="8861a-104">A weak contract is a contract that declares that the worst case state corruption is of greater scope than the instance passed to the call, that is, the <xref:System.AppDomain> or process state may become corrupted or that its result is not always deterministically computable when called within a CER.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8861a-105">Belirtiler</span><span class="sxs-lookup"><span data-stu-id="8861a-105">Symptoms</span></span>  
 <span data-ttu-id="8861a-106">Kod bir CER yürütülürken beklenmeyen sonuçlar.</span><span class="sxs-lookup"><span data-stu-id="8861a-106">Unexpected results when executing code in a CER.</span></span> <span data-ttu-id="8861a-107">Belirtiler özel değildir.</span><span class="sxs-lookup"><span data-stu-id="8861a-107">The symptoms are not specific.</span></span> <span data-ttu-id="8861a-108">Beklenmeyen bir olabilir <xref:System.OutOfMemoryException>, <xref:System.Threading.ThreadAbortException>, veya diğer özel durumlar güvenilmez yöntemiyle çağrısında çalışma zamanı olmamasından önceden hazırlayın veya ondan korumak <xref:System.Threading.ThreadAbortException> çalışma zamanında özel durum.</span><span class="sxs-lookup"><span data-stu-id="8861a-108">They could be an unexpected <xref:System.OutOfMemoryException>, a <xref:System.Threading.ThreadAbortException>, or other exceptions at the call into the unreliable method because the runtime did not prepare it ahead of time or protect it from <xref:System.Threading.ThreadAbortException> exceptions at run time.</span></span> <span data-ttu-id="8861a-109">Daha büyük bir tehdit yöntemden zamanında kaynaklanan bir özel durumla bırakabilir olduğu <xref:System.AppDomain> veya işlem bir CER amacı aykırı kararsız bir durumda.</span><span class="sxs-lookup"><span data-stu-id="8861a-109">A greater threat is that any exception resulting from the method at run time could leave the <xref:System.AppDomain> or process in an unstable state, which is contrary to the objective of a CER.</span></span> <span data-ttu-id="8861a-110">Bu gibi durumu bozulmaları önlemek için bir CER oluşturulan neden gerekir.</span><span class="sxs-lookup"><span data-stu-id="8861a-110">The reason a CER is created is to avoid state corruptions such as this.</span></span> <span data-ttu-id="8861a-111">Bozuk durum belirtileri uygulamaya özel olduklarından uygulamalar arasında tutarlı bir duruma tanımını farklıdır.</span><span class="sxs-lookup"><span data-stu-id="8861a-111">The symptoms of corrupt state are application specific because the definition of consistent state is different between applications.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8861a-112">Sebep</span><span class="sxs-lookup"><span data-stu-id="8861a-112">Cause</span></span>  
 <span data-ttu-id="8861a-113">Bir CER içindeki kod içermeyen bir işlevi çağırmak <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> veya bir zayıf ile <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> bir CER çalıştıran ile uyumlu değil.</span><span class="sxs-lookup"><span data-stu-id="8861a-113">Code within a CER is calling a function with no <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> or with a weak <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> that is not compatible with running in a CER.</span></span>  
  
 <span data-ttu-id="8861a-114">Güvenilirlik sözleşme sözdizimi açısından zayıf bir sözleşme belirtmediği sözleşmedir bir <xref:System.Runtime.ConstrainedExecution.Consistency> numaralandırma değeri veya belirten bir <xref:System.Runtime.ConstrainedExecution.Consistency> değerini <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>, veya <xref:System.Runtime.ConstrainedExecution.Cer.None>.</span><span class="sxs-lookup"><span data-stu-id="8861a-114">In terms of reliability contract syntax, a weak contract is a contract that does not specify a <xref:System.Runtime.ConstrainedExecution.Consistency> enumeration value or specifies a <xref:System.Runtime.ConstrainedExecution.Consistency> value of <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>, or <xref:System.Runtime.ConstrainedExecution.Cer.None>.</span></span> <span data-ttu-id="8861a-115">Bu koşulların herhangi biri çağrılan kodu tutarlı durumunu korumak üzere çabalarına CER diğer kod engelleyebilecek gösterir.</span><span class="sxs-lookup"><span data-stu-id="8861a-115">Any of these conditions indicates that the code called may impede the efforts of the other code in the CER to maintain consistent state.</span></span>  <span data-ttu-id="8861a-116">CERs uygulamaya önemli iç invariants koruma ve, bellek yetersiz özel durumları gibi geçici hataları yüz çalışmaya devam etmesini sağlayan çok belirleyici bir şekilde hataları işlemek kod sağlar.</span><span class="sxs-lookup"><span data-stu-id="8861a-116">CERs allow code to treat errors in a very deterministic manner, maintaining internal invariants that are important to the application and allowing it to continue running in the face of transient errors such as out-of-memory exceptions.</span></span>  
  
 <span data-ttu-id="8861a-117">Bu MDA etkinleştirme CER çağrılan yöntem arayan değil beklediğiniz neydi veya, ayrıldığında bir şekilde başarısız olasılığı gösterir <xref:System.AppDomain> veya işlem durumu bozuk veya kurtarılamaz.</span><span class="sxs-lookup"><span data-stu-id="8861a-117">The activation of this MDA indicates a possibility the method being called in the CER can fail in a way that the caller did not expect or that leaves the <xref:System.AppDomain> or process state corrupted or unrecoverable.</span></span> <span data-ttu-id="8861a-118">Elbette, çağrılan kodu doğru yürütebilir ve yalnızca eksik sözleşme sorunudur.</span><span class="sxs-lookup"><span data-stu-id="8861a-118">Of course, the called code might execute correctly and the problem is simply a missing contract.</span></span> <span data-ttu-id="8861a-119">Ancak, güvenilir kod yazma ilgili sorunları zarif ve bir sözleşme yokluğu kodu doğru yürütmeme iyi bir göstergesidir.</span><span class="sxs-lookup"><span data-stu-id="8861a-119">However, the issues involved in writing reliable code are subtle and the absence of a contract is a good indicator the code might not execute correctly.</span></span> <span data-ttu-id="8861a-120">Sözleşmeler Programcı güvenilir bir şekilde kodlanmış ve aynı zamanda bu garantiler kodu düzeltmelerini gelecekte değiştirmez taahhüt eder göstergesidir.</span><span class="sxs-lookup"><span data-stu-id="8861a-120">The contracts are indicators that the programmer has coded reliably and also promises that these guarantees will not change in future revisions of the code.</span></span>  <span data-ttu-id="8861a-121">Diğer bir deyişle, sözleşmeler amacı ve yalnızca uygulama ayrıntılarını bildirimlerini ' dir.</span><span class="sxs-lookup"><span data-stu-id="8861a-121">That is, the contracts are declarations of intent and not just implementation details.</span></span>  
  
 <span data-ttu-id="8861a-122">Çalışma zamanı kendi beklenmeyen hataları hiçbirini geç JIT-derleme tarafından genel türler sözlüğü sunulan yöntemi kaldırmak denemez zayıf veya var olmayan bir sözleşmeyi herhangi bir yöntemle potansiyel olarak birçok beklenmedik şekilde başarısız olabileceğinden popülasyon ya da iş parçacığı, örneğin durdurur.</span><span class="sxs-lookup"><span data-stu-id="8861a-122">Because any method with a weak or nonexistent contract can potentially fail in many unpredictable ways, the runtime does not attempt to remove any of its own unpredictable failures from the method  that are introduced by lazy JIT-compiling, generics dictionary population, or thread aborts, for example.</span></span> <span data-ttu-id="8861a-123">Diğer bir deyişle, bu MDA etkinleştirildiğinde, çalışma zamanı tanımlanmakta CER içinde çağrılan yöntemin içermeyen belirtir; Bu alt ağaç hazırlamak etmeden olası hata maske yardımcı olan arama grafiği bu düğümde sonlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="8861a-123">That is, when this MDA is activated, it indicates that the runtime did not include the called method in the CER being defined; the call graph was terminated at this node because continuing to prepare this subtree would help mask the potential error.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8861a-124">Çözüm</span><span class="sxs-lookup"><span data-stu-id="8861a-124">Resolution</span></span>  
 <span data-ttu-id="8861a-125">İşlev geçerli güvenilirlik sözleşme eklemek veya bu işlev çağrısı kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="8861a-125">Add a valid reliability contract to the function or avoid using that function call.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8861a-126">Çalışma zamanı etkisi</span><span class="sxs-lookup"><span data-stu-id="8861a-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="8861a-127">Zayıf bir sözleşme CER çağırma etkisini işlemlerini tamamlamak için CER hata olabilir.</span><span class="sxs-lookup"><span data-stu-id="8861a-127">The effect of calling a weak contract from a CER could be the CER failure to complete its operations.</span></span> <span data-ttu-id="8861a-128">Bu bozulmasına yol açabilir <xref:System.AppDomain> işlem durumu.</span><span class="sxs-lookup"><span data-stu-id="8861a-128">This could lead to corruption of the <xref:System.AppDomain> process state.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8861a-129">Çıkış</span><span class="sxs-lookup"><span data-stu-id="8861a-129">Output</span></span>  
 <span data-ttu-id="8861a-130">Bu MDA dosyasından örnek çıktı verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="8861a-130">The following is sample output from this MDA.</span></span>  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a><span data-ttu-id="8861a-131">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="8861a-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8861a-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8861a-132">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution>  
 [<span data-ttu-id="8861a-133">Yönetilen hata ayıklama Yardımcıları ile hataları tanılama</span><span class="sxs-lookup"><span data-stu-id="8861a-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)