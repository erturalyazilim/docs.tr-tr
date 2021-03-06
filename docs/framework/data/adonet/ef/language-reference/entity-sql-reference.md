---
title: "Varlık SQL Başvurusu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 776a2a93f559ba54651adc49e6b609c8156e9e31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="entity-sql-reference"></a>Varlık SQL Başvurusu
Bu bölüm içerir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] başvuru konuları. Bu konuda özetler ve grupları [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kategoriye göre işleçler.  
  
## <a name="arithmetic-operators"></a>Aritmetik İşleçler  
 Aritmetik işleçler bir veya daha fazla sayısal veri türleri iki ifadeye matematik işlemleri gerçekleştirir. Aşağıdaki tabloda [!INCLUDE[esql](../../../../../../includes/esql-md.md)] aritmetik işleçler.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[+ (Ekle)](../../../../../../docs/framework/data/adonet/ef/language-reference/add.md)|Ayrıca.|  
|"/ (Bölme)"|Bölme.|  
|[% (Modül)](../../../../../../docs/framework/data/adonet/ef/language-reference/modulo-entity-sql.md)|Bölme kalanı döndürür.|  
|[* (Çarp)](../../../../../../docs/framework/data/adonet/ef/language-reference/multiply-entity-sql.md)|Çarpma.|  
|[-(Negatif)](../../../../../../docs/framework/data/adonet/ef/language-reference/negative-entity-sql.md)|Değilleme.|  
|[-(Çıkart)](../../../../../../docs/framework/data/adonet/ef/language-reference/subtract-entity-sql.md)|Çıkarma.|  
  
## <a name="canonical-functions"></a>Kurallı işlevleri  
 Kurallı işlevleri tüm veri sağlayıcıları tarafından desteklenir ve tüm sorgulanırken teknolojileri ile kullanılabilir. Aşağıdaki tabloda kurallı işlevleri listeler.  
  
|İşlev|Tür|  
|--------------|----------|  
|[Birleşik varlık SQL kurallı işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|Toplama anlatılmaktadır [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri.|  
|[Kurallı matematik işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|Matematik anlatılmaktadır [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri.|  
|[Dize kurallı işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|Dize anlatılmaktadır [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri.|  
|[Tarih ve saat kurallı işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Tarih ve saat anlatılmaktadır [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri.|  
|[Bit düzeyinde kurallı işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Bit düzeyinde ele [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri.|  
|[Kurallı diğer işlevleri](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)|Bit düzeyinde, tarih, dize, matematik veya toplu olarak sınıflandırılan değil işlevleri açıklanır.|  
  
## <a name="comparison-operators"></a>Karşılaştırma İşleçleri  
 Karşılaştırma işleçleri şu türler için tanımlanır: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` , `DateTimeOffset`. Karşılaştırma işleci uygulanmadan önce örtük tür yükseltme işlenenler için oluşur. Karşılaştırma işleçleri her zaman Boole değerleri verim. İşlenen en az biri olduğunda `null`, sonuç `null`.  
  
 Eşitlik ve eşitsizlik gibi kimliğine sahip nesne türü için tanımlanmış `Boolean` türü. Kimliğine sahip olmayan ilkel nesneleri aynı kimliğe paylaşıyorsanız eşit olarak kabul edilir. Aşağıdaki tabloda [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Karşılaştırma işleçleri.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[= (Eşittir)](../../../../../../docs/framework/data/adonet/ef/language-reference/equals-entity-sql.md)|İki ifadeye eşitliğini karşılaştırır.|  
|[> (Büyük)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-entity-sql.md)|Sol ifade sağ ifade büyük bir değere sahip olup olmadığını belirlemek için iki ifadeye karşılaştırır.|  
|[> = (büyüktür veya eşittir)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-or-equal-to-entity-sql.md)|Sol ifade sağ ifade eşit veya daha büyük bir değere sahip olup olmadığını belirlemek için iki ifadeye karşılaştırır.|  
|[OLAN &#91; DEĞİL &#93; NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/isnull-entity-sql.md)|Bir sorgu ifadesi null olup olmadığını belirler.|  
|[< (Küçüktür)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-entity-sql.md)|Sol ifade sağ ifade'den küçük bir değer olup olmadığını belirlemek için iki ifadeye karşılaştırır.|  
|[< = (küçük veya eşittir)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-or-equal-to-entity-sql.md)|Sol ifade bir değere eşit veya sağ ifade için olup olmadığını belirlemek için iki ifadeye karşılaştırır.|  
|[&#91; DEĞİL &#93; ARASINDA](../../../../../../docs/framework/data/adonet/ef/language-reference/between-entity-sql.md)|Belirtilen aralıktaki bir değere bir ifade sonucu olup olmadığını belirler.|  
|[! = (Eşit değildir)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-equal-to-entity-sql.md)|Sol ifade sağ ifade eşit olup olmadığını belirlemek için iki ifadeye karşılaştırır.|  
|[&#91; DEĞİL &#93; GİBİ](../../../../../../docs/framework/data/adonet/ef/language-reference/like-entity-sql.md)|Bir özel karakter dizesi belirtilen desenle eşleşip eşleşmediğini belirler.|  
  
## <a name="logical-and-case-expression-operators"></a>Mantıksal ve büyük/küçük harfe ifade işleçleri  
 Mantıksal işleçler bir koşul gerçekte için test edin. Servis talebi ifade sonucu belirlemek için Boole ifadeleri kümesi olur. Aşağıdaki tabloda, mantıksal ve büyük/küçük HARFE ifadesi işleçleri listeler.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[& & (Mantıksal ve)](../../../../../../docs/framework/data/adonet/ef/language-reference/and-entity-sql.md)|Mantıksal and|  
|[! (Mantıksal değil)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-entity-sql.md)|Mantıksal değil.|  
|[&#124; &#124; (Mantıksal OR)](../../../../../../docs/framework/data/adonet/ef/language-reference/or-entity-sql.md)|Mantıksal OR.|  
|[DURUMU](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)|Boole ifadeleri sonucu belirlemek için bir dizi değerlendirir.|  
|[ARDINDAN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)|Sonucunu bir [zaman](http://msdn.microsoft.com/en-us/6233fe9f-00b0-460e-8372-64e138a5f998) doğru olarak değerlendirildiğinde yan tümcesi.|  
  
## <a name="query-operators"></a>Sorgu işleçleri  
 Sorgu işleçleri, varlık veri döndüren sorgu ifadeleri tanımlamak için kullanılır. Aşağıdaki tabloda, sorgu işleçleri listeler.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[KAYNAK](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)|Kullanılan koleksiyon belirtir [seçin](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) deyimleri.|  
|[GRUPLANDIRMA ÖLÇÜTÜ](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)|Hangi nesneleri, bir sorgu tarafından döndürülür grupları belirtir ([seçin](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) ifade olan yerleştirilecek.|  
|[Grouppartıtıon](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md)|Bağımsız değişken değerleri toplama ilgili olduğu Grup bölümünün öngörülen koleksiyonunu döndürür.|  
|[SAHİP](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)|Bir grup veya bir toplama için bir arama koşulu belirtir.|  
|[SINIRI](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)|İle kullanılan [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) gerçekleştirilen fiziksel disk belleği yan tümcesini.|  
|[SIRALAMA ÖLÇÜTÜ](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)|Döndürülen nesneler üzerinde kullanılan sıralama düzenini belirleyen bir [seçin](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) deyimi.|  
|[SEÇİN](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)|Öğeleri bir sorgu tarafından döndürülen projeksiyon belirtir.|  
|[ATLA](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)|İle kullanılan [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) gerçekleştirilen fiziksel disk belleği yan tümcesini.|  
|[SAYFANIN ÜSTÜ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)|Yalnızca ilk satır kümesini sorgu sonuç döndürülür belirtir.|  
|[BURADA](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)|Koşullu bir sorgu tarafından döndürülen veri filtreler.|  
  
## <a name="reference-operators"></a>Başvuru işleçleri  
 Belirli bir varlık kümesinde belirli bir varlık için bir mantıksal işaretçisi (yabancı anahtar) başvurudur. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]oluşturun, deconstruct ve başvurular arasında gezinmek için aşağıdaki işleçleri destekler.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)|Bir varlık başvuruları bir varlık kümesi oluşturur.|  
|[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)|Bir başvuru değer ve başvuru sonucu, üretir dereferences.|  
|[ANAHTARI](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)|Bir başvuru veya varlık ifade anahtarını ayıklar.|  
|[GİDİN](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)|Bir varlık türü arasında ilişki üzerinden giderek sağlar|  
|[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)|Bir varlık örneği için bir başvuru döndürür.|  
  
## <a name="set-operators"></a>Küme işleci  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]çeşitli güçlü işlemler sağlar. Bu küme işleci UNION, INTERSECT, EXCEPT, Transact-SQL işleçleriyle benzer içerir ve EXISTS. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Ayrıca işleçleri yinelenen eleme (küme), (gelen) sınama üyeliği ve birleşimler (birleştirme) destekler. Aşağıdaki tabloda [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri ayarlayın.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[ANYELEMENT](../../../../../../docs/framework/data/adonet/ef/language-reference/anyelement-entity-sql.md)|Bir öğenin birden çok değerli bir koleksiyondan ayıklar.|  
|[DIŞINDA](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)|Tüm farklı değerler koleksiyonu sorgu ifadesinden de sorgu ifadesinden EXCEPT işleneni sağındaki döndürülmez EXCEPT işleneni sola döndürür.|  
|[&#91; DEĞİL &#93; VAR](../../../../../../docs/framework/data/adonet/ef/language-reference/exists-entity-sql.md)|Bir koleksiyonu boş olup olmadığını belirler.|  
|[DÜZLEŞTİRME](../../../../../../docs/framework/data/adonet/ef/language-reference/flatten-entity-sql.md)|Değişkeninin bir koleksiyonlar koleksiyonu düzleştirilmiş bir koleksiyonuna dönüştürür.|  
|[&#91; DEĞİL &#93; IN](../../../../../../docs/framework/data/adonet/ef/language-reference/in-entity-sql.md)|Bir değer bir koleksiyondaki herhangi bir değer eşleşip eşleşmediğini belirler.|  
|[INTERSECT](../../../../../../docs/framework/data/adonet/ef/language-reference/intersect-entity-sql.md)|Her iki sorgu ifadeleri sol tarafından döndürülen tüm farklı değerler koleksiyonu ve INTERSECT işleneni sağ tarafında döndürür.|  
|[ÇAKIŞIYOR](../../../../../../docs/framework/data/adonet/ef/language-reference/overlaps-entity-sql.md)|İki koleksiyon ortak öğeler sahip olup olmadığını belirler.|  
|[AYARLAMA](../../../../../../docs/framework/data/adonet/ef/language-reference/set-entity-sql.md)|Kaldırılan tüm yinelenen öğeler ile yeni bir koleksiyon sağlayan tarafından bir kümesine nesneler koleksiyonunu dönüştürmek için kullanılır.|  
|[BİRLEŞİM](../../../../../../docs/framework/data/adonet/ef/language-reference/union-entity-sql.md)|İki veya daha fazla sorguların sonuçlarını tek bir koleksiyona birleştirir.|  
  
## <a name="type-operators"></a>Türü işleçleri  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]oluşturulan, sorgulanabilir ve yönetilebilir bir ifade (değer) türüne izin işlemler sağlar. Aşağıdaki tablo türleri ile çalışmak için kullanılan işleçleri listeler.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[ATAMA](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)|Bir veri türünde bir ifadenin diğerine dönüştürür.|  
|[KOLEKSİYONU](../../../../../../docs/framework/data/adonet/ef/language-reference/collection-entity-sql.md)|Kullanılan bir [işlevi](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) varlık türleri veya karmaşık türler koleksiyonu bildirmek için işlemi.|  
|[OLAN &#91; DEĞİL &#93; ,](../../../../../../docs/framework/data/adonet/ef/language-reference/isof-entity-sql.md)|İfade türü belirtilen türe veya onun alt türlerinden birini olup olmadığını belirler.|  
|[OFTYPE](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)|Belirli bir türde bir sorgu ifadesinden nesneler koleksiyonunu döndürür.|  
|[Adlı tür Oluşturucu](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)|Varlık türleri veya karmaşık türler örneklerini oluşturmak için kullanılır.|  
|[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)|Değerler listesinden bir çoklu küme örneği oluşturur.|  
|[SATIR](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)|Bir veya daha fazla değer anonim, yapısal olarak yazılan kayıtları oluşturur.|  
|[KABUL ET](../../../../../../docs/framework/data/adonet/ef/language-reference/treat-entity-sql.md)|Belirli bir temel türdeki bir nesneyi belirtilen türetilen türde bir nesne olarak değerlendirir.|  
  
## <a name="other-operators"></a>Diğer işleçleri  
 Aşağıdaki tablo diğer listeler [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçler.  
  
|İşleç|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|---------|  
|[+ (Dize birleştirme)](../../../../../../docs/framework/data/adonet/ef/language-reference/string-concatenation-entity-sql.md)|Dizelerde birleştirmek için kullanılan [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[. (Üye erişimi)](../../../../../../docs/framework/data/adonet/ef/language-reference/member-access-entity-sql.md)|Bir özellik veya yapısal kavramsal model türünün bir örneği alanının değerini erişmek için kullanılır.|  
|[--(Açıklama)](../../../../../../docs/framework/data/adonet/ef/language-reference/comment-entity-sql.md)|Dahil [!INCLUDE[esql](../../../../../../includes/esql-md.md)] açıklamaları.|  
|[İŞLEVİ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)|Bir varlık SQL sorgusunda yürütülebilir bir satır içi işlev tanımlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Varlık SQL dili](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
