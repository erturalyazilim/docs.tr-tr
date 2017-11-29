---
title: "Özel akış denetimi etkinlikleri oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 12b5c8db096c0261041c29385b0ebe2e1569078c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-custom-flow-control-activities"></a><span data-ttu-id="65205-102">Özel akış denetimi etkinlikleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="65205-102">Creating custom flow control activities</span></span>
<span data-ttu-id="65205-103">.Net Framework benzer şekilde programlama yapıları soyut işlev akış denetimi etkinlikleri çeşitli içerir (gibi <xref:System.Activities.Statements.Flowchart>) veya standart programlama deyimleri (gibi <xref:System.Activities.Statements.If>).</span><span class="sxs-lookup"><span data-stu-id="65205-103">The .Net Framework contains a variety of flow-control activities that function similarly to abstract programming structures (such as <xref:System.Activities.Statements.Flowchart>)   or to standard programming statements (such as <xref:System.Activities.Statements.If>).</span></span> <span data-ttu-id="65205-104">Bu konu örnek projelerinden birini mimarisini açıklar [olmayan genel ForEach](../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md).</span><span class="sxs-lookup"><span data-stu-id="65205-104">This topic discusses the architecture of one of the sample projects, [Non-Generic ForEach](../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md).</span></span>  
  
## <a name="creating-the-custom-class"></a><span data-ttu-id="65205-105">Özel bir sınıf oluşturma</span><span class="sxs-lookup"><span data-stu-id="65205-105">Creating the custom class</span></span>  
 <span data-ttu-id="65205-106">Genel olmayan ForEach sınıfın alt etkinlikler zamanlamak ihtiyaç duyacağı beri türetmek gerekir <xref:System.Activities.NativeActivity>, türetilen etkinlikleri itibaren <xref:System.Workflow.Activities.CodeActivity> bu işlevselliğe sahip değil.</span><span class="sxs-lookup"><span data-stu-id="65205-106">Since the Non-Generic ForEach class will need to schedule child activities, it will need to derive from <xref:System.Activities.NativeActivity>, since activities that derive from <xref:System.Workflow.Activities.CodeActivity> do not have this functionality.</span></span>  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 <span data-ttu-id="65205-107">Özel bir sınıf etkinlik tarafından kullanılan verileri depolamak ve etkinliğin alt etkinlikleri yürütmek için işlevselliği sağlamak için birkaç üye gerektirir.</span><span class="sxs-lookup"><span data-stu-id="65205-107">The custom class requires several members to store data being used by the activity, and to provide functionality to execute the activity’s child activities.</span></span> <span data-ttu-id="65205-108">Bu üyeleri Ekle:</span><span class="sxs-lookup"><span data-stu-id="65205-108">These members include:</span></span>  
  
-   <span data-ttu-id="65205-109">`valueEnumerator`: Genel olmayan <xref:System.Activities.Variable%601> türü <xref:System.Collections.IEnumerator> öğeleri koleksiyon üzerinde döngüyle gezinmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="65205-109">`valueEnumerator`: The non-public <xref:System.Activities.Variable%601> of type <xref:System.Collections.IEnumerator> used to iterate over the collection of items.</span></span> <span data-ttu-id="65205-110">Bu üye türünde <xref:System.Activities.Variable%601> etkinlik yerine bir bağımsız değişken ya da bu nesnenin etkinlik dışında bir kaynağa sahip gerekiyorsa, kullanılacak ortak özellik dahili olarak kullanıldığından.</span><span class="sxs-lookup"><span data-stu-id="65205-110">This member is of type <xref:System.Activities.Variable%601> because it is used internally in the activity, rather than an argument or public property, which would be used if this object were to have an origin outside the activity.</span></span>  
  
-   <span data-ttu-id="65205-111">`OnChildComplete`: Ortak <xref:System.Activities.CompletionCallback> özelliği, her alt yürütme tamamlandığında yürütür.</span><span class="sxs-lookup"><span data-stu-id="65205-111">`OnChildComplete`: The public <xref:System.Activities.CompletionCallback> property that executes when each child completes execution.</span></span> <span data-ttu-id="65205-112">Değeri etkinliğin farklı örnekleri için değiştirmez beri bu üye CLR özelliği olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="65205-112">This member is defined as a CLR property, since its value will not change for different instances of the activity.</span></span>  
  
-   <span data-ttu-id="65205-113">`Values`: Alt etkinlik yineleme için kullanılan girişleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="65205-113">`Values`: The collection of inputs used for the iterations of the child activity.</span></span> <span data-ttu-id="65205-114">Bu üye türünde <xref:System.Activities.InArgument%601>, bu yana veri kaynağını dışında bir etkinliktir ancak koleksiyonunun içeriğini Etkinlik yürütme sırasında değiştirmek için beklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="65205-114">This member is of type <xref:System.Activities.InArgument%601>, since the origin of the data is outside the activity, but the contents of the collection is not expected to change during the execution of the activity.</span></span> <span data-ttu-id="65205-115">Etkinlik (eklemek veya etkinlikleri, örneğin kaldırmak için) etkinlik çalıştırırken bu koleksiyonun içeriğini değiştirme işlevselliği gerekirse, bu üye olarak tanımlanmış bir <xref:System.Activities.ActivityAction>, daha sonra her zaman değerlendirilen Böylece değişiklikleri faaliyete kullanılabilir olur, bunlara.</span><span class="sxs-lookup"><span data-stu-id="65205-115">If the activity needed the functionality to change the contents of this collection while the activity was executing (to add or remove activities, for instance), this member would have been defined as an <xref:System.Activities.ActivityAction>, which then would have been evaluated every time it was accessed, so that changes would be available to the activity.</span></span>  
  
-   <span data-ttu-id="65205-116">`Body`: Her öğe için yürütülecek etkinliği bu üye tanımlar `Values` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="65205-116">`Body`: This member defines the activity to be executed for each item in the `Values` collection.</span></span> <span data-ttu-id="65205-117">Bu üye olarak tanımlanan bir <xref:System.Activities.ActivityAction> böylece her erişildiğinde değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="65205-117">This member is defined as an <xref:System.Activities.ActivityAction> so that it is evaluated every time it is accessed.</span></span>  
  
-   <span data-ttu-id="65205-118">`Execute`: Bu yöntem `InternalExecute`, `OnForEachComplete`, ve `GetStateAndExecute` zamanlayarak ve gövde üye tanımlanan alt etkinliğin tamamlanma işleyici atamak için ortak olmayan üyeler.</span><span class="sxs-lookup"><span data-stu-id="65205-118">`Execute`: This method uses the `InternalExecute`, `OnForEachComplete`, and `GetStateAndExecute` non-public members to schedule the execution and assign the completion handler of the child activity defined in the Body member.</span></span>  
  
-   <span data-ttu-id="65205-119">`CacheMetadata`: Bu üye çalışma zamanı etkinliği yürütmek gereken bilgileri sağlar.</span><span class="sxs-lookup"><span data-stu-id="65205-119">`CacheMetadata`: This member provides the runtime with the information it needs to execute the activity.</span></span> <span data-ttu-id="65205-120">Varsayılan olarak, bir etkinlik 's `CacheMetadata` yöntemi hakkında bilgilendirmek tüm genel üyeler etkinliğin çalışma zamanı, ancak bu etkinlik için bazı işlevler özel üyelerin kullandığından, onu çalışma zamanı farkında olması için kendi varlığı çalışma zamanı bildirmesi gerekir. bunları.</span><span class="sxs-lookup"><span data-stu-id="65205-120">By default, an activity’s `CacheMetadata` method will inform the runtime of all public members of the activity, but since this activity uses private members for some functionality, it needs to inform the runtime of their existence so that the runtime can be aware of them.</span></span> <span data-ttu-id="65205-121">Bu durumda, `CacheMetadata` işlevi geçersiz kılınmıştır böylece özel `valueEnumerator` üye erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="65205-121">In this case, the `CacheMetadata` function is overridden so that the private `valueEnumerator` member can be accessed.</span></span> <span data-ttu-id="65205-122">Bu üye ayrıca değerleri etkinliği için bir bağımsız değişken oluşturur, böylece bunlar etkinliği yürütülürken geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="65205-122">This member also creates an argument for the values for the activity so that they can be passed in to the activity during execution.</span></span>