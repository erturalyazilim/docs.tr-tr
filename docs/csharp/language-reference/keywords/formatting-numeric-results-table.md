---
title: "Sayısal Sonuçlar Tablosunu Biçimlendirme (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce14d5124ffdf030701ae0fc769278da51f86cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="formatting-numeric-results-table-c-reference"></a>Sayısal Sonuçlar Tablosunu Biçimlendirme (C# Başvurusu)
Sayısal sonuçlar kullanarak biçimlendirebilirsiniz <xref:System.String.Format%2A?displayProperty=nameWithType> yöntemi, aracılığıyla veya <xref:System.Console.Write%2A?displayProperty=nameWithType> veya <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> çağırır yöntemi `String.Format`. Biçim biçim dizeleri kullanılarak belirtilir. Aşağıdaki tabloda, desteklenen standart biçim dizeleri içerir. Biçim dizesi aşağıdaki biçimdedir: `Axx`, burada `A` biçim belirteci olan ve `xx` duyarlık Belirleyicisi değil. Sayısal değer uygulanan biçimlendirme türü biçim belirteci denetler ve önemli basamak sayısını veya ondalık biçimlendirilmiş çıkış duyarlık Belirleyicisi denetler. Duyarlık Belirleyicisi aralığından 0 ile 99 değeri.  
  
 Standart ve özel biçimlendirme dizeleri hakkında daha fazla bilgi için bkz: [biçimlendirme türleri](../../../standard/base-types/formatting-types.md). Hakkında daha fazla bilgi için `String.Format` yöntemi, bkz: <xref:System.String.Format%2A?displayProperty=nameWithType>.  
  
|Biçim belirticisi|Açıklama|Örnekler|Çıkış|  
|----------------------|-----------------|--------------|------------|  
|C veya c|Para Birimi|Console.Write ("{0: c}", 2.5);<br /><br /> Console.Write ("{0: c}",-2.5);|$2.50<br /><br /> ($2.50)|  
|D veya d|Ondalık|Console.Write ("{0:D5}" 25);|00025|  
|E veya e|Bilimsel|Console.Write ("{0:E}" 250000);|2.500000E + 005|  
|F veya f|Sabit nokta|Console.Write ("{0: F2}", 25);<br /><br /> Console.Write ("{0:F0}" 25);|25.00<br /><br /> 25|  
|G veya g|Genel|Console.Write ("{0:G}" 2.5);|2,5|  
|N veya n|Sayı|Console.Write ("{0: n}", 2500000);|2,500,000.00|  
|X veya x|Onaltılık|Console.Write ("{0: x}", 250);<br /><br /> Console.Write ("{0: x}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Standart sayısal biçim dizeleri](../../../standard/base-types/standard-numeric-format-strings.md)  
 [Türler için başvuru tabloları](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [dize](../../../csharp/language-reference/keywords/string.md)
