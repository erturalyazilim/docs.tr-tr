---
title: "Verileri sıralama ve filtreleme"
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 01c09d94fd3224e8fd875b7f6eea06b2d2c35cca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="25dbe-102">Verileri sıralama ve filtreleme</span><span class="sxs-lookup"><span data-stu-id="25dbe-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="25dbe-103"><xref:System.Data.DataView> Sıralama ve filtreleme verileri çeşitli yollar sağlar bir <xref:System.Data.DataTable>:</span><span class="sxs-lookup"><span data-stu-id="25dbe-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
-   <span data-ttu-id="25dbe-104">Kullanabileceğiniz <xref:System.Data.DataView.Sort%2A> tek belirtmek için özellik veya sıralama siparişleri ve ASC (artan) ve (Azalan) DESC parametreleri dahil birden fazla sütun.</span><span class="sxs-lookup"><span data-stu-id="25dbe-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
-   <span data-ttu-id="25dbe-105">Kullanabileceğiniz <xref:System.Data.DataView.ApplyDefaultSort%2A> artan sırada bir sıralama düzeni otomatik olarak oluşturmak için özelliğini temel tablosunun sütunlarını ve birincil anahtar sütunu üzerinde.</span><span class="sxs-lookup"><span data-stu-id="25dbe-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="25dbe-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>yalnızca aşağıdaki durumlarda uygulanır **sıralama** özelliği olan bir null başvuru ya da boş bir dize ve ne zaman tablonun tanımlı bir birincil anahtara sahip.</span><span class="sxs-lookup"><span data-stu-id="25dbe-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
-   <span data-ttu-id="25dbe-107">Kullanabileceğiniz <xref:System.Data.DataView.RowFilter%2A> satır kümelerine belirtmek üzere özelliğe dayalı sütun değerlerine göre.</span><span class="sxs-lookup"><span data-stu-id="25dbe-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="25dbe-108">İçin geçerli ifadeler hakkında ayrıntılı bilgi için **RowFilter** özelliği, başvuru bilgileri için bkz <xref:System.Data.DataColumn.Expression%2A> özelliği <xref:System.Data.DataColumn> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="25dbe-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="25dbe-109">Bir veri alt kümesini dinamik bir görünümünü sağlayarak verileri üzerinde belirli bir sorgu sonuçlarını kullanmak dönmek istiyorsanız <xref:System.Data.DataView.Find%2A> veya <xref:System.Data.DataView.FindRows%2A> yöntemlerinin **DataView** en iyi performans elde etmek için yerine ayarı **RowFilter** özelliği.</span><span class="sxs-lookup"><span data-stu-id="25dbe-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="25dbe-110">Ayarı **RowFilter** özelliği veri yükü uygulamanıza ekleme ve performans azaltmak için dizini yeniden oluşturur.</span><span class="sxs-lookup"><span data-stu-id="25dbe-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="25dbe-111">**RowFilter** özelliği en iyi kullanılır verilere bağlı uygulamada burada bağlantılı denetim filtrelenen sonuçları görüntüler.</span><span class="sxs-lookup"><span data-stu-id="25dbe-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="25dbe-112">**Bul** ve **FindRows** yöntemleri yeniden oluşturulması için dizin gerek kalmadan geçerli dizini yararlanın.</span><span class="sxs-lookup"><span data-stu-id="25dbe-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="25dbe-113">Hakkında daha fazla bilgi için **Bul** ve **FindRows** yöntemleri bkz [bulma satırları](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="25dbe-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
-   <span data-ttu-id="25dbe-114">Kullanabileceğiniz <xref:System.Data.DataView.RowStateFilter%2A> özelliği görüntülemek için hangi satır sürümlerini belirtin.</span><span class="sxs-lookup"><span data-stu-id="25dbe-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="25dbe-115">**DataView** dolaylı olarak bağlı olarak kullanıma sunmak için hangi satır sürümü yönetir **RowState** temel satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="25dbe-116">Örneğin, varsa **RowStateFilter** ayarlanır **DataViewRowState.Deleted**, **DataView** sunan **özgün** satır sürümü tüm **silinmiş** olduğundan satırları hiçbir **geçerli** satır sürümü.</span><span class="sxs-lookup"><span data-stu-id="25dbe-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="25dbe-117">Hangi satır sürümü satır kullanarak yararlanılmasını belirleyebilirsiniz **RowVersion** özelliği **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="25dbe-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="25dbe-118">Aşağıdaki tabloda seçeneklerini gösterir **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="25dbe-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="25dbe-119">DataViewRowState seçenekleri</span><span class="sxs-lookup"><span data-stu-id="25dbe-119">DataViewRowState options</span></span>|<span data-ttu-id="25dbe-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="25dbe-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="25dbe-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="25dbe-121">**CurrentRows**</span></span>|<span data-ttu-id="25dbe-122">**Geçerli** tüm satır sürümü **Unchanged**, **eklenen**, ve **değiştirilen** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="25dbe-123">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-123">This is the default.</span></span>|  
    |<span data-ttu-id="25dbe-124">**Eklenen**</span><span class="sxs-lookup"><span data-stu-id="25dbe-124">**Added**</span></span>|<span data-ttu-id="25dbe-125">**Geçerli** tüm satır sürümü **eklenen** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="25dbe-126">**Silindi**</span><span class="sxs-lookup"><span data-stu-id="25dbe-126">**Deleted**</span></span>|<span data-ttu-id="25dbe-127">**Özgün** tüm satır sürümü **silinmiş** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="25dbe-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="25dbe-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="25dbe-129">**Geçerli** tüm satır sürümü **değiştirilen** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="25dbe-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="25dbe-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="25dbe-131">**Özgün** tüm satır sürümü **değiştirilen** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="25dbe-132">**Yok**</span><span class="sxs-lookup"><span data-stu-id="25dbe-132">**None**</span></span>|<span data-ttu-id="25dbe-133">Satır yok.</span><span class="sxs-lookup"><span data-stu-id="25dbe-133">No rows.</span></span>|  
    |<span data-ttu-id="25dbe-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="25dbe-134">**OriginalRows**</span></span>|<span data-ttu-id="25dbe-135">**Özgün** tüm satır sürümü **Unchanged**, **değiştirilen**, ve **silinmiş** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="25dbe-136">**Değişmedi**</span><span class="sxs-lookup"><span data-stu-id="25dbe-136">**Unchanged**</span></span>|<span data-ttu-id="25dbe-137">**Geçerli** tüm satır sürümü **Unchanged** satır.</span><span class="sxs-lookup"><span data-stu-id="25dbe-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="25dbe-138">Satır durumları ve satır sürümleri hakkında daha fazla bilgi için bkz: [satır durumları ve satır sürümleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="25dbe-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="25dbe-139">Aşağıdaki kod örneğinde gösterildiği stoktaki birim sayısını sipariş düzeyine eşit veya daha az olduğu tüm ürünleri sıralanmış sağlayıcı kimliği ve ardından ürün adına göre ilk bir görünüm oluşturur.</span><span class="sxs-lookup"><span data-stu-id="25dbe-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="25dbe-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="25dbe-140">See Also</span></span>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="25dbe-141">DataView</span><span class="sxs-lookup"><span data-stu-id="25dbe-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="25dbe-142">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="25dbe-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)