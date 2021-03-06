---
title: "Projeksiyonlar düzenleme"
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8afd48c6ce7c6313e82a7b74c2271f52833d1f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-projections"></a>Projeksiyonlar düzenleme
Aşağıdaki örneklerde gösterildiği nasıl `select` deyimi C# ve `Select` deyiminde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] form sorgu tahminleri için diğer özelliklerle birlikte kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) için kişi adı bir dizi döndürülecek `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) ve *anonim türler* kişi adlarının dizisini döndürür ve telefon numaraları için `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) ve *anonim türler* adlarının dizisini döndürür ve çalışanlar için telefonu numaraları. `FirstName` Ve `LastName` alanları tek bir alana birleştirilir (`Name`) ve `HomePhone` alan yeniden adlandırılamaz `Phone` elde edilen sıralı.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) ve *anonim türler* tüm bir dizi döndürülecek `ProductID`s ve adlı hesaplanan değeri `HalfPrice`. Bu değer ayarlanırsa `UnitPrice` 2 tarafından ayrılmış.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) ve bir *koşullu ifade* bir dizi ürün adı ve ürün kullanılabilirlik dönün.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` yan tümcesi (`select` yan tümcesinde C#) ve bir *türü bilinen* bir dizi çalışanların adlarını döndürmek için (ad).  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Select` ve `Where` içinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` ve `where` C#) döndürmek için bir *sırası filtre* Londra müşteriler için kişi adları.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir `Select` yan tümcesinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` yan tümcesinde C#) ve *anonim türler* döndürmek için bir *alt şeklinde* müşteriler ilgili veriler.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, aşağıdaki sonuçları döndürmek için iç içe geçmiş sorgular kullanır:  
  
-   Tüm siparişler ve bunların karşılık gelen bir dizi `OrderID`s.  
  
-   Bir değişkene bir indirim siparişi öğeler.  
  
-   Sevkiyat maliyetini dahil edilmezse kaydedilen para miktarı.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sorgu örnekleri](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
