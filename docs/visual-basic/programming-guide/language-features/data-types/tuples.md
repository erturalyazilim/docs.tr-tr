---
title: Visual Basic'de diziler
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be50b22e9acca9ff8cfbde798d78869ee1c72634
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="tuples-visual-basic"></a>Diziler (Visual Basic)

Visual Basic 2017 ile başlayarak, Visual Basic Dil yapar diziler için yerleşik destek sunar tanımlama grupları oluşturma ve diziler daha kolay öğelerini erişme. Bir tanımlama grubu belirli sayıda ve değerleri dizisi olan bir hafif veri yapısıdır. Tuple örneği olduğunda sayısını ve her değeri (veya bir öğenin) veri türünü tanımlayın. Örneğin, bir 2 bölütlü (veya çifti) iki öğe sahiptir. İlk olabilir bir `Boolean` değer ikinci olsa da bir `String`. Tanımlama grupları birden çok değeri tek bir nesnede depolama kolaylaştırmak için bunlar genellikle birden çok değer döndürme için basit bir yol olarak kullanılır.

> [!IMPORTANT]
> Tuple destek gerektiren <xref:System.ValueTuple> türü. .NET Framework 4.7 yüklü değilse, NuGet paketini eklemeniz gerekir `System.ValueTuple`, hangi kullanılabilir NuGet galerisinde. Bu paketi bir derleme hatası benzer şekilde, "'ValueTuple(Of,,,)' tanımlı veya alınmamış önceden tanımlanmış türü." alabilirsiniz

## <a name="instantiating-and-using-a-tuple"></a>Örnek oluşturma ve bir tanımlama grubu kullanma

Bir tanımlama grubu, virgülle ayrılmış değerler IM parantez kapsayan tarafından örneği oluşturur. Bu değerlerin her birini daha sonra kayıt bir alan olur. Örneğin, aşağıdaki kodu Üçlü (veya 3-tanımlama grubu) ile tanımlayan bir `Date` ilk değeri olarak bir `String` , ikinci olarak ve bir `Boolean` kendi üçüncü olarak.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Varsayılan olarak, bir tanımlama grubu içindeki her alan adını dizesi oluşur `Item` birlikte alanın tabanlı konumda yer alan tanımlama grubu. Bu 3-başlığı için `Date` alandır `Item1`, `String` alandır `Item2`ve `Boolean` alanı `Item3`. Aşağıdaki örnek kod önceki satırında örneği kayıt alanların değerlerini görüntüler.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Visual Basic tanımlama grubu okuma-yazma alanlardır; bir tanımlama grubu örneği sonra değerlerini değiştirebilirsiniz. Aşağıdaki örnek önceki örnekte oluşturulan tanımlama grubu üç alanlarını ikilisi değiştirir ve sonucu görüntüler.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Örnek oluşturma ve adlandırılmış bir tanımlama grubu kullanma

Demete ait alanları için varsayılan adlar kullanmak yerine, bir örneğini oluşturabilirsiniz bir *tanımlama grubu adlı* demete ait öğelerine kendi adlarınızı atayarak. Demete ait alanlara sonra atanan adlarıyla erişilebilir *veya* varsayılan adlarına göre. Açıkça ilk alan adları dışında aynı 3-tanımlama grubu olarak daha önce aşağıdaki örnek başlatır `EventDate`, ikinci `Name`ve üçüncü `IsHoliday`. Bunu ardından alan değerlerini, bunları değiştirir ve alan değerlerini yeniden görüntüler.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="tuples-versus-structures"></a>Yapılar ve diziler

Visual Basic tanımlama grubu birini örneği olan bir değer türü olan bir **System.ValueTuple** genel türler. Örneğin, `holiday` tanımlama grubu önceki örnekte tanımlanan bir örneğidir <xref:System.ValueTuple%603> yapısı. Veriler için basit bir kapsayıcı olacak şekilde tasarlanmıştır. Birden çok veri öğeleri ile bir nesne oluşturmayı kolaylaştırmak için tanımlama grubu amaçlar olduğundan, özel bir yapıya sahip özelliklerden bazıları eksik. Bu güncelleştirmeler şunlardır:

- Müşteri üyeleri. Kendi özellikleri, yöntemleri ya da bir tanımlama grubu için olayları tanımlayamazsınız.

- Doğrulama. Alanlarına atanan veri doğrulanamıyor.

- Girişi. Visual Basic diziler değişebilir. Değişebilir veya sabit bir örneği olup olmadığını buna karşılık, özel bir yapı denetlemenize izin verir.

Özel üye, özellik ve alan doğrulama veya girişi önemliyse, Visual Basic kullanması gereken [yapısı](../../../language-reference/statements/structure-statement.md) deyimi bir özel değer türünü tanımlayın.

Visual Basic tanımlama grubu üyelerinin devralmıyor kendi **ValueTuple** türü. Kendi alanlara ek olarak, bunlar aşağıdaki yöntemler şunlardır:

| Üye | Açıklama |
| ---|---|
| CompareTo | Geçerli tanımlama grubu için başka bir tanımlama grubu aynı sayıda öğe ile karşılaştırır. |
| Eşittir | Geçerli tanımlama grubu başka bir tanımlama grubu veya nesneye eşit olup olmadığını belirler. |
| GetHashCode | Geçerli örneğe ilişkin karma kodu hesaplar. |
| ToString | Formundadır bu tanımlama grubu dize gösterimini döndürür `(Item1, Item2...)`, burada `Item1` ve `Item2` demete ait alanların değerlerini temsil eder. |

Ayrıca, **ValueTuple** türleri uygulayan <xref:System.Collections.IStructuralComparable> ve <xref:System.Collections.IStructuralEquatable> müşteri comparers tanımlamanıza izin arabirimleri.

## <a name="assignment-and-tuples"></a>Atama ve diziler

Visual Basic atama alanları aynı sayıda tanımlama grubu türleri arasındaki destekler. Aşağıdakilerden biri doğruysa alan türleri dönüştürülebilir:

- Kaynak ve hedef alan aynı türde olan.

- Kaynak türü hedef türü için bir genişletme (ya da örtük) dönüştürme tanımlanır. 

- `Option Strict`olan `On`, ve bir kaynak türü daraltma (veya açık) dönüştürülmesi hedef türü için tanımlanır. Kaynak değerin hedef türü aralık dışında ise bu dönüştürme bir özel durum.

Diğer dönüştürme atamaları dikkate alınmaz. Dizi türleri arasında izin atamalarını türlerini bakalım.

Aşağıdaki örneklerde kullanılan bu değişkenleri göz önünde bulundurun:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

İlk iki değişkenleri `unnamed` ve `anonymous`, alanlar için sağlanan anlamsal adları yok. Varsayılan alan adları olan `Item1` ve `Item2`. Son iki değişken `named` ve `differentName` anlamsal alan adları içeriyor. Bu iki başlığın alanları için farklı adlar gerektiğini unutmayın.

Dört Bu başlık aynı sayıda alanlar ('parametre' adlandırılır) sahip ve bu alan türlerini aynıdır. Bu nedenle, tüm bu atamaları çalışır:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Diziler adları atanmamıştır dikkat edin. Tanımlama grubundaki alanların sırasını aşağıdaki alanların değerlerini atanır.

Son olarak, biz atayabilirsiniz dikkat edin `named` tanımlama grubu için `conversion` başlığın olsa bile ilk alanını `named` olan bir `Integer`ve ilk alanını `conversion` olan bir `Long`. Dönüştürme çünkü bu ataması başarılı bir `Integer` için bir `Long` genişletme dönüştürme değildir.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Diziler farklı sayıda alana sahip atanabilir değil:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Diziler yöntemi olarak dönüş değerleri

Bir yöntem yalnızca tek bir değer döndürebilir. Sık sık rağmen birden çok değer döndürmek için bir yöntem çağrısı istersiniz. Bu sınırlamaya geçici bir çözüm için birkaç yol vardır:

- Özel sınıf veya yapı özellikleri oluşturabilir veya alanlar yöntemi tarafından döndürülen değerleri temsil eder. Bu nedenle bir ağır çözümdür; Bu yöntem çağrısından değerleri almak için tek amacı olan bir özel tür tanımlamanızı gerektirir.

- Tek bir değer döndürme ve yöntemine başvuruya geçirerek kalan değerler döndürür. Bu değişken ve başvuruya göre geçirme değişkenin değerini yanlışlıkla üzerine riskleri başlatmasını yükünü içerir.

- Birden çok dönüş değerleri alma için basit bir çözüm sağlar bir tanımlama grubu kullanabilirsiniz.

Örneğin, **TryParseyöntemini** .NET return yöntemleri bir `Boolean` ayrıştırma işlemi başarılı olup olmadığını belirten değer. Ayrıştırma işleminin sonucu başvuruya yöntemine geçirilen bir değişken döndürülür. Normal olarak yapılan bir çağrı gibi ayrıştırma yönteminin <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> aşağıdaki gibi görünür:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Biz çağrısı sarmalama, biz bir tanımlama grubu ayrıştırma işlemi döndürebilir <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> kendi yöntemi yöntemi. Aşağıdaki örnekte, `NumericLibrary.ParseInteger` çağrıları <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> yöntemi ve iki öğe ile adlandırılmış bir tanımlama grubu döndürür. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Ardından aşağıdaki gibi kod ile yöntemi çağırabilirsiniz:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic başlıkları ve .NET Framework diziler

Visual Basic tanımlama grubu birinin örneğidir **System.ValueTuple** .NET Framework 4.7 içinde sunulan genel türler. .NET Framework genel bir dizi de içerir **System.Tuple** sınıfları. Bu sınıfları, ancak Visual Basic diziler farklı ve **System.ValueTuple** çeşitli yollarla genel türleri:

- Öğelerini **tanımlama grubu** sınıflardır adlı özellikleri `Item1`, `Item2`ve benzeri. Visual Basic dizilerde ve **ValueTuple** türleri, başlığın öğeleri alanlardır.

- Anlamlı adlar öğelerine atayamazsınız bir **tanımlama grubu** örneği veya bir **ValueTuple** örneği. Visual Basic, alanları anlamını iletişim adları atamanıza olanak sağlar.

- Özelliklerini bir **tanımlama grubu** örnek salt okunur; başlıklar değişmez. Visual Basic dizilerde ve **ValueTuple** türleri tanımlama grubu alanlardır okuma-yazma; başlıklar değişebilir.

- Genel **tanımlama grubu** türleri başvuru türleridir. Bunlar kullanarak **tanımlama grubu** türleri nesneleri ayırma anlamına gelir. Sık kullanılan yollarına göre bu, uygulamanızın performans üzerinde ölçülebilir bir etkisi olabilir. Visual Basic başlıkları ve **ValueTuple** değer türleri türleridir.

Genişletme yöntemleri <xref:System.TupleExtensions> sınıfı kolaylaştırır Visual Basic başlıkları ve .NET arasında dönüştürme **tanımlama grubu** nesneleri. **ToTuple** yöntemi dönüştürür Visual Basic tanımlama grubu için bir .NET **tanımlama grubu** nesnesi ve **ToValueTuple** yöntemi bir .NET dönüştürür **tanımlama grubu** Visual Basic tanımlama grubu nesne.

Aşağıdaki örnek bir tanımlama grubu oluşturur, bir .NET dönüştürür **tanımlama grubu** nesne ve bir Visual Basic tanımlama grubu geri dönüştürür. Örnek daha sonra bu tanımlama grubu eşit olduğundan emin olmak için özgün bir karşılaştırır.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Ayrıca bkz.

[Visual Basic Dil Başvurusu](index.md)  
