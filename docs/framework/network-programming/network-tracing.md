---
title: ".NET Framework'te Ağ İzleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: faeb028733ef008f3862e95fde0412f51bf7d1c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="network-tracing-in-the-net-framework"></a>.NET Framework'te Ağ İzleme
.NET Framework'te ağ izleme, yönetilen uygulama tarafından oluşturulan yöntem çağrıları ve ağ trafiğiyle ilgili bilgilere erişim sağlar. Bu özellik, geliştirilen uygulamalarda hata ayıklanırken ve dağıtılan uygulamalar analiz edilirken yararlı olur. Ağ izleme tarafından sağlanan çıkış, geliştirme zamanı ve üretim ortamında farklı kullanım senaryolarını destekleyecek şekilde özelleştirilebilir.  
  
 .NET Framework'te ağ izlemeyi etkinleştirmek üzere izleme çıkışı için bir hedef seçmeniz ve ağ izleme yapılandırma ayarlarını uygulamaya ve makine yapılandırma dosyasına eklemeniz gerekir. Yapılandırma dosyaları ve bunların nasıl kullanıldığı açıklamaları için bkz: [yapılandırma dosyalarını](../../../docs/framework/configure-apps/index.md). Ağ izlemeyi etkinleştirme hakkında daha fazla bilgi için bkz: [etkinleştirme ağ izleme](../../../docs/framework/network-programming/enabling-network-tracing.md). Yapılandırma dosyası eklemek için gereken ayarları hakkında daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma ağ izleme](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 İzleme etkinleştirildiğinde tarafından çıkış izleme bilgileri yakalamak için **System.Net** sınıfları. İzleme bilgileri oluşturan ağ sınıfı üyelerinin .NET Framework sınıf kitaplığı belgelerindeki Açıklamalar bölümünde aşağıdaki not vardır:  
  
> [!NOTE]
>  Uygulamanızda ağ izlemeyi etkinleştirdiğinizde, bu üye izleme bilgilerini çıkarır. Daha fazla bilgi için bkz. Ağ İzleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ağ izlemeyi etkinleştirme](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [Nasıl yapılır: ağ İzlemeyi Yapılandır](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [Ağ izleme yorumlama](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [İzleme ve izleme giriş](http://msdn.microsoft.com/en-us/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
