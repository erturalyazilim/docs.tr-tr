---
title: "Nasıl yapılır: ilgili ne kadar veri alındığını denetleme"
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
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 708f972610c92aac07e06359b4f740ae6f0100be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Nasıl yapılır: ilgili ne kadar veri alındığını denetleme
Kullanım <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> yöntemi ana hedefiniz ilgili hangi verileri belirtmek için aynı anda alınan. Örneğin, müşterilerin siparişler hakkında bilgi gerekir biliyorsanız, kullanabileceğiniz <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> sipariş bilgileri, müşteri bilgileri aynı zamanda alınır emin olmak için. Bu yaklaşımın iki bilgi için veritabanı içinde yalnızca bir seyahat sonuçlanır.  
  
> [!NOTE]
>  Müşteriler hedeflediğinizde siparişleri alma gibi bir büyük projeksiyon olarak çapraz ürün alarak sorgunuzu ana hedefe ilgili verileri alabilir. Ancak bu yaklaşım genellikle dezavantajları vardır. Örneğin, yalnızca tahminleri ve değil, değiştirilebilir ve tarafından kalıcı varlıkları sonucu olan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Ve çok fazla ihtiyacınız olmayan veri alma.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, tüm `Orders` tüm `Customers` kimin Londra'da buluna alınır sorgunun yürütüldüğü zaman. Sonuç olarak, art arda gelen erişimi `Orders` özelliği bir `Customer` nesne yeni bir veritabanı sorgusu tetiklemez.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veritabanı sorgulama](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
