---
title: "Nasıl yapılır: parametre almaz saklı yordamları kullanma"
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
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fbd4e0b7534a213f56c5c6ba60208d3024535bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="90663-102">Nasıl yapılır: parametre almaz saklı yordamları kullanma</span><span class="sxs-lookup"><span data-stu-id="90663-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="90663-103">başvuru parametreleri için çıkış parametreleri eşler ve değer türleri için parametre null olarak bildirir.</span><span class="sxs-lookup"><span data-stu-id="90663-103"> maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="90663-104">Giriş parametresi bir satır kümesi döndüren bir sorgu kullanma örneği için bkz: [nasıl yapılır: satır kümeleri iade](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="90663-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90663-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="90663-105">Example</span></span>  
 <span data-ttu-id="90663-106">Aşağıdaki örnek, tek bir giriş parametre (Müşteri Kimliği) alır ve out parametresi (o müşteri için toplam satış) döndürür.</span><span class="sxs-lookup"><span data-stu-id="90663-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="90663-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="90663-107">Example</span></span>  
 <span data-ttu-id="90663-108">Bu saklı yordam gibi çağırırsınız:</span><span class="sxs-lookup"><span data-stu-id="90663-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="90663-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="90663-109">See Also</span></span>  
 [<span data-ttu-id="90663-110">Saklı yordamlar</span><span class="sxs-lookup"><span data-stu-id="90663-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="90663-111">Örnek veritabanları yükleme</span><span class="sxs-lookup"><span data-stu-id="90663-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="90663-112">Boş değer atanabilir türleri kullanma</span><span class="sxs-lookup"><span data-stu-id="90663-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="90663-113">Boş değer atanabilen değer türleri</span><span class="sxs-lookup"><span data-stu-id="90663-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)