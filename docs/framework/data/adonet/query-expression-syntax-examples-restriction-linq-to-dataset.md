---
title: "Sorgu ifade sözdizimi örnekleri: Kısıtlama (LINQ-DataSet)"
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
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c63f99067215e7aa66f7c7a79c2a2f5ce45069bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="1c9ed-102">Sorgu ifade sözdizimi örnekleri: Kısıtlama (LINQ-DataSet)</span><span class="sxs-lookup"><span data-stu-id="1c9ed-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="1c9ed-103">Bu konudaki örnekler nasıl kullanılacağını gösteren <xref:System.Linq.Enumerable.Where%2A> sorgu yönteme bir <xref:System.Data.DataSet> sorgu ifade sözdizimi kullanarak.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="1c9ed-104">`FillDataSet` Bu örneklerde kullanılan yöntemi belirtilen [yüklenirken veri içine bir veri kümesi](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="1c9ed-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="1c9ed-105">Bu konudaki örnekler kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarını AdventureWorks örnek veritabanını kullanın.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1c9ed-106">Aşağıdaki örneklerde bu konudaki `using` / `Imports` deyimleri:</span><span class="sxs-lookup"><span data-stu-id="1c9ed-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="1c9ed-107">Daha fazla bilgi için bkz: [nasıl yapılır: bir LINQ to Visual Studio'da DataSet projesi oluşturma](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1c9ed-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="1c9ed-108">Where</span><span class="sxs-lookup"><span data-stu-id="1c9ed-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="1c9ed-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="1c9ed-109">Example</span></span>  
 <span data-ttu-id="1c9ed-110">Bu örnekte tüm çevrimiçi siparişleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="1c9ed-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="1c9ed-111">Example</span></span>  
 <span data-ttu-id="1c9ed-112">Bu örnekte, sipariş miktarı 2 değerinden 6'dan büyük ve olduğu siparişleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="1c9ed-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="1c9ed-113">Example</span></span>  
 <span data-ttu-id="1c9ed-114">Bu örnekte tüm kırmızı renkli ürünleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="1c9ed-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="1c9ed-115">Example</span></span>  
 <span data-ttu-id="1c9ed-116">Bu örnekte <xref:System.Linq.Enumerable.Where%2A> 1 Aralık 2002'den sonra yapılan siparişleri ve kullandığı bulmak için yöntem <xref:System.Data.DataRow.GetChildRows%2A> her sipariş için ayrıntıları almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="1c9ed-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1c9ed-117">See Also</span></span>  
 [<span data-ttu-id="1c9ed-118">Bir veri kümesine veri yükleme</span><span class="sxs-lookup"><span data-stu-id="1c9ed-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="1c9ed-119">LINQ-DataSet örnekleri</span><span class="sxs-lookup"><span data-stu-id="1c9ed-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="1c9ed-120">Standart sorgu işleçlerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="1c9ed-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)