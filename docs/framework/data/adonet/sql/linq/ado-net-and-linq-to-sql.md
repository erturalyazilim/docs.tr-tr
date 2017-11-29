---
title: ADO.NET ve LINQ-SQL
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
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 97cf55419c6e13a497264bcbaa3a546eac37f982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="5e291-102">ADO.NET ve LINQ-SQL</span><span class="sxs-lookup"><span data-stu-id="5e291-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="5e291-103">parçası olan [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] teknoloji ailesi.</span><span class="sxs-lookup"><span data-stu-id="5e291-103"> is part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies.</span></span> <span data-ttu-id="5e291-104">Tarafından sağlanan hizmetlerin dayanır [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] sağlayıcı modeli.</span><span class="sxs-lookup"><span data-stu-id="5e291-104">It is based on services provided by the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] provider model.</span></span> <span data-ttu-id="5e291-105">Bu nedenle karıştırabilirsiniz [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] varolan kod [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] uygulamaları ve geçerli geçirmek [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] çözümleri [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e291-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applications and migrate current [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5e291-106">Aşağıdaki çizimde ilişki üst düzey bir görünümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="5e291-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="5e291-107">![LINQ-SQL ve ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="5e291-107">![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="5e291-108">Bağlantıları</span><span class="sxs-lookup"><span data-stu-id="5e291-108">Connections</span></span>  
 <span data-ttu-id="5e291-109">Mevcut bir kaynağı [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] oluşturduğunuzda bağlantı bir [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="5e291-109">You can supply an existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="5e291-110">Tüm işlemleri karşı <xref:System.Data.Linq.DataContext> (sorgular dahil olmak üzere) bu bağlantı sağlanan kullanın.</span><span class="sxs-lookup"><span data-stu-id="5e291-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="5e291-111">Bağlantı zaten açık ise [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ile işiniz bittiğinde olduğu gibi bırakır.</span><span class="sxs-lookup"><span data-stu-id="5e291-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="5e291-112">Her zaman bağlantı erişmek ve kendiniz kullanarak kapatmak <xref:System.Data.Linq.DataContext.Connection%2A> özelliği, aşağıdaki kod olduğu gibi:</span><span class="sxs-lookup"><span data-stu-id="5e291-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="5e291-113">İşlemler</span><span class="sxs-lookup"><span data-stu-id="5e291-113">Transactions</span></span>  
 <span data-ttu-id="5e291-114">Size sağlayabilir, <xref:System.Data.Linq.DataContext> uygulamanızın işlem zaten başlattı ve istediğiniz zaman kendi veritabanı işlemi ile <xref:System.Data.Linq.DataContext> yer alması için.</span><span class="sxs-lookup"><span data-stu-id="5e291-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="5e291-115">Hareketlerle yapmanın tercih edilen yöntem [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] kullanmaktır <xref:System.Transactions.TransactionScope> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="5e291-115">The preferred method of doing transactions with the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="5e291-116">Bu yaklaşımı kullanarak, veritabanları ve diğer bellekte kaynak yöneticileri arasında iş dağıtılmış işlemler yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5e291-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="5e291-117">İşlem kapsamları başlatmak için birkaç kaynakları gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5e291-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="5e291-118">Yalnızca işlem kapsamı içinde birden fazla bağlantı kurulduğunda bunların kendileri için Dağıtılmış işlemler yükseltin.</span><span class="sxs-lookup"><span data-stu-id="5e291-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="5e291-119">Bu yaklaşım tüm veritabanları için kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="5e291-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="5e291-120">Örneğin, karşı çalışırken sistem işlemleri SqlClient bağlantı yükseltemezsiniz bir [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] sunucu.</span><span class="sxs-lookup"><span data-stu-id="5e291-120">For example, the SqlClient connection cannot promote system transactions when it works against a [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] server.</span></span> <span data-ttu-id="5e291-121">Bunun yerine, kullanılmakta olan bir işlem kapsamı görür olduğunda otomatik olarak bir tam, dağıtılmış işlem kaydeder.</span><span class="sxs-lookup"><span data-stu-id="5e291-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="5e291-122">Doğrudan SQL komutları</span><span class="sxs-lookup"><span data-stu-id="5e291-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="5e291-123">Bazen durumlarda karşılaşabilirsiniz burada özelliğini <xref:System.Data.Linq.DataContext> sorgu veya değişiklikleri uygulamak istediğiniz özel görev için yeterli göndermek için.</span><span class="sxs-lookup"><span data-stu-id="5e291-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="5e291-124">Bu durumlarda, kullanabileceğiniz <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> veritabanına SQL komutlarını verin ve sorgu sonuçlarını nesnelere dönüştürmek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="5e291-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="5e291-125">Örneğin, varsayımında verilerini `Customer` sınıfı (customer1 ve customer2) üzerinde iki tablo yayılır.</span><span class="sxs-lookup"><span data-stu-id="5e291-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="5e291-126">Aşağıdaki sorgu bir dizi döndürür `Customer` nesneler:</span><span class="sxs-lookup"><span data-stu-id="5e291-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="5e291-127">Tablo sonuçları sütun adlarının sütun özellikleri varlık sınıfınızın eşleştiği sürece [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nesnelerinizi dışında herhangi bir SQL sorgu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5e291-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="5e291-128">Parametreler</span><span class="sxs-lookup"><span data-stu-id="5e291-128">Parameters</span></span>  
 <span data-ttu-id="5e291-129"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A> Yöntemi parametreleri kabul eder.</span><span class="sxs-lookup"><span data-stu-id="5e291-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="5e291-130">Aşağıdaki kod, parametreli bir sorgu çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="5e291-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="5e291-131">Parametreleri ifade edilir sorgu metni tarafından kullanılan aynı süslü gösterimini kullanarak `Console.WriteLine()` ve `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="5e291-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="5e291-132">`String.Format()`sorgu dizesini sağlar ve oluşturulan parametre adları braced süslü parametrelerle gibi değiştirir alan `@p0`, `@p1` ... `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="5e291-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e291-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5e291-133">See Also</span></span>  
 [<span data-ttu-id="5e291-134">Arka plan bilgileri</span><span class="sxs-lookup"><span data-stu-id="5e291-134">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="5e291-135">Nasıl yapılır: ADO.NET komutu ile bir DataContext arasında bir bağlantı yeniden</span><span class="sxs-lookup"><span data-stu-id="5e291-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)