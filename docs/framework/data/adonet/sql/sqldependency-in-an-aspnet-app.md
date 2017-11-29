---
title: "Bir ASP.NET uygulamasında SqlDependency"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69cdb468098a373f17ec25f28e43b77c650cc05f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="61181-102">Bir ASP.NET uygulamasında SqlDependency</span><span class="sxs-lookup"><span data-stu-id="61181-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="61181-103">Bu bölümdeki örnek nasıl kullanılacağını gösterir <xref:System.Data.SqlClient.SqlDependency> ASP.NET yararlanarak dolaylı olarak <xref:System.Web.Caching.SqlCacheDependency> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="61181-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="61181-104"><xref:System.Web.Caching.SqlCacheDependency> Nesne kullanan bir <xref:System.Data.SqlClient.SqlDependency> bildirimleri için dinleme ve doğru önbelleğini güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="61181-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61181-105">Örnek kod sorgu bildirimleri komut yürüterek etkinleştirdiğiniz varsayar [etkinleştirme sorgu bildirimleri](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="61181-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="61181-106">Örnek uygulama hakkında</span><span class="sxs-lookup"><span data-stu-id="61181-106">About the Sample Application</span></span>  
 <span data-ttu-id="61181-107">Örnek uygulama, ürün bilgilerini görüntülemek için tek bir ASP.NET Web sayfası kullanır **AdventureWorks** SQL Server veritabanında bir <xref:System.Web.UI.WebControls.GridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="61181-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="61181-108">Sayfa yüklendiğinde, geçerli tarihe kadar kod yazar bir <xref:System.Web.UI.WebControls.Label> denetim.</span><span class="sxs-lookup"><span data-stu-id="61181-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="61181-109">Ardından tanımlayan bir <xref:System.Web.Caching.SqlCacheDependency> nesne ve özellikleri ayarlar <xref:System.Web.Caching.Cache> üç dakikaya kadar önbellek verilerini depolamak için nesne.</span><span class="sxs-lookup"><span data-stu-id="61181-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="61181-110">Kod veritabanına bağlanır ve verileri alır.</span><span class="sxs-lookup"><span data-stu-id="61181-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="61181-111">Ne zaman sayfa yüklendikten ve ASP.NET uygulamasını çalıştıran sayfasında süre değişmez belirtmeye doğrulayabilirsiniz önbellekten verileri alır.</span><span class="sxs-lookup"><span data-stu-id="61181-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="61181-112">İzlenmekte olan verileri ASP.NET değişip değişmediğini önbelleği geçersiz kılar ve yeniden `GridView` görüntülenen saati güncelleştiriliyor yeni verilerle denetim `Label` denetim.</span><span class="sxs-lookup"><span data-stu-id="61181-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="61181-113">Örnek uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="61181-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="61181-114">Oluşturun ve örnek uygulamayı çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="61181-114">Follow these steps to create and run the sample application:</span></span>  
  
1.  <span data-ttu-id="61181-115">Yeni bir ASP.NET Web sitesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="61181-115">Create a new ASP.NET Web site.</span></span>  
  
2.  <span data-ttu-id="61181-116">Ekleme bir <xref:System.Web.UI.WebControls.Label> ve <xref:System.Web.UI.WebControls.GridView> Default.aspx sayfasında denetimine.</span><span class="sxs-lookup"><span data-stu-id="61181-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3.  <span data-ttu-id="61181-117">Sayfanın sınıf modülü açın ve aşağıdaki yönergeleri ekleyin:</span><span class="sxs-lookup"><span data-stu-id="61181-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  <span data-ttu-id="61181-118">Sayfanın içinde aşağıdaki kodu ekleyin `Page_Load` olay:</span><span class="sxs-lookup"><span data-stu-id="61181-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  <span data-ttu-id="61181-119">İki yardımcı yöntem ekler `GetConnectionString` ve `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="61181-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="61181-120">Tanımlanan bağlantı dizesi tümleşik güvenliği kullanır.</span><span class="sxs-lookup"><span data-stu-id="61181-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="61181-121">Kullandığınız hesabın gerekli veritabanı izinleri olduğunu doğrulamanız gerekir örnek veritabanı **AdventureWorks**, etkin bildirimleri sahiptir.</span><span class="sxs-lookup"><span data-stu-id="61181-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span> <span data-ttu-id="61181-122">Daha fazla bilgi için bkz: [özel dikkat edilecek noktalar kullanarak sorgu bildirimleri](http://msdn.microsoft.com/en-us/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span><span class="sxs-lookup"><span data-stu-id="61181-122">For more information, see [Special Considerations When Using Query Notifications](http://msdn.microsoft.com/en-us/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="61181-123">Uygulamayı Test Etme</span><span class="sxs-lookup"><span data-stu-id="61181-123">Testing the Application</span></span>  
 <span data-ttu-id="61181-124">Uygulama, Web formunda görüntülenen verileri önbelleğe alır ve etkinlik yoksa üç dakikada bir yenilenir.</span><span class="sxs-lookup"><span data-stu-id="61181-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="61181-125">Veritabanına bir değişiklik meydana gelirse, önbellek hemen yenilenir.</span><span class="sxs-lookup"><span data-stu-id="61181-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="61181-126">Visual Studio'dan sayfa tarayıcısına yükleyen, uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="61181-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="61181-127">Görüntülenen önbellek yenileme zamanı önbellek son ne zaman yenilendiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="61181-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="61181-128">Üç dakika bekleyin ve sonra gerçekleşmesi bir geri gönderme olayı neden sayfayı yenileyin.</span><span class="sxs-lookup"><span data-stu-id="61181-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="61181-129">Sayfada görüntülenen zaman değiştiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="61181-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="61181-130">Üç dakikadan daha kısa bir süre içinde sayfayı yenileyin, sayfada görüntülenen zaman aynı kalır.</span><span class="sxs-lookup"><span data-stu-id="61181-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="61181-131">Şimdi bir Transact-SQL güncelleştirme komut kullanarak veritabanındaki verileri güncelleştirin ve sayfayı yenileyin.</span><span class="sxs-lookup"><span data-stu-id="61181-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="61181-132">Görüntülenen zaman şimdi önbellek veritabanından yeni verileri yenilendiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="61181-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="61181-133">Önbelleği güncelleştirilirken rağmen geri gönderme olay gerçekleşene kadar sayfada görüntülenen saati değişmez unutmayın.</span><span class="sxs-lookup"><span data-stu-id="61181-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61181-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="61181-134">See Also</span></span>  
 [<span data-ttu-id="61181-135">SQL Server'da sorgu bildirimleri</span><span class="sxs-lookup"><span data-stu-id="61181-135">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="61181-136">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="61181-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)