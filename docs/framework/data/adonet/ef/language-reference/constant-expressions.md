---
title: Sabit ifadeleri
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
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 759805b2970aa760e4bce882789efbc947303573
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="constant-expressions"></a>Sabit ifadeleri
Sabit bir ifade sabit bir değer oluşur. Sabit değerler doğrudan istemcide çeviri içermeyen sabit komut ağacı ifadeleri dönüştürülür. Bu, sabit bir değer neden ifadeleri içerir. Bu nedenle, veri kaynağı davranışı sabitleri içeren tüm ifadeler için beklenmelidir. Bu CLR davranışından farklıdır davranışa neden olabilir.  
  
 Aşağıdaki örnek, sunucu üzerinde değerlendirilir sabit bir ifade gösterir.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]bir kullanıcı sınıfı bir sabit değer olarak kullanılmasını desteklemez. Ancak, bir özellik referansı bir kullanıcı sınıfını bir sabit olarak kabul edilir ve komut ağacı sabit bir ifade için dönüştürülür ve veri kaynağı üzerinde yürütülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to Entities sorgu ifadeleri](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
