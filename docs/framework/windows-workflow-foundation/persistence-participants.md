---
title: "Kalıcılık katılımcıları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a19099ea928e8867dd8206b8add0f1146496d052
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="persistence-participants"></a><span data-ttu-id="1962a-102">Kalıcılık katılımcıları</span><span class="sxs-lookup"><span data-stu-id="1962a-102">Persistence Participants</span></span>
<span data-ttu-id="1962a-103">Kalıcılık katılımcı bir uygulama ana bilgisayarı tarafından tetiklenen bir sürdürme işlemi (kaydetme veya yük) katılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1962a-103">A persistence participant can participate in a persistence operation (Save or Load) triggered by an application host.</span></span> <span data-ttu-id="1962a-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] İki soyut sınıflar ile birlikte gelen **PersistenceParticipant** ve **PersistenceIOParticipant**, hangi Kalıcılık katılımcı oluşturmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1962a-104">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with two abstract classes, **PersistenceParticipant** and **PersistenceIOParticipant**, which you can use to create a persistence participant.</span></span> <span data-ttu-id="1962a-105">Kalıcılık katılımcı bu sınıfların birinden türetilen, ilgi yöntemlerini uygular ve sınıfının bir örneğini ekler <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> koleksiyonunda <xref:System.ServiceModel.Activities.WorkflowServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="1962a-105">A persistence participant derives from one of these classes, implements the methods of interest, and then adds an instance of the class to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> collection on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> .</span></span> <span data-ttu-id="1962a-106">Uygulama ana bilgisayarı gibi iş akışı uzantıları için bir iş akışı örneği kalıcı olduğunda bakın ve uygun zamanlarda Kalıcılık katılımcıları uygun yöntemleri çağırma olabilir.</span><span class="sxs-lookup"><span data-stu-id="1962a-106">The application host may look for such workflow extensions when persisting a workflow instance and invoke appropriate methods on the persistence participants at appropriate times.</span></span>  
  
 <span data-ttu-id="1962a-107">Aşağıdaki listede kalan (Kaydet) işlemi farklı aşamalarında Kalıcılık alt sistemi tarafından gerçekleştirilen görevleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="1962a-107">The following list describes the tasks performed by the persistence subsystem in different stages of the Persist (Save) operation.</span></span> <span data-ttu-id="1962a-108">Kalıcılık katılımcıları üçüncü ve dördüncü aşamasında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1962a-108">The persistence participants are used in the third and fourth stages.</span></span> <span data-ttu-id="1962a-109">Katılımcı bir GÇ Katılımcısı (Ayrıca g/ç işlemlerinde katılan Kalıcılık katılımcı) ise, katılımcı de altıncı aşamasında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1962a-109">If the participant is an IO participant (a persistence participant that also participates in IO operations), the participant is also used in the sixth stage.</span></span>  
  
1.  <span data-ttu-id="1962a-110">İş akışı durumu, yer işaretleri, eşlenen değişkenleri ve zaman damgası dahil olmak üzere yerleşik değerleri toplar.</span><span class="sxs-lookup"><span data-stu-id="1962a-110">Gathers built-in values, including workflow state, bookmarks, mapped variables, and timestamp.</span></span>  
  
2.  <span data-ttu-id="1962a-111">İş akışı örneği ile ilişkili uzantı koleksiyonuna eklenen tüm Kalıcılık katılımcılar toplar.</span><span class="sxs-lookup"><span data-stu-id="1962a-111">Gathers all persistence participants that were added to the extension collection associated with the workflow instance.</span></span>  
  
3.  <span data-ttu-id="1962a-112">Çağırır <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> tüm Kalıcılık katılımcıları tarafından uygulanan yöntem.</span><span class="sxs-lookup"><span data-stu-id="1962a-112">Invokes the <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> method implemented by all persistence participants.</span></span>  
  
4.  <span data-ttu-id="1962a-113">Çağırır <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> tüm Kalıcılık katılımcıları tarafından uygulanan yöntem.</span><span class="sxs-lookup"><span data-stu-id="1962a-113">Invokes the <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> method implemented by all persistence participants.</span></span>  
  
5.  <span data-ttu-id="1962a-114">Kalıcı hale getirmek veya iş akışını kalıcı depoya kaydedin.</span><span class="sxs-lookup"><span data-stu-id="1962a-114">Persist or save the workflow into the persistence store.</span></span>  
  
6.  <span data-ttu-id="1962a-115">Çağırır <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> tüm Kalıcılık GÇ katılımcının yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1962a-115">Invokes the <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> method on all of the persistence IO participants.</span></span> <span data-ttu-id="1962a-116">Katılımcı bir GÇ Katılımcısı değilse, bu görev atlanır.</span><span class="sxs-lookup"><span data-stu-id="1962a-116">If the participant is not an IO participant, this task is skipped.</span></span> <span data-ttu-id="1962a-117">Kalıcılık bölüm işlemsel ise, işlem Transaction.Current özelliğinde sağlanır.</span><span class="sxs-lookup"><span data-stu-id="1962a-117">If the persistence episode is transactional, the transaction is provided in Transaction.Current property.</span></span>  
  
7.  <span data-ttu-id="1962a-118">Tamamlamak Kalıcılık katılımcılarını bekler.</span><span class="sxs-lookup"><span data-stu-id="1962a-118">Waits for all persistence participants to complete.</span></span> <span data-ttu-id="1962a-119">İşlem, tüm katılımcılar kalıcı örnek verileri başarılı olursa, kaydeder.</span><span class="sxs-lookup"><span data-stu-id="1962a-119">If all the participants succeed in persisting instance data, commits the transaction.</span></span>  
  
 <span data-ttu-id="1962a-120">Kalıcılık katılımcı türetilen **PersistenceParticipant** sınıfı ve uygulayabilir **CollectValues** ve **MapValues** yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="1962a-120">A persistence participant derives from the **PersistenceParticipant** class and may implement the **CollectValues** and **MapValues** methods.</span></span> <span data-ttu-id="1962a-121">Kalıcılık GÇ katılımcı türetilen **PersistenceIOParticipant** sınıfı ve uygulayabilir **BeginOnSave** uygulama yanı sıra yöntemi **CollectValues**ve **MapValues** yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="1962a-121">A persistence IO participant derives from the **PersistenceIOParticipant** class and may implement the **BeginOnSave** method in addition to implementing the **CollectValues** and **MapValues** methods.</span></span>  
  
 <span data-ttu-id="1962a-122">Her aşama, sonraki aşamasına başlamadan önce tamamlanır.</span><span class="sxs-lookup"><span data-stu-id="1962a-122">Each stage is completed before the next stage begins.</span></span> <span data-ttu-id="1962a-123">Örneğin, gelen değerleri toplanan **tüm** Kalıcılık katılımcıları ilk aşamasında.</span><span class="sxs-lookup"><span data-stu-id="1962a-123">For example, values are collected from **all** persistence participants in the first stage.</span></span> <span data-ttu-id="1962a-124">Ardından ilk aşamasında toplanan tüm değerlerin ikinci aşaması eşleme için tüm Kalıcılık katılımcıları sağlanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="1962a-124">Then all the values collected in the first stage are provided to all persistence participants in the second stage for mapping.</span></span> <span data-ttu-id="1962a-125">Ardından ilk ve İkinci aşamada eşlenen ve toplanan tüm değerleri Kalıcılık sağlayıcıya üçüncü aşamada sağlanır ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="1962a-125">Then all the values collected and mapped in the first and second stages are provided to the persistence provider in the third stage, and so on.</span></span>  
  
 <span data-ttu-id="1962a-126">Aşağıdaki liste, yükleme işlemi farklı aşamalarında Kalıcılık alt sistemi tarafından gerçekleştirilen görevleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="1962a-126">The following list describes the tasks performed by the persistence subsystem in different stages of the Load operation.</span></span> <span data-ttu-id="1962a-127">Kalıcılık katılımcıları dördüncü aşamasında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1962a-127">The persistence participants are used in the fourth stage.</span></span> <span data-ttu-id="1962a-128">Kalıcılık GÇ katılımcıları (Ayrıca g/ç işlemlerinde katılmak Kalıcılık katılımcıları) üçüncü aşamada de kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1962a-128">The persistence IO participants (persistence participants that also participate in IO operations) are also used in the third stage.</span></span>  
  
1.  <span data-ttu-id="1962a-129">İş akışı örneği ile ilişkili uzantı koleksiyonuna eklenen tüm Kalıcılık katılımcılar toplar.</span><span class="sxs-lookup"><span data-stu-id="1962a-129">Gathers all persistence participants that were added to the extension collection associated with the workflow instance.</span></span>  
  
2.  <span data-ttu-id="1962a-130">İş akışını sürdürme deposundan yükler.</span><span class="sxs-lookup"><span data-stu-id="1962a-130">Loads the workflow from the persistence store.</span></span>  
  
3.  <span data-ttu-id="1962a-131">Çağırır <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> tüm Kalıcılık GÇ Katılımcıları ve tamamlamak tüm Kalıcılık katılımcılar bekler.</span><span class="sxs-lookup"><span data-stu-id="1962a-131">Invokes the <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> on all persistence IO participants and waits for all the persistence participants to complete.</span></span> <span data-ttu-id="1962a-132">Kalıcılık bölüm işlemsel ise, işlem Transaction.Current içinde sağlanır.</span><span class="sxs-lookup"><span data-stu-id="1962a-132">If the persistence episode is transactional, the transaction is provided in Transaction.Current.</span></span>  
  
4.  <span data-ttu-id="1962a-133">İş akışı örneği Kalıcılık Mağazası'ndan alınan veriler temelinde bellekte yükler.</span><span class="sxs-lookup"><span data-stu-id="1962a-133">Loads the workflow instance in memory based on the data retrieved from the persistence store.</span></span>  
  
5.  <span data-ttu-id="1962a-134">Çağırır <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> her Kalıcılık katılımcı üzerinde.</span><span class="sxs-lookup"><span data-stu-id="1962a-134">Invokes <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> on each persistence participant.</span></span>  
  
 <span data-ttu-id="1962a-135">Kalıcılık katılımcı türetilen **PersistenceParticipant** sınıfı ve uygulayabilir **PublishValues** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1962a-135">A persistence participant derives from the **PersistenceParticipant** class and may implement the **PublishValues** method.</span></span> <span data-ttu-id="1962a-136">Kalıcılık GÇ katılımcı türetilen **PersistenceIOParticipant** sınıfı ve uygulayabilir **BeginOnLoad** uygulama yanı sıra yöntemi **PublishValues**yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1962a-136">A persistence IO participant derives from the **PersistenceIOParticipant** class and may implement the **BeginOnLoad** method in addition to implementing the **PublishValues** method.</span></span>  
  
 <span data-ttu-id="1962a-137">Bir iş akışı örneği yüklenirken Kalıcılık sağlayıcısı bu örneğinde bir kilit oluşturur.</span><span class="sxs-lookup"><span data-stu-id="1962a-137">When loading a workflow instance the persistence provider creates a lock on that instance.</span></span> <span data-ttu-id="1962a-138">Bu örnek bir çok düğümlü senaryosunda birden çok ana bilgisayar tarafından yüklenmesini engeller.</span><span class="sxs-lookup"><span data-stu-id="1962a-138">This prevents the instance from being loaded by more than one host in a multi-node scenario.</span></span> <span data-ttu-id="1962a-139">Kilitli bir iş akışı örneği yüklemeye çalışırsanız aşağıdaki gibi bir özel durum görürsünüz: özel durum "System.ServiceModel.persistence.ınstancelockexception: İstenen işlem tamamlanamadı kilidi örneği için ' 00000000-0000-0000-0000-000000000000' değil alınamadı ".</span><span class="sxs-lookup"><span data-stu-id="1962a-139">If you attempt to load a workflow instance that has been locked you will see an exception like the following: The exception " System.ServiceModel.Persistence.InstanceLockException: The requested operation could not complete because the lock for instance '00000000-0000-0000-0000-000000000000' could not be acquired".</span></span> <span data-ttu-id="1962a-140">Aşağıdakilerden biri oluştuğunda bu hataya neden olur:</span><span class="sxs-lookup"><span data-stu-id="1962a-140">This error is caused when one of the following occurs:</span></span>  
  
-   <span data-ttu-id="1962a-141">Bir çok düğümlü senaryosunda örneği başka bir ana bilgisayar tarafından yüklenir.</span><span class="sxs-lookup"><span data-stu-id="1962a-141">In a multi-node scenario the instance is loaded by another host.</span></span>  <span data-ttu-id="1962a-142">Bu tür çakışmaları çözümlemek için birkaç farklı yolu vardır: yeniden deneme ve kilit sahibi olan düğüme işleme iletmek veya işlerine kaydedemez başka bir ana neden olacak yük zorlayın.</span><span class="sxs-lookup"><span data-stu-id="1962a-142">There are a few different ways to resolve these types of conflicts: forward the processing to the node which owns the lock and retry, or force the load which will cause the other host to be unable to save their work.</span></span>  
  
-   <span data-ttu-id="1962a-143">Bir tek düğümlü senaryo ve konak kilitlendi.</span><span class="sxs-lookup"><span data-stu-id="1962a-143">In a single-node scenario and the host crashed.</span></span>  <span data-ttu-id="1962a-144">Ana bilgisayar başlatıldığında yeniden (işlem geri dönüştürme veya yeni bir Kalıcılık sağlayıcı fabrikası oluşturma) yeni ana bilgisayar olduğu kilidi henüz dolmadığından için eski ana bilgisayar tarafından hala kilitli örneğini yüklemeyi dener.</span><span class="sxs-lookup"><span data-stu-id="1962a-144">When the host starts up again (a process recycle or creating a new persistence provider factory) the new host attempts to load an instance which is still locked by the old host because the lock hasn't expired yet.</span></span>  
  
-   <span data-ttu-id="1962a-145">Bir tek düğümlü senaryo ve örnek bir noktada söz konusu durduruldu ve farklı ana bilgisayar kimliği olan yeni bir Kalıcılık sağlayıcı örneği oluşturulur</span><span class="sxs-lookup"><span data-stu-id="1962a-145">In a single-node scenario and the instance in question was aborted at some point and a new persistence provider instance is created which has a different host ID.</span></span>  
  
 <span data-ttu-id="1962a-146">Varsayılan değer olan 5 dakika kilit zaman aşımı değerine sahip, çağrılırken farklı zaman aşımı değeri belirleyebilirsiniz <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="1962a-146">The lock timeout value has a default value of 5 minutes, you can specify a different timeout value when calling <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1962a-147">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="1962a-147">In This Section</span></span>  
  
-   [<span data-ttu-id="1962a-148">Nasıl yapılır: özel Kalıcılık katılımcı oluşturma</span><span class="sxs-lookup"><span data-stu-id="1962a-148">How to: Create a Custom Persistence Participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a><span data-ttu-id="1962a-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1962a-149">See Also</span></span>  
 [<span data-ttu-id="1962a-150">Depolama genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="1962a-150">Store Extensibility</span></span>](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)