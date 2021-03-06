---
title: "Özellik Tasarım"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a>Özellik Tasarım
Özellikler teknik olarak yöntemlere çok benzer olmakla birlikte, bunların kullanım senaryoları açısından oldukça farklı. Akıllı alanlar olarak görülmelidir. Alanları arama söz dizimi ve yöntemleri esnekliğini sahiptirler.  
  
 **✓ YAPMAK** çağıran özelliğin değerini değiştirmek açmaması gereken, yalnızca get özellikleri oluşturun.  
  
 Olması durumunda türünü unutmayın özelliği kesilebilir başvuru türü, özellik değeri yalnızca get olsa bile özellik değiştirilebilir.  
  
 **X yok** alıcı daha geniş erişilebilirlik sahip ayarlayıcı yalnızca küme özellikleri veya özellikleri sağlar.  
  
 Örneğin, özellikler, ortak bir Ayarlayıcısı ve korumalı bir alıcı ile kullanmayın.  
  
 Özellik alıcısı sağlanamaz, bunun yerine işlevi bir yöntem olarak uygular. Yöntem adı ile başlayan göz önünde bulundurun `Set` ve ne özelliği adlı ile izleyin. Örneğin, <xref:System.AppDomain> sahip olarak adlandırılan bir yöntem `SetCachePath` adlı yalnızca kümesi özelliğine sahip yerine `CachePath`.  
  
 **✓ YAPMAK** tüm özellikleri, varsayılan bir güvenlik açığı veya çok verimsiz kodu yol açmamasını sağlamak için duyarlı varsayılan değerler sağlayın.  
  
 **✓ YAPMAK** bu nesne bir geçici geçersiz durumda sonuçları olsa bile herhangi bir sırada ayarlanacak özellikler izin verir.  
  
 Diğer özelliklerin değerlerine aynı nesne üzerinde verilen burada bir özelliğin bazı değerler geçersiz olabilir bir noktasına birbiriyle ilişkili olarak iki veya daha fazla özellik yaygındır. Birbiriyle ilişkili özellikler gerçekte birlikte nesne tarafından kullanılan kadar bu gibi durumlarda, özel durumlar geçersiz durumdan kaynaklanan Ertelenen.  
  
 **✓ YAPMAK** özellik set yordamı bir özel durum oluşturursa önceki değeri korumak.  
  
 **KAÇININ x** özellik alıcıları özel durumları atma.  
  
 Özellik alıcıları basit işlemler olmalıdır ve tüm önkoşullara sahip olmamalıdır. Bir alıcı bir özel durum, bir yöntem için büyük olasılıkla tasarlanması gerekir. Bu kural dizin oluşturucular, bağımsız değişkenler doğrulama sonucu olarak özel durumlar burada bekliyoruz uygulanmaz dikkat edin.  
  
### <a name="indexed-property-design"></a>Dizin oluşturulmuş özellik Tasarım  
 Dizinli bir özelliği, parametreleri ve bir dizi dizin oluşturma için benzer özel bir sözdizimi ile çağrılabilir özel bir özelliğidir.  
  
 Dizinli Özellikler, yaygın olarak dizin oluşturucular da adlandırılır. Dizin Oluşturucular, mantıksal bir koleksiyondaki öğelerin erişim sağlayan API'lerde kullanılmalıdır. Örneğin, bir dizeyi karakter ve oluşturucuda koleksiyonudur <xref:System.String?displayProperty=nameWithType> kendi karakter erişmek için eklendi.  
  
 **✓ DÜŞÜNÜN** iç dizisinde depolanan verilere erişim sağlamak için dizin oluşturucular kullanma.  
  
 **✓ DÜŞÜNÜN** öğe koleksiyonunu temsil eden türlerinde dizin oluşturucular sağlama.  
  
 **KAÇININ x** dizin oluşturulmuş özellikleri birden fazla parametresiyle kullanarak.  
  
 Tasarım birden çok parametre gerektiriyorsa, özellik, bir erişimci gerçekten mantıksal bir koleksiyonu temsil eder. olup olmadığını alan. Yoksa, bunun yerine yöntemlerini kullanın. Yöntem adı ile başlayan göz önünde bulundurun `Get` veya `Set`.  
  
 **KAÇININ x** dışında parametre türleri oluşturucularla <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, veya enum.  
  
 Tasarım diğer türleri parametre gerektiriyorsa, API, erişimci gerçekten mantıksal bir koleksiyonu temsil eder. olup olmadığını kesinlikle yeniden. Yoksa, bir yöntem kullanın. Yöntem adı ile başlayan göz önünde bulundurun `Get` veya `Set`.  
  
 **✓ YAPMAK** adını kullanın `Item` için tabii daha iyi bir adı olmadıkça özellikleri dizine (örn., bkz: <xref:System.String.Chars%2A> özellikte `System.String`).  
  
 C# ' ta dizin oluşturucular öğesi adlı varsayılan olarak gelir. <xref:System.Runtime.CompilerServices.IndexerNameAttribute> Bu adını özelleştirmek için kullanılabilir.  
  
 **X yok** hem bir dizin oluşturucu hem de anlam olarak eşdeğerdir yöntemleri sağlar.  
  
 **X yok** aşırı yüklenmiş dizin oluşturucular bir türde birden fazla ailesi sağlayın.  
  
 Bu, C# Derleyici tarafından zorlanır.  
  
 **X yok** kullanım varsayılan olmayan dizin oluşturulmuş özellikleri.  
  
 Bu, C# Derleyici tarafından zorlanır.  
  
### <a name="property-change-notification-events"></a>Özellik değişikliği bildirim olayı  
 Bazen bir özellik değeri değişiklikleri kullanıcı bildiren bir olay sağlamak yararlıdır. Örneğin, `System.Windows.Forms.Control` başlatır bir `TextChanged` olayından sonra değerini kendi `Text` özelliği değişti.  
  
 **✓ DÜŞÜNÜN** değişiklik üst düzey API'leri (genellikle Tasarımcı bileşenleri) özellik değerlerinde değişiklik yapıldığında bildirim olayları oluşturma.  
  
 Bir kullanıcının ne zaman bir nesnenin bir özelliğini değiştirme bilmek iyi bir senaryo ise, nesnenin bir özellik için bir değişiklik bildirimi olayı tetiklemelidir.  
  
 Ancak, temel türleri veya koleksiyon gibi alt düzey API'ler için bu gibi olaylar yükseltmek için ek yükü değerinde olması olası değil. Örneğin, <xref:System.Collections.Generic.List%601> listesine yeni bir öğe eklendiğinde bu gibi olaylar oluşturmaz ve `Count` özellik değişikliği.  
  
 **✓ DÜŞÜNÜN** değişiklik bir özelliğin değerini dış zorlar değiştiğinde bildirim olayları oluşturma.  
  
 Bazı dış yürürlükte (nesne üzerinde yöntemleri çağırarak bir yol dışında) aracılığıyla bir özellik değeri değişiklikleri olursa olayları belirtmek için geliştirici değeri değişen ve değişti. İyi bir örnektir `Text` metin kutusu denetiminin özelliği. Ne zaman kullanıcı türleri metinde bir `TextBox`, özellik değeri otomatik olarak değiştirir.  
  
 *Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye tasarım yönergeleri](../../../docs/standard/design-guidelines/member.md)  
 [Framework tasarım yönergeleri](../../../docs/standard/design-guidelines/index.md)
