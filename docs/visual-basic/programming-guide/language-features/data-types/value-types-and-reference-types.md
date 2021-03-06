---
title: "Değer Türleri ve Başvuru Türleri"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b54945d27d186771e8b5353e753afd74c56d71b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-and-reference-types"></a>Değer Türleri ve Başvuru Türleri
Visual Basic veri türleri sınıflandırmalarına göre uygulanır. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Veri türleri sınıflandırılmış belirli türde bir değişken kendi veri veya veri için bir işaretçi depolar göre. Kendi verilerini depolayan ise bir *değer türü*; başka bir yerde bu bellek verileri için bir işaretçi barındırıyorsa bir *başvuru türüne*.  
  
## <a name="value-types"></a>Değer Türleri  
 Bir veri türü olan bir *değer türü* kendi bellek ayırma içindeki verilere tutuyorsa. Değer türleri şunlardır:  
  
-   Tüm sayısal veri türleri  
  
-   `Boolean`, `Char`, ve`Date`  
  
-   Başvuru türleri üyeleri olan olsa bile tüm yapıları  
  
-   Kendi temel alınan türü her zaman olduğundan numaralandırmalar `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, veya`ULong`  
  
 Başvuru türü üyeleri içerse bile, her bir değer türü yapısıdır. Bu nedenle, değer türleri gibi `Char` ve `Integer` .NET Framework yapıları tarafından uygulanır.  
  
 Ayrılmış bir anahtar sözcük, örneğin, kullanarak bir değer türü bildirebilirsiniz `Decimal`. Aynı zamanda `New` anahtar sözcüğü bir değer türü başlatılamadı. Bu tür parametreler isteyen bir kurucusunun özellikle yararlıdır. Bunun bir örneği <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> yeni yapılar Oluşturucusu `Decimal` sağlanan bölümlerinden değeri.  
  
## <a name="reference-types"></a>Başvuru Türleri  
 A *başvuru türüne* verilerini tutan başka bir bellek konumunu gösteren bir işaretçi içeriyor. Başvuru türleri şunlardır:  
  
-   `String`  
  
-   Değer türleri kendi öğeleridir olsa bile tüm diziler  
  
-   Sınıf türleri, gibi<xref:System.Windows.Forms.Form>  
  
-   Temsilciler  
  
 Bir sınıf bir *başvuru türüne*. Bu nedenle, başvuru türleri gibi `Object` ve `String` tarafından desteklenen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] sınıfları. Değer türleri üyeleri olsa bile, her dizi bir başvuru türü olduğunu unutmayın.  
  
 Her başvuru türündeki temel alınan bir .NET Framework sınıfı temsil ettiği kullanmalısınız [New işleci](../../../../visual-basic/language-reference/operators/new-operator.md) , Initialize when anahtar sözcüğü. Aşağıdaki deyim, bir dizi başlatır.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Türleri olmayan öğeler  
 Bildirilen öğe için bir veri türü olarak hiçbirini belirtilemez çünkü aşağıdaki programlama öğeleri türleri olarak nitelemek değil:  
  
-   Ad Alanları  
  
-   Modüller  
  
-   Olaylar  
  
-   Özellikler ve yordamları  
  
-   Değişkenlerinin, sabitleri ve alanlar  
  
## <a name="working-with-the-object-data-type"></a>Nesne veri türü ile çalışma  
 Bir değişken için bir başvuru türü veya bir değer türü atayabilirsiniz `Object` veri türü. Bir `Object` değişkeni verileri verilerin kendisini hiçbir zaman, her zaman bir işaretçi tutar. Ancak, bir değer türü atarsanız bir `Object` kendi verilerini varmış gibi değişken, davranır. Daha fazla bilgi için bkz: [nesne veri türü](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Tanımlanmadığını bulabileceğiniz bir `Object` değişken işlevi gören bir başvuru türü veya bir değer türü olarak geçirerek <xref:Microsoft.VisualBasic.Information.IsReference%2A> yönteminde <xref:Microsoft.VisualBasic.Information> sınıfının <xref:Microsoft.VisualBasic?displayProperty=nameWithType> ad alanı. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>döndürür `True` varsa içeriğini `Object` değişkeni bir başvuru türü temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Boş değer atanabilen değer türleri](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Visual Basic'de tür dönüştürmeleri](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Structure deyimi](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Veri türlerinin etkili kullanımı](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Nesne veri türü](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Veri türleri](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
