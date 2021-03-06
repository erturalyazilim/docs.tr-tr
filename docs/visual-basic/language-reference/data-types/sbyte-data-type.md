---
title: "SByte Veri Türü (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a>SByte veri türü (Visual Basic)

Ayrı tutma -128 değeri ile 127 arasında 8 bit (1-bayt) tamsayıları imzalanmış.  
  
## <a name="remarks"></a>Açıklamalar

Kullanım `SByte` veri türü tam veri genişliği gerektirmeyen tamsayı değerleri içeren `Integer` veya hatta yarım veri genişliği `Short`. Bazı durumlarda, ortak dil çalışma zamanı paketi olabilir, `SByte` değişkenleri yakın işbirliği içinde ve bellek tüketimi.

Varsayılan değer olan `SByte` 0'dır.

## <a name="literal-assignments"></a>Değişmez değer atamaları
  
Bildirme ve başlatma bir `SByte` değişken bir ondalık değişmez değeri, onaltılık değişmez değeri bir sekizlik değişmez değeri atama veya (Visual Basic 2017 ile ikili bir hazır değer başlayarak).

Aşağıdaki örnekte, ondalık sayı olarak, onaltılık temsil-102 tamsayılar eşit ve ikili değişmez değerler atanır `SByte` değerleri. Bu örnek ile derleme gerektirir `/removeintchecks` derleyici anahtar.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Önek kullanması `&h` veya `&H` bir onaltılık değişmez değeri, öneki belirtmek için `&b` veya `&B` ikili bir hazır değer ve öneki belirtmek için `&o` veya `&O` sekizlik değişmez değeri belirtmek için. Ondalık değişmez değerler, önek vardır.

Visual Basic 2017 ile başlayarak, alt çizgi karakteri de kullanabilirsiniz `_`, okunabilirliğini artırmak için bir basamak ayırıcı olarak, aşağıdaki örnekte görüldüğü gibi.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Değişmez değer tamsayı aralığı dışında ise `SByte` (diğer bir deyişle, bu ise değerinden <xref:System.SByte.MinValue?displayProperty=nameWithType> veya daha büyük <xref:System.SByte.MaxValue?displayProperty=nameWithType>, derleme hatası oluşur. Hiçbir soneki değişmez değer bir tamsayı sahip olduğunda bir [tamsayı](integer-data-type.md) algılanır. Değişmez değer tamsayı aralığı dışında ise `Integer` türü, bir [uzun](long-data-type.md) algılanır. Bu, önceki örneklerde, sayısal değişmez değerleri anlamına `0x9A` ve `0b10011010` 32 bit imzalı tamsayılar aşıyor 156, değerini olarak yorumlanır <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Başarıyla bir ondalık olmayan tamsayıya atayan şöyle Kodu derlemek için bir `SByte`, aşağıdakilerden birini yapabilirsiniz:

- Tamsayı sınırları denetimleri ile derleme tarafından devre dışı `/removeintchecks` derleyici anahtar.

- Kullanım bir [türü karakteri](../../programming-guide\language-features\data-types/type-characters.md) atamak istediğiniz hazır değeri açıkça tanımlamak için `SByte`. Aşağıdaki örnek negatif bir hazır değer atar `Short` değeri bir `SByte`. Negatif sayılar için dikkat edin, yüksek sıralı bit yüksek düzey Word nümerik sabit değer olarak ayarlanması gerekir. Bizim örneğimizde söz konusu olduğunda, bu bit değişmez değeri 15 `Short` değeri.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Programlama ipuçları
  
-   **CLS uyumluluğu.** `SByte` Veri türü değil parçası [ortak dil belirtimi](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), CLS uyumlu kod kullandığı bir bileşen kullanamayacaklarını şekilde.

-   **Genişletme.** `SByte` Veri türü widens için `Short`, `Integer`, `Long`, `Decimal`, `Single`, ve `Double`. Bu dönüştürebilirsiniz anlamına gelir `SByte` karşılaşmadan olmadan bu türdeki herhangi bir <xref:System.OverflowException?displayProperty=nameWithType> hata.
  
-   **Karakterleri yazın.** `SByte`değişmez değer türü karakteri ya da tanımlayıcı türü karakteri içeriyor.  
  
-   **Framework türü.** .NET Framework'teki karşılık gelen tür <xref:System.SByte?displayProperty=nameWithType> yapısı.
  
## <a name="see-also"></a>Ayrıca bkz.

 <xref:System.SByte?displayProperty=nameWithType>  
 [Veri türleri](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tür dönüşüm işlevleri](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Dönüştürme özeti](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short veri türü](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer veri türü](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long veri türü](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Veri türlerinin etkili kullanımı](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
