---
title: "&lt;eş&gt; &lt;sertifikası&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8bf8cb80201f2501fb60df7c9abb5039d688dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a>&lt;eş&gt; &lt;sertifikası&gt;
Bir eş tarafından kullanılan bir sertifika belirtir.  
  
 \<Sistem. ServiceModel >  
\<davranışları >  
\<serviceBehaviors >  
\<davranışı >  
\<serviceCredentials >  
\<Eş >  
\<Sertifika >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`findValue`|X.509 sertifika deposunda arama için değer içeren bir dize. Özniteliğinde bulunan türü belirtilen gereksinimleri karşılaması gerekir `x509FindType`. Varsayılan boş bir dizedir.|  
|`storeLocation`|İstemcinin karşı eşin sertifikasını doğrulamak için kullandığı X.509 sertifika depolama konumunu belirtir. Geçerli değerler şunlardır:<br /><br /> -LocalMachine: Yerel Makine sertifika deposuna.<br />-Currentuser'a: sertifika deposuna geçerli kullanıcıya atanmış.<br /><br /> LocalMachine varsayılandır.|  
|`storeName`|Açmak için X.509 Sertifika deposu adını belirtir. Geçerli değerler şunlardır:<br /><br /> -Adres Defteri: Diğer kullanıcılar sertifika deposu.<br />-AuthRoot: sertifika deposunu üçüncü taraf sertifika yetkilileri (CA'lar) için.<br />-CertificateAuthority: Ara sertifika yetkilileri (CA) sertifika deposu.<br />-İzin verilmeyen: mağaza iptal edilen sertifikaları için sertifika.<br />-My: Sertifika deposunda kişisel sertifikalar için.<br />-Kök: Güvenilen kök sertifika yetkilileri (CA'lar) sertifika deposu.<br />-TrustedPeople: Doğrudan-güvenilir kişiler ve kaynaklar sertifika deposu.<br />-TrustedPublisher: Doğrudan-Güvenilen Yayımcılar sertifika deposu.<br /><br /> Varsayılan değer My.|  
|`X509FindType`|Yürütülecek X.509 arama türünü tanımlar. Geçerli değerler şunlardır:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> İçinde yer alan türü `findValue` özniteliği belirtilen gereksinimleri karşılaması gerekir `X509FindType`.<br /><br /> FindBySubjectDistinguishedName varsayılan değerdir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Eş >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Eş düğüm için geçerli kimlik bilgilerini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapılandırma öğesi içeren bir `X509Certificate2` eş kafes Komşuları doğrulanırken kullanılan örnek.  
  
 Eşler arası programlama hakkında daha fazla bilgi için bkz: [eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Sertifikalar ile çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Eş kanal ileti kimlik doğrulaması](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Eş kanal özel kimlik doğrulama](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Eş kanalı uygulamalarını güvenli hale getirme](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Hizmetler ve istemcileri güvenli hale getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
