---
title: "Nasıl yapılır: PLINQ Sorgu Performansını Ölçme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03432e70454cb6203e55e340111a6cb7efe62dc4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-measure-plinq-query-performance"></a>Nasıl yapılır: PLINQ Sorgu Performansını Ölçme
Bu örnek nasıl kullanıldığını gösterir <xref:System.Diagnostics.Stopwatch> bir PLINQ sorgusu çalıştırmak geçen süreyi ölçmek için sınıf.  
  
## <a name="example"></a>Örnek  
 Bu örnekte boş bir `foreach` döngü (`For Each` Visual Basic'te) sorguyu yürütmek gereken süreyi ölçmek için. Gerçek kodda döngü genellikle toplam sorgu yürütme zamana ekle ek işleme adımları içerir. Kronometre değil dikkat edin, yalnızca kadar döngü önce ne zaman olduğundan başlatılan sorgu yürütme başlar. Daha fazla hassas ölçüm gerektiriyorsa, kullanabileceğiniz `ElapsedTicks` özelliği yerine `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Toplam yürütme süresi bir yararlı sorgu uygulamaları ile denemeler ancak Yazının tamamını her zaman söylemez ölçümüdür. Birbirleriyle ve diğer çalışan işlemleri ile etkileşim sorgu iş parçacığı daha derin ve daha zengin bir görünümünü almak için eşzamanlılık görselleştiricisi kullanın. Daha fazla bilgi için bkz: [eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
