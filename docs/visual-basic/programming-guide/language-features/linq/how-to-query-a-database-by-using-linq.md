---
title: "Nasıl yapılır: LINQ Kullanarak Veritabanını Sorgulama (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9949b5f6f670c66463c42a71434c0cdd941c995b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="677f1-102">Nasıl yapılır: LINQ Kullanarak Veritabanını Sorgulama (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="677f1-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="677f1-103">Dil ile tümleşik sorgu (LINQ) Veritabanı bilgilerine erişmek ve sorguları yürütün daha kolay hale getirir.</span><span class="sxs-lookup"><span data-stu-id="677f1-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="677f1-104">Aşağıdaki örnek, bir SQL Server veritabanı sorguları gerçekleştirir yeni bir uygulama oluşturmak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="677f1-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="677f1-105">Bu konudaki örnekler Northwind örnek veritabanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="677f1-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="677f1-106">Northwind örnek veritabanı geliştirme bilgisayarınızda yoksa, buradan indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web sitesi.</span><span class="sxs-lookup"><span data-stu-id="677f1-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="677f1-107">Yönergeler için bkz: [örnek veritabanları yükleme](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="677f1-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="677f1-108">Bir veritabanına bir bağlantı oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="677f1-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="677f1-109">Visual Studio'da açın **Sunucu Gezgini**/**Database Explorer** tıklayarak **Sunucu Gezgini**/**veritabanı Explorer** üzerinde **Görünüm** menüsü.</span><span class="sxs-lookup"><span data-stu-id="677f1-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="677f1-110">Sağ **veri bağlantıları** içinde **Sunucu Gezgini**/**Database Explorer** ve ardından **Bağlantı Ekle**.</span><span class="sxs-lookup"><span data-stu-id="677f1-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="677f1-111">Northwind örnek veritabanı için geçerli bir bağlantı belirtin.</span><span class="sxs-lookup"><span data-stu-id="677f1-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="677f1-112">Bir LINQ to SQL dosyası içeren bir proje eklemek için</span><span class="sxs-lookup"><span data-stu-id="677f1-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="677f1-113">Visual Studio'da üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.</span><span class="sxs-lookup"><span data-stu-id="677f1-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="677f1-114">Visual Basic seçin **Windows Forms uygulaması** proje türü olarak.</span><span class="sxs-lookup"><span data-stu-id="677f1-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="677f1-115">Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.</span><span class="sxs-lookup"><span data-stu-id="677f1-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="677f1-116">Seçin **LINQ'ten SQL'e sınıflarını** öğe şablonu.</span><span class="sxs-lookup"><span data-stu-id="677f1-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="677f1-117">Dosya adı `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="677f1-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="677f1-118">**Ekle**'yi tıklatın.</span><span class="sxs-lookup"><span data-stu-id="677f1-118">Click **Add**.</span></span> <span data-ttu-id="677f1-119">Nesne İlişkisel Tasarımcısı (O/R Tasarımcısı) northwind.dbml dosyası için açıldı.</span><span class="sxs-lookup"><span data-stu-id="677f1-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="677f1-120">O/R Tasarımcısı sorgulamak için tablo eklemek için</span><span class="sxs-lookup"><span data-stu-id="677f1-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="677f1-121">İçinde **Sunucu Gezgini**/**Database Explorer**, Northwind veritabanına bağlantı genişletin.</span><span class="sxs-lookup"><span data-stu-id="677f1-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="677f1-122">Genişletme **tabloları** klasör.</span><span class="sxs-lookup"><span data-stu-id="677f1-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="677f1-123">O/R Tasarımcısı kapattıysanız, daha önce eklediğiniz northwind.dbml dosyasını çift tıklatarak yeniden açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="677f1-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="677f1-124">Müşteriler tablosunu tıklayın ve tasarımcı sol bölmesine sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="677f1-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="677f1-125">Siparişler tablosundaki tıklayın ve tasarımcı sol bölmesine sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="677f1-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="677f1-126">Tasarımcı oluşturur Yeni `Customer` ve `Order` projeniz için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="677f1-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="677f1-127">Tasarımcı otomatik olarak tablolar arasındaki ilişkileri algılar ve alt ilgili nesnelerin özelliklerini oluşturur dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="677f1-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="677f1-128">IntelliSense, örneğin, gösterecektir `Customer` nesnesi bir `Orders` özelliği tüm siparişler için o müşteri ile ilişkili.</span><span class="sxs-lookup"><span data-stu-id="677f1-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="677f1-129">Değişikliklerinizi kaydetmek ve Tasarımcısı'nı kapatın.</span><span class="sxs-lookup"><span data-stu-id="677f1-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="677f1-130">Projeyi kaydedin.</span><span class="sxs-lookup"><span data-stu-id="677f1-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="677f1-131">Veritabanını sorgulamak ve sonuçları görüntülemek üzere kod eklemek için</span><span class="sxs-lookup"><span data-stu-id="677f1-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="677f1-132">Gelen **araç**, sürükleyin bir <xref:System.Windows.Forms.DataGridView> Form1 projeniz için varsayılan Windows Form denetimi.</span><span class="sxs-lookup"><span data-stu-id="677f1-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="677f1-133">Kodu eklemek için Form1 çift `Load` olay formunun.</span><span class="sxs-lookup"><span data-stu-id="677f1-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="677f1-134">O/R Tasarımcısı tabloları eklendiğinde Tasarımcı eklenen bir <xref:System.Data.Linq.DataContext> projeniz için nesne.</span><span class="sxs-lookup"><span data-stu-id="677f1-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="677f1-135">Bu nesne, ayrı ayrı nesneleri ve koleksiyonları her tablo için ek olarak bu tablolar erişmek zorunda kodunu içerir.</span><span class="sxs-lookup"><span data-stu-id="677f1-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="677f1-136"><xref:System.Data.Linq.DataContext> Nesne projenizi adlı için .dbml dosyanızı adına dayalı.</span><span class="sxs-lookup"><span data-stu-id="677f1-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="677f1-137">Bu proje için <xref:System.Data.Linq.DataContext> nesne adlandırılan `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="677f1-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="677f1-138">Bir örneğini oluşturabilirsiniz <xref:System.Data.Linq.DataContext> tabloları, kod ve sorgu O/R tasarımcısı tarafından belirtilen.</span><span class="sxs-lookup"><span data-stu-id="677f1-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="677f1-139">Aşağıdaki kodu ekleyin `Load` veri bağlamı özellikleri olarak sunulur tabloları sorgulamak için olay.</span><span class="sxs-lookup"><span data-stu-id="677f1-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="677f1-140">Projenizi çalıştırma ve sonuçları görüntülemek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="677f1-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="677f1-141">Deneyebileceğiniz bazı ek sorgular şunlardır:</span><span class="sxs-lookup"><span data-stu-id="677f1-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="677f1-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="677f1-142">See Also</span></span>  
 [<span data-ttu-id="677f1-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="677f1-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="677f1-144">Sorguları</span><span class="sxs-lookup"><span data-stu-id="677f1-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="677f1-145">LINQ-SQL</span><span class="sxs-lookup"><span data-stu-id="677f1-145">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="677f1-146">DataContext yöntemleri (O/R Tasarımcısı)</span><span class="sxs-lookup"><span data-stu-id="677f1-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)