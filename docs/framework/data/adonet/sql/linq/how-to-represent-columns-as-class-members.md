---
title: "Nasıl yapılır: sütun sınıf üyeleri olarak temsil eder"
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
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0e797886b5e2fedafccf08b71e8cbb2791ea72b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="7347a-102">Nasıl yapılır: sütun sınıf üyeleri olarak temsil eder</span><span class="sxs-lookup"><span data-stu-id="7347a-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="7347a-103">Kullanım [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> bir alan veya özellik bir veritabanı sütununa ile ilişkilendirilecek özniteliği.</span><span class="sxs-lookup"><span data-stu-id="7347a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="7347a-104">Bir alan veya özellik için bir veritabanı sütununa eşlemek için</span><span class="sxs-lookup"><span data-stu-id="7347a-104">To map a field or property to a database column</span></span>  
  
-   <span data-ttu-id="7347a-105">Ekleme <xref:System.Data.Linq.Mapping.ColumnAttribute> özniteliği için özelliği veya alanı bildirimi.</span><span class="sxs-lookup"><span data-stu-id="7347a-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7347a-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="7347a-106">Example</span></span>  
 <span data-ttu-id="7347a-107">Aşağıdaki kod eşlemeleri `CustomerID` alanındaki `Customer` sınıfının `CustomerID` sütununda `Customers` veritabanı tablosu.</span><span class="sxs-lookup"><span data-stu-id="7347a-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="7347a-108">Belirtmek zorunda değilsiniz <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> adı çıkarsanabileceği varsa özelliği.</span><span class="sxs-lookup"><span data-stu-id="7347a-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="7347a-109">Bir ad belirtmezseniz, adı, özellik veya alan aynı adı olduğu kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="7347a-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7347a-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7347a-110">See Also</span></span>  
 [<span data-ttu-id="7347a-111">LINQ to SQL nesne modeli</span><span class="sxs-lookup"><span data-stu-id="7347a-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="7347a-112">Nasıl yapılır: kod düzenleyicisini kullanarak sınıflar özelleştirme</span><span class="sxs-lookup"><span data-stu-id="7347a-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)