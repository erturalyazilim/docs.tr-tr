---
title: "Windows Communication Foundation Örnekleri için Bir Kerelik Kurulum Prosedürü"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
caps.latest.revision: "83"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b699a9af286287f1cdd1aa224afd3f8c41dd90d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Windows Communication Foundation Örnekleri için Bir Kerelik Kurulum Prosedürü
Çoğu [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] örnekleri Internet Information Services (IIS) barındırılan ve bir ortak sanal dizinden çalıştırın. Bu bir kerelik Kurulum prosedürü disk üzerinde bir klasör oluşturur; Ayrıca IIS adlı bir sanal dizin ekler **ServiceModelSamples**.  
  
 **ServiceModelSamples** sanal dizini oluşturmak ve bir IIS tarafından barındırılan hizmeti kullanan tüm örnekleri çalıştırmak için kullanılır. Bu örnekleri çalıştırmak için gereken tek sanal dizinidir. Örnek oluşturma bu sanal dizin önceden dağıtılmış bir hizmeti değiştirir; yalnızca en son oluşturulan örnek, dağıtılan ve bu sanal dizin kullanılabilir olacaktır.  
  
> [!NOTE]
>  Tüm komutlar yerel yönetici hesabı altında çalışmalıdır. Windows 7, kullanıyorsanız [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], veya Windows Server 2008 R2, ayrıca çalıştırmanız gerekir komut isteminde yükseltilmiş ayrıcalıklara sahip. Bunu yapmak için komut istemi simgesine sağ tıklayın ve ardından **yönetici olarak çalıştır**. Bu konudaki tüm komutlar uygun yolu ayarlara sahip bir komut istemi çalıştırmanız gerekir.  Bunu sağlamak için en kolay yolu, Visual Studio komut istemi kullanmaktır. Bu İstemi'ni açmak için **Başlat**seçin **tüm programlar**, aşağı kaydırarak **Visual Studio 2010**seçin **Visual Studio Araçları**, sağ **Visual Studio komut istemi (2010)**ve ardından **yönetici olarak çalıştır**. Yüklü Visual Studio Express sürümleri biri varsa, bu komut istemi kullanılabilir değil ve sistem yoluna "C:\Windows\Microsoft.Net\Framework\v4.0" eklemeniz gerekir.  
  
### <a name="one-time-setup-procedure-for-wcf-samples"></a>WCF örnekleri için bir kerelik Kurulum prosedürü  
  
1.  Emin [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ayarlanır. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]nasıl ayarlandığı [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], bkz: [Internet Information Service barındırma yönergeleri](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).  
  
2.  Emin [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] yüklenir. Aşağıdaki v4.0 için dizin (veya üstü) arama: **\Windows\Microsoft.NET\Framework**  
  
3.  Varsa [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] yüklü değil ve işletim sisteminizi Windows Server 2008 SP2 değil ya da yüklemeyi daha sonra [düzeltme 251798](http://go.microsoft.com/fwlink/?LinkId=184693).  
  
4.  Aşağıdaki komutları çalıştırın. Neden bu komutları çalıştırmanız gerekir hakkında daha fazla bilgi için bkz: [IIS barındırılan hizmet başarısız](http://msdn.microsoft.com/en-us/ee5499fc-1b10-4cda-a9b1-13dba70f05f8).  
  
    > [!WARNING]
    >  IIS yeniden yüklenirse, aşağıdaki komutları yeniden çalıştırılması gerekir.  
  
    ```  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r  
    ```  
  
    > [!WARNING]
    >  Komutunu çalıştırarak `aspnet_regiis –i –enable` varsayılan uygulama havuzunu kullanarak çalışmasını sağlamak [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], aynı bilgisayardaki diğer uygulamalar için uyumsuzluk sorunları oluşturabilir.  
  
5.  İzleyin [güvenlik duvarı yönergeleri](../../../../docs/framework/wcf/samples/firewall-instructions.md) örnekleri tarafından kullanılan bağlantı noktaları etkinleştirme.  
  
6.  Aşağıdaki varsayılan dizini denetleyin: \<InstallDrive >:**\WF_WCF_Samples**. Bu, örnekler önceden yüklenmiş olan, varsayılan dizindir.  
  
7.  Örnekler yüklü değilse, bunları örnekleri karşıdan yükleme konumu yükleyin [Visual C#](http://go.microsoft.com/fwlink/?LinkId=190939) veya [Visual Basic](http://go.microsoft.com/fwlink/?LinkID=193373).  
  
8.  Örnekler yükledikten sonra gidin: \<InstallDrive >:**\WF_WCF_Samples\WCF\Setup\\**  
  
9. Çalıştırma **Setupvroot.bat** toplu iş dosyası. Aşağıdaki adımlar gerçekleştirilir:  
  
    -   Bir sanal dizin ServiceModelSamples adlı IIS'de oluşturulur.  
  
    -   Yeni disk dizinler adlandırılmış %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples ve % SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin oluşturulur.  
  
     Bu dizinler el ile ayarlamak tercih ederseniz, bkz. [sanal dizin ayarlama yönergeleri](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md). Bu adımda yapılan tüm değişiklikleri geri almak için örnekler kullanmayı bitirdikten sonra cleanupvroot.bat çalıştırın.  
  
    > [!NOTE]
    >  Cleanupvroot.bat çalıştırmadığınız sürece bir bilgisayarda, bu yordam yalnızca bir kez gerçekleştirilmesi gerekir.  
  
10. %SystemDrive%\inetpub\wwwroot altında örnekler ve ağ hizmeti kullanıcı oluşturmakta olduğunuz hesabı değiştirmek için izni vermesi gerekir. Yapı sırasında bazı Web barındırılan örnekleri yukarıda belirtilen konuma derlenmiş ikili dosyaları kopyalamak deneyebilir ve uygun izinleri ayarlamadıysanız derleme kesilir. Alternatif olarak, izinleri olan ve SDK komut istemi veya Visual Studio komut istemi (2012) yönetici olarak çalıştır gibi bırakın veya için örnekler yapı içinde [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]de yönetici olarak çalıştırın.  
  
    > [!NOTE]
    >  Bu adım tamamlanmazsa, IIS tarafından barındırılan tüm örnekleri oluşturma sırasında başarısız olur. Doğru izinler veya SDK komut istemi ve Visual Studio komut istemi (2012) yönetici olarak çalıştır emin olun.  
  
11. Bilgisayarda C:\logs dizin oluşturun; Bazı örnekler, bekliyor olabilir. Uygun hesap bu klasöre yazma erişim olduğundan emin olun. Windows 7 için [!INCLUDE[wv](../../../../includes/wv-md.md)], ve Windows Server 2008 R2, bu hesap, **ağ hizmeti**. İçin [!INCLUDE[lserver](../../../../includes/lserver-md.md)], NT Authority\Network Service hesabıdır. İçin [!INCLUDE[wxp](../../../../includes/wxp-md.md)] ve [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], ASPNET hesabıdır.  
  
12. Setupcerttool.bat dosyasını çalıştırın. Bu dosya bulunan \<InstallPath > \WF_WCF_Samples\WCF\Setup\ klasör.  Bu komut dosyası aşağıdaki görevleri gerçekleştirmeniz gerekecektir:  
  
    -   FindPrivateKey aracı oluşturun.  
  
    -   % ProgramFiles%\ServiceModelSampleTools adlı bir dizin oluşturun.  
  
    -   Yeni FindPrivateKey aracı bu dizine kopyalayın.  
  
     Bu araç, sertifikaları kullanan ve IIS'de barındırılan örnekleri tarafından gereklidir.  
  
    > [!NOTE]
    >  Güvenlik nedeniyle, sanal dizin tanımı ve örneklerle tamamladıktan sonra Cleanupvroot.bat adlı toplu iş dosyasını çalıştırarak Kurulum adımlarında verilen izinleri kaldırmayı unutmayın.  
  
13. Kendi kendine barındırılmaktadır (IIS'de barındırılan değil) örnekleri bilgisayarda dinleme için HTTP adreslerini Kaydet izni gerektirir. Bir HTTP ad alanı ayırmasını izinlerini örneği çalıştırmak için kullanılan kullanıcı hesabından gelir. Varsayılan olarak, yönetici hesapları herhangi bir HTTP adresi kaydetme iznine sahip. Yönetici olmayan hesaplar örnekleri tarafından kullanılan HTTP ad alanları için izin verilmelidir. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]ad alanı ayırmaları yapılandırma hakkında [yapılandırma HTTP ve HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).  
  
14. Bazı örnekler, Message Queuing gerektirir. Bkz: [yükleme Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md) yükleme yönergeleri için.  
  
    > [!NOTE]
    >  Message Queuing gerektiren tüm örnekleri çalıştırmadan önce MSMQ hizmeti Başlat emin olun.  
  
15. Bazı örnekler sertifikaları gerektirir. Bkz: [Internet Information Services (IIS) sunucu sertifikası yükleme yönergeleri](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.
