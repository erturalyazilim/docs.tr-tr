---
title: "SQL iş akışı örneği deposu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bf78f3b966b006d002771414551412ea0208e30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="sql-workflow-instance-store"></a><span data-ttu-id="6e2c0-102">SQL iş akışı örneği deposu</span><span class="sxs-lookup"><span data-stu-id="6e2c0-102">SQL Workflow Instance Store</span></span>
<span data-ttu-id="6e2c0-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] İş akışı örneği bir SQL Server 2005 veya SQL Server 2008 veritabanı ile ilgili durum bilgisini kalıcı hale getirmek için iş akışlarını tanır SQL iş akışı örneği deposu ile birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-103">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ships with the SQL Workflow Instance Store, which allows workflows to persist state information about workflow instances in a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="6e2c0-104">Bu özellik öncelikle biçiminde uygulanan <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Özet türeyen sınıf <xref:System.Runtime.DurableInstancing.InstanceStore> Kalıcılık framework'ün sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-104">This feature is primarily implemented in the form of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class, which derives from the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class of the persistence framework.</span></span> <span data-ttu-id="6e2c0-105">SQL iş akışı örneği depolama özelliğini Kalıcılık komutları mağazaya göndermek için bir konak kullanır API Kalıcılık somut bir uygulamasıdır SQL Kalıcılık sağlayıcısı meydana gelir.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-105">The SQL Workflow Instance Store feature constitutes a SQL persistence provider, which is a concrete implementation of the persistence API that a host uses to send persistence commands to the store.</span></span>  
  
 <span data-ttu-id="6e2c0-106">SQL iş akışı örneği deposuna kendini barındıran iş akışları veya kullanan iş akışı hizmetleri destekleyen <xref:System.Activities.WorkflowApplication> veya <xref:System.ServiceModel.WorkflowServiceHost> barındırılan hizmetleri yanı sıra kullanarak <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-106">The SQL Workflow Instance Store supports both self-hosted workflows or workflow services that use <xref:System.Activities.WorkflowApplication> or <xref:System.ServiceModel.WorkflowServiceHost> as well as services hosted in WAS using <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="6e2c0-107">Özelliği tarafından sunulan nesne modelini kullanarak kendini barındıran Hizmetleri için SQL iş akışı örneği depolama özelliği programlı olarak yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-107">You can configure the SQL Workflow Instance Store feature for self-hosted services programmatically by using the object model exposed by the feature.</span></span> <span data-ttu-id="6e2c0-108">Bu özellik tarafından barındırılan hizmetler için yapılandırabileceğiniz <xref:System.ServiceModel.WorkflowServiceHost> nesne modelini kullanarak programlı olarak hem de bir XML yapılandırma dosyası kullanarak.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-108">You can configure this feature for services hosted by <xref:System.ServiceModel.WorkflowServiceHost> both programmatically by using the object model and also by using an XML configuration file.</span></span>  
  
 <span data-ttu-id="6e2c0-109">SQL iş akışı örneği depolama özelliğini (**SqlWorkflowInstanceStore** sınıfı) uygulamayan <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> ve bu nedenle dayanıklı iş akışı olmayan WCF hizmetleri için Kalıcılık destek sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-109">The SQL Workflow Instance Store feature (**SqlWorkflowInstanceStore** class) does not implement <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> and hence does not offer persistence support for durable non-workflow WCF services.</span></span> <span data-ttu-id="6e2c0-110">Bu ayrıca uygulamayan <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> ve bu nedenle 3.x iş akışları için Kalıcılık destek sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-110">It also does not implement <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> and hence does not offer persistence support for 3.x workflows.</span></span> <span data-ttu-id="6e2c0-111">Özelliği, yalnızca WF 4.0 için (ve daha sonra) Kalıcılık iş akışları ve iş akışı hizmetleri destekler.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-111">The feature supports persistence for only WF 4.0 (and later) workflows and workflow services.</span></span> <span data-ttu-id="6e2c0-112">Özellik SQL Server 2005 ve SQL Server 2008 dışındaki tüm veritabanlarını da desteklemez.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-112">The feature also does not support any databases other than SQL Server 2005 and SQL Server 2008.</span></span>  
  
 <span data-ttu-id="6e2c0-113">Bu bölümdeki konularda SQL iş akışı örneği deposunun özellikleri açıklamak ve depolama yapılandırma hakkında ayrıntılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-113">The topics in this section describe properties and features of the SQL Workflow Instance Store and provide you with details on configuring the store.</span></span>  
  
 <span data-ttu-id="6e2c0-114">Windows Server App Fabric kendi örnek deposuna ve yapılandırmayı ve örnek deposuna kullanımını kolaylaştırmak için araç sağlar.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-114">Windows Server App Fabric provides its own instance store and tooling to simplify the configuration and use of the instance store.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="6e2c0-115">bkz: [Windows Server App Fabric örnek deposuna](http://go.microsoft.com/fwlink/?LinkId=201201).</span><span class="sxs-lookup"><span data-stu-id="6e2c0-115"> see [Windows Server App Fabric Instance Store](http://go.microsoft.com/fwlink/?LinkId=201201).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="6e2c0-116">Uygulama doku SQL Server Kalıcılık veritabanı bakın [uygulama doku SQL Server Kalıcılık veritabanı](http://go.microsoft.com/fwlink/?LinkId=201202)</span><span class="sxs-lookup"><span data-stu-id="6e2c0-116"> the App Fabric SQL Server Persistence Database see [App Fabric SQL Server Persistence Database](http://go.microsoft.com/fwlink/?LinkId=201202)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e2c0-117">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="6e2c0-117">In This Section</span></span>  
  
-   [<span data-ttu-id="6e2c0-118">SQL iş akışı örneği deposu özellikleri</span><span class="sxs-lookup"><span data-stu-id="6e2c0-118">Properties of SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="6e2c0-119">Nasıl yapılır: iş akışları ve iş akışı hizmetleri için SQL kalıcılığı etkinleştir</span><span class="sxs-lookup"><span data-stu-id="6e2c0-119">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [<span data-ttu-id="6e2c0-120">Örnek etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="6e2c0-120">Instance Activation</span></span>](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [<span data-ttu-id="6e2c0-121">Sorgular için destek</span><span class="sxs-lookup"><span data-stu-id="6e2c0-121">Support for Queries</span></span>](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [<span data-ttu-id="6e2c0-122">Depolama genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="6e2c0-122">Store Extensibility</span></span>](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [<span data-ttu-id="6e2c0-123">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="6e2c0-123">Security</span></span>](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [<span data-ttu-id="6e2c0-124">SQL Server Kalıcılık veritabanı</span><span class="sxs-lookup"><span data-stu-id="6e2c0-124">SQL Server Persistence Database</span></span>](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e2c0-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6e2c0-125">See Also</span></span>  
 [<span data-ttu-id="6e2c0-126">Kalıcılık örnekleri</span><span class="sxs-lookup"><span data-stu-id="6e2c0-126">Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkID=177735)