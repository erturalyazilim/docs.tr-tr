---
title: "İleti Aktarımı Hatalarını İşlemek için Teslim Edilemeyen İletiler Sırası Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9e891c6a-d960-45ea-904f-1a00e202d61a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd717b24eaf161145249e175425bd5296f3ef727
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="using-dead-letter-queues-to-handle-message-transfer-failures"></a>İleti Aktarımı Hatalarını İşlemek için Teslim Edilemeyen İletiler Sırası Kullanma
Sıraya alınan iletileri teslim başarısız olabilir. Bu başarısız iletileri teslim edilemeyen sırada kaydedilir. Başarısız teslim nedenlerden ötürü ağ hataları, silinen bir kuyruk, dolu bir sıra, kimlik doğrulama hatası veya zamanında teslim etmek için bir hata neden olabilir.  
  
 Alma işlemini yapan uygulamanın bunları zamanında sırasından okumaz, sıraya alınan iletileri uzun süredir kuyrukta kalabileceği. Bu davranış, zamana duyarlı iletileri için uygun olmayabilir. Zamana duyarlı iletileri gerekir süresi dolmadan önce ne kadar süreyle iletiler kuyrukta uygulanıp uygulanamayacağını gösterir sıraya alınan bağlamasında ayarlanan yaşam süresi (TTL) özelliği için bir zaman sahip. Süresi dolan iletileri sahipsiz sıra adı verilen bir özel sıra için gönderilir. İleti ayrıca bir sahipsiz sıraya diğer nedeniyle, bir sıra kotasını gibi veya kimlik doğrulama hatası nedeniyle beklemeye getirilebilir.  
  
 Genellikle, uygulamaları eski ileti sırası ve hata nedeniyle iletileri okumak için maaş mantığı yazma. Maaş mantığı başarısızlığın nedenini bağlıdır. Örneğin, kimlik doğrulama hatası olması durumunda, iletiyle iliştirilmiş sertifika düzeltin ve iletiyi yeniden gönderin. Hedef sıra kotası üst sınırına ulaşıldığı için teslim başarısız olduysa, kota sorunun çözümlendiğini soluk teslimi yeniden çalıştırmayı deneyin.  
  
 Bu sistemden alınan tüm başarısız iletileri depolandığı bir sistem genelinde sahipsiz sırayı en kuyruk sistemleri var. Message Queuing (MSMQ) iki sistem genelinde sıralarındaki sağlar: işlem sırası ve depolar işlemsel olmayan bir sistem genelinde sahipsiz sıraya teslim edilemedi iletileri depolayan bir işlem sistem genelinde atılacak İşlemsel olmayan bir sıraya teslim edilemedi iletileri. İki istemcileri iki farklı hizmetlere ve bu nedenle farklı sıralarındaki iletileri gönderiyorsanız [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] iletileri bir karışımını sistem sahipsiz sıraya olması mümkündür sonra göndermek için aynı MSMQ hizmeti paylaşıyorsunuz. Bu her zaman en uygun değildir. Bazı durumlarda (örneğin, güvenlik), başka bir istemcinin iletileri teslim edilemeyen kuyruktan okumak için bir istemci istemeyebilirsiniz. Paylaşılan bir sahipsiz sırayı Ayrıca, hangi şekilde basımı karşılamayacak kadar pahalı olabilir sahipsiz sıradaki iletilerin sayısına dayalı olarak gönderilen bir ileti bulmak için sırada göz atmak istemcileri gerektirir. Bu nedenle, içinde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `NetMsmqBinding`, `MsmqIntegrationBinding,` ve üzerinde MSMQ [!INCLUDE[wv](../../../../includes/wv-md.md)] (bazen bir uygulamaya özgü sahipsiz sırayı adlandırılır) özel bir sahipsiz sırayı sağlayın.  
  
 Özel sahipsiz sırayı iletileri göndermek için aynı MSMQ hizmeti paylaşan istemcileri arasında yalıtım sağlar.  
  
 Üzerinde [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ve [!INCLUDE[wxp](../../../../includes/wxp-md.md)], [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tüm kuyruğa alınan istemci uygulamalarının bir sistem genelinde sahipsiz sırayı sağlar. Üzerinde [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] her sıraya alınan istemci uygulaması için eski ileti sırası sağlar.  
  
## <a name="specifying-use-of-the-dead-letter-queue"></a>Sahipsiz Sıra kullanımını belirtme  
 Sahipsiz Sıra gönderen uygulama sıra Yöneticisi'nde ' dir. Süresi dolan veya aktarımı veya teslim başarısız olmuş iletileri depolar.  
  
 Bağlama sahipsiz sırayı özellikleri şunlardır:  
  
-   <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>  
  
-   <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>  
  
## <a name="reading-messages-from-the-dead-letter-queue"></a>İletileri teslim edilemeyen sırasından okuma  
 Sahipsiz sıra dışında iletilerini okuyan bir uygulama benzer bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aşağıdaki küçük farklılıklar dışında bir uygulama sırasından okur hizmeti:  
  
-   Sistem işlem teslim edilemeyen kuyruktan iletileri okumak için Tekdüzen Kaynak Tanımlayıcısı (URI) biçiminde olmalıdır: net.msmq://localhost/system$; DeadXact.  
  
-   Sistem işlem olmayan sahipsiz kuyruktan iletileri okumak için URI biçiminde olmalıdır: net.msmq://localhost/system$; geçersiz.  
  
-   Özel sahipsiz kuyruktan iletileri okumak için URI form: net.msmq://localhost/private/ olmalıdır\<*özel dlq ad*> Burada *özel dlq ad* özel adıdır sahipsiz sıra.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Kuyruklar adres nasıl [hizmet uç noktaları ve kuyruk işleme](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Üzerinde dinleyen bir hizmet alıcı eşleşmeleri adresleri iletideki adresiyle yığında. Adresleri eşleşirse, ileti gönderilir; Aksi durumda, ileti değil gönderilir. Teslim edilemeyen sıradaki iletiler genellikle hizmeti ve eski ileti sırası hizmeti yönlendirildiği bu sorunları sahipsiz sıradan okunurken neden olabilir. Bu nedenle, sahipsiz sırasından okuma hizmetini bir adresi filtresi yüklemelisiniz `ServiceBehavior` alıcıyı bağımsız olarak sıradaki tüm iletileri eşleştirmek için yığın bildirir. Özellikle, eklemelisiniz bir `ServiceBehavior` ile <xref:System.ServiceModel.AddressFilterMode.Any> iletileri teslim edilemeyen sırasından okuma hizmetine parametresi.  
  
## <a name="poison-message-handling-from-the-dead-letter-queue"></a>Zehirli ileti teslim edilemeyen sıradan işleme  
 Zehirli ileti işleme sıralarındaki, bazı koşullar ile kullanılabilir. Alt sıralar sistem sahipsiz sıradan okunurken sistem sıralarından oluşturulamıyor çünkü `ReceiveErrorHandling` ayarlanamıyor `Move`. Not özel sahipsiz kuyruktan okuyorsanız Alt sıralar olabilir ve bu nedenle, `Move` zehir iletisi için geçerli bir eğilimi.  
  
 Zaman `ReceiveErrorHandling` ayarlanır `Reject`, özel sahipsiz sıra zehir iletisi okunurken sistem sahipsiz sıraya konur. Sistem sahipsiz sıradan okuma ise, iletiyi (silinen) bırakılır. MSMQ düşme bir sistem sahipsiz kuyruktan Reddet (ileti temizler).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, sahipsiz sıra oluşturma ve onu süresi dolan iletileri işlemek için nasıl kullanılacağını gösterir. Örnek örnekte dayalı [nasıl yapılır: WCF uç noktaları Exchange sıraya alınan iletileri](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md). Aşağıdaki örnek, sipariş işleme her uygulama için bir sahipsiz sırayı kullanan hizmet için istemci kodu yazma gösterilmektedir. Bu örnek ayrıca sahipsiz sıraya alınan iletileri işlemek nasıl gösterir.  
  
 Her uygulama için sahipsiz sırayı belirten bir istemci için kod aşağıda verilmiştir.  
  
 [!code-csharp[S_DeadLetter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/client.cs#1)]
 [!code-vb[S_DeadLetter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/client.vb#1)]  
  
 İstemci yapılandırma dosyası için kod aşağıda verilmiştir.  
  
  
  
 Sahipsiz sıraya alınan iletileri işleme bir hizmet için kod aşağıda verilmiştir.  
  
 [!code-csharp[S_DeadLetter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/dlservice.cs#3)]
 [!code-vb[S_DeadLetter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/dlservice.vb#3)]  
  
 Sahipsiz Sıra hizmet yapılandırma dosyası için kod aşağıda verilmiştir.  
  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kuyruklar genel bakış](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [Nasıl yapılır: WCF uç noktaları iletileri kuyruğa alınan](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [Zehirli ileti işleme](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
