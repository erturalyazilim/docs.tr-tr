---
title: Yetkilendirme ve SQL Server'daki izinleri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340405c-91f4-4837-a3cc-a238ee89888a
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0916ca83cae40d1deda2e1126fd7b7ebab46a23c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-and-permissions-in-sql-server"></a>Yetkilendirme ve SQL Server'daki izinleri
Veritabanı nesneleri oluşturduğunuzda, açıkça kullanıcıların erişimine açmak için izinleri vermeniz gerekir. Her güvenliği sağlanabilir nesne izni deyimleri kullanarak bir sorumluyu verilebilir izinlerine sahip değil.  
  
## <a name="the-principle-of-least-privilege"></a>En az ayrıcalık prensibi  
 En az ayrıcalıklı kullanıcı hesabı (LUA) yaklaşımı kullanarak bir uygulama geliştirirken, güvenlik tehditleri tedarikle için savunma, kapsamlı bir strateji önemli bir parçasıdır. LUA yaklaşım, kullanıcıların en az ayrıcalık ilkesini izleyin ve her zaman sınırlı kullanıcı hesaplarıyla oturum sağlar. Yönetim görevleri bölünen sabit sunucu rollerini ve kullanımını kullanarak `sysadmin` sabit sunucu rolünün ciddi bir şekilde kısıtlıdır.  
  
 Her zaman en az ayrıcalık prensibi veritabanı kullanıcılara izin verme izleyin. Belirli bir görevi gerçekleştirmek için en az bir kullanıcı veya rol için gerekli izinleri.  
  
> [!IMPORTANT]
>  Geliştirme ve LUA yaklaşım kullanarak bir uygulamayı test Zorluk derecesini geliştirme sürecinin ekler. Nesneleri oluşturmak ve bir LUA hesabı kullanarak daha Sistem Yöneticisi veya veritabanının sahibi oturum açarken kod yazmak daha kolay olur. Ancak, en az ayrıcalıklı kullanıcılar düzgün çalışması için yükseltilmiş izinleri gerektiren bir uygulama çalıştırmak istediğinizde yüksek ayrıcalıklı bir hesap kullanarak uygulamaların geliştirilmesini işlevsellik etkisini belirsizleştirirseniz. İşlev kaybı yeniden almak için kullanıcılara aşırı izinleri verme, uygulamanızın saldırılara karşı savunmasız bırakabilir. Tasarlama, geliştirme ve LUA hesabıyla oturum açmış uygulamanızı test etme kötü beklenmeyen durumları ve hızlı düzeltme olarak yükseltilmiş ayrıcalıkları vermek için buradaki eðilim ortadan kaldıran Güvenlik planlaması için disiplinli bir yaklaşım uygular. Uygulamanızı Windows kimlik doğrulaması kullanarak dağıtmak için tasarlanmıştır olsa bile test etmek için bir SQL Server oturumu kullanabilirsiniz.  
  
## <a name="role-based-permissions"></a>Role dayalı izinleri  
 Rolleri yerine kullanıcıların izinleri verme, güvenlik yönetimini basitleştirir. Rol atanmış izin kümeleri rolün tüm üyeleri tarafından devralınır. Eklemek veya ayrı izni yeniden için tek tek kullanıcılar için ayarlar olandan kullanıcılar bir rolden kaldırmak daha kolay olur. Rolleri, iç içe konabilir; Ancak, çok fazla iç içe geçme düzeyi performansı düşürebilir. Ayrıca kullanıcı izinleri atamayı basitleştirmek için sabit veritabanı rolleri ekleyebilirsiniz.  
  
 Şema düzeyinde izinleri verebilirsiniz. Kullanıcıların otomatik olarak şemada oluşturulan tüm yeni nesneler izinlerini devralır; Yeni nesneler oluşturuldukça izinler vermeniz gerekmez.  
  
## <a name="permissions-through-procedural-code"></a>Yordam kodu aracılığıyla izinler  
 Veri erişimi modülleri aracılığıyla gibi Kapsüllenen saklı yordamları ve kullanıcı tanımlı işlevler, uygulamanızın etrafında koruma ek katmanı sağlar. Tabloları gibi temel nesneler için izinleri reddetme sırasında yalnızca saklı yordamları ve işlevleri için izinleri vererek veritabanı nesneleri ile doğrudan etkileşim gelen kullanıcıların engelleyebilir. SQL Server bunu sahipliği zincirleme tarafından uygular.  
  
## <a name="permission-statements"></a>İzni deyimleri  
 Üç Transact-SQL izni ifadeler aşağıdaki tabloda açıklanmıştır.  
  
|İzni deyimi|Açıklama|  
|--------------------------|-----------------|  
|VERME|Bir izin verir.|  
|İPTAL ETME|İzni iptal eder. Yeni bir nesne varsayılan durumudur. Bir kullanıcı veya rol iptal izin hala diğer grupların veya rollerin asıl atandığı devralınabilir.|  
|REDDET|REDDETME izin iptal eder; böylece devralınan olamaz. REDDETME önceliklidir tüm izinleri REDDETME nesne sahipleri veya üyeleri için geçerli değildir dışında `sysadmin`. Reddederse, bir nesneye izinlerini `public` reddedilen tüm kullanıcılar ve roller nesne sahipleri dışında rolü ve `sysadmin` üyeleri.|  
  
-   Verme deyimi, bir Grup ya da veritabanı kullanıcılar tarafından devralınan rol izinleri atayabilirsiniz. Ancak, REDDETME deyimi diğer tüm izni deyimleri önceliklidir. Bu nedenle, bir izni reddedildiği bir kullanıcı başka bir rolün devralan olamaz.  
  
> [!NOTE]
>  Üyeleri `sysadmin` sabit sunucu rolü ve nesne sahipleri izinleri reddedildi olamaz.  
  
## <a name="ownership-chains"></a>Sahipliği zincirleri  
 SQL Server, yalnızca izin verilen sorumluların nesneleri erişebilmesini sağlar. Birden çok veritabanı nesnelerini birbirine eriştiğinizde, sırası zinciri olarak bilinir. SQL Server bağlantıları zincirindeki yaptıran, her öğe ayrı olarak erişmekte varsa düğmelerden bu izinleri farklı değerlendirir. Bir nesne bir zincir erişildiğinde, SQL Server (önceki bağlantı zincirindeki) arama nesnenin sahibi nesnenin sahibi ilk karşılaştırır. Her iki nesnenin aynı sahip varsa, referans verilen nesnenin izinlerini denetlenmez. Bir nesne farklı bir sahip olan başka bir nesneyi eriştiğinde, sahipliği zinciri bozuk ve SQL Server arayanın güvenlik bağlamı denetlemelidir.  
  
## <a name="procedural-code-and-ownership-chaining"></a>Yordam kodu ve sahipliği zincirleme  
 Bir kullanıcıya bir tablodan veri seçer bir saklı yordamı yürütme izinleri verilir varsayalım. Saklı yordamı ve tabloyu aynı sahip varsa, kullanıcının tablo üzerinde herhangi bir izin verilmesi gerekmez ve izinleri bile engellenebilir. Ancak, saklı yordamı ve tabloyu farklı sahipleri varsa, SQL Server verilere erişmesine izin vermeden önce kullanıcının izinlerini tablo denetlemelisiniz.  
  
> [!NOTE]
>  Sahiplik zincirleme söz konusu olduğunda dinamik SQL deyimleri geçerli değildir. Bir SQL deyimini yürütür bir yordam çağırma için arayan temel tabloları izinlerini uygulamanızı SQL ekleme saldırısına karşı savunmasız bırakır verilmelidir. SQL Server, kimliğe bürünme ve temel tabloların izin verme gerektirmeyen sertifikaları modüllerle imzalama gibi yeni mekanizmaları sağlar. Bunlar, CLR saklı yordamlar ile de kullanılabilir.  
  
## <a name="external-resources"></a>Dış Kaynaklar  
 Daha fazla bilgi için aşağıdaki kaynaklara bakın.  
  
|Kaynak|Açıklama|  
|--------------|-----------------|  
|[İzinleri](http://msdn.microsoft.com/library/ms191291.aspx) SQL Server Çevrimiçi Kitapları'nda|İzinleri hiyerarşi, Katalog görünümleri ve sabit sunucu ve veritabanı rolleri izinleriyle açıklayan konuları içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET uygulamalarının güvenliğini sağlama](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server'daki uygulama güvenlik senaryoları](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [SQL Server kimlik doğrulaması](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Sunucusu ve SQL Server veritabanı rolleri](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [Sahipliği ve SQL Server'daki kullanıcı şema ayırma](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
