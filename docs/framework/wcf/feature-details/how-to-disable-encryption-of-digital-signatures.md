---
title: "Nasıl yapılır: Dijital İmzaların Şifrelenmesini Devre Dışı Bırakma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce72cb4d71bcc08980104158940a15ea6ecd0c6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Nasıl yapılır: Dijital İmzaların Şifrelenmesini Devre Dışı Bırakma
Varsayılan olarak, bir ileti imzalanır ve imza dijital olarak şifrelenir. Bu örneği ile özel bağlama oluşturarak denetlenir <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> veya <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> ve ayarı `MessageProtectionOrder` özelliği için her iki sınıfın bir <xref:System.ServiceModel.Security.MessageProtectionOrder> numaralandırma değeri. Varsayılan, <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> değeridir. Bu işlem yalnızca imzalama değerinden daha uzun yüzde 30 tüketir ve şifreleme Genel ileti (daha küçük ileti, daha büyük performans etkisi) boyutuna göre. İmza şifrelemeyi devre dışı bırakmak ancak, bir saldırganın iletinin içeriğini tahmin sağlayabilir. Düz metin iletisi imzalı her bölümünün karma kodunu imza öğesi içerdiği için bu mümkün olur. Örneğin, varsayılan ileti gövdesi şifrelenmesine rağmen şifrelenmemiş imza ileti gövdesi şifreleme önce karma kodunu içerir. İmzalanmış ve şifrelenmiş bölümü için olası değerler kümesi küçükse, bir saldırganın karma değer bakarak içeriği türetme olabilir. İmza şifreleme bu saldırı vektörü azaltır.  
  
 Bu nedenle, şifreleme imza yalnızca içeriğin düşük değeri veya olası içerik değerleri büyük ve belirleyici kümesidir ve performans kazancı yukarıda açıklanan saldırı Azaltıcı daha fazla önemlidir devre dışı bırakın.  
  
> [!NOTE]
>  Varsa hiçbir şey şifrelenir iletide, imza öğesi şifrelenmez, bile <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> veya <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> özelliği ayarlanmış <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Bu davranış, hatta sistem tarafından sağlanan bağlamalar ile oluşur; tüm sistem tarafından sağlanan bağlamaları kümesine ileti koruma sırasını sahip `SignBeforeEncryptAndEncryptSignature`. Ancak, Web Hizmetleri Açıklama Dili (WSDL) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oluşturur içermeye devam `<sp:EncryptSignature>` onaylama.  
  
### <a name="to-disable-digital-signing"></a>Dijital imzasını devre dışı bırakmak için  
  
1.  Oluşturma bir <xref:System.ServiceModel.Channels.CustomBinding>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Nasıl yapılır: SecurityBindingElement kullanarak özel bağlama oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Ekleyip ya da bir <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> veya <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> bağlama koleksiyonuna.  
  
3.  Ayarlama <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> özelliğine <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, veya <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> özelliğine <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel bağlamalarla güvenlik özellikleri](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
