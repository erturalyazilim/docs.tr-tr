---
title: "Ana bilgisayar kilit yenileme süresi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48a5d2e1d8c5381f322ea1b6ffc9022853683efc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="host-lock-renewal-period"></a>Ana bilgisayar kilit yenileme süresi
**Konak kilit yenileme süresini** özelliği SQL iş akışı örneği deposunun konak içinde bir iş akışı örneği üzerinde kendi kilit yeniler süre belirtmenize olanak sağlar. Kilidi geçerli kaldığı için ana bilgisayar kilit yenileme süresini + 30 saniye. Kilidi yenilemek ana bilgisayar başarısız olursa (diğer bir deyişle, kira süresini) kilidi bu süre içinde süresi dolar ve Kalıcılık sağlayıcı örneği kilidini açar. Bu özellik için değer "ss: dd:" biçiminde TimeSpan türüdür. Değer izin verilen minimum "00: 00:01" (1 saniye). Bu özelliğin varsayılan değeri "00: 00:30" (30 saniye).  
  
 Bu özellik, sahip bir iş akışı hizmeti örneği kilidini açabilir önce bir iş akışı hizmeti ana bilgisayarı nerede başarısız senaryolarda önemlidir. Böylece aynı bilgisayarda veya bir sunucu grubundaki başka bir bilgisayarda çalışan başka bir iş akışı hizmeti ana bilgisayarı elde edebilirsiniz kilit süresi dolduktan sonra bu senaryoda, kilit Kalıcılık veritabanındaki iş akışı hizmet örneği üzerinde Kalıcılık sağlayıcı tarafından kaldırılır Kilitle ve iş akışı hizmeti örneğinin son kalıcı durumunu kendi yürütülmesini Sürdür belleğe yükler.  
  
 Bu özellik için daha yüksek bir değere ayarlamak, iş akışı uzun süre Kalıcılık veritabanında kilitlenmesine hizmet örnekleri neden olur ve bu nedenle örnek kurtarma son Kalıcılık noktasından geciktirir. Bu özellik için kısa bir süre ayarlama başarısız iş akışı hizmeti örneği hızlı bir şekilde almak için iş akışı hizmeti ana bilgisayarı yeni bir örneğini neden olur, ancak iş akışı hizmeti ana bilgisayarı ve SQL Server veritabanı için iş yükü artışa neden olur.  
  
 SQL iş akışı örneği deposuna düzenli aralıklarla uyanır ve onlar üzerinde süresi dolmuş kilitleri örnekleriyle algılar iç bir görev çalıştırır. Süresi dolan kilitleri örnekleriyle bulduğunda, böylece bir iş akışı ana almak ve bu örnekleri çalıştırmak RunnableInstances tabloda örnekleri yerleştirir.
