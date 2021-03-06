---
title: "XAMLX dayanıklı gecikmesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7396c5ca2119dcf096036695233d5c89a3f014f7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay-in-xamlx"></a>XAMLX dayanıklı gecikmesi
Bu örnek, sağlam bir aygıt için iş akışı sırasında gecikme devam ederse gecikme dayanıklı bir gecikme kullanımı gösterilmiştir.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Tartışma  
 Örnek iş akışı tarafından bir gecikme ayrılmış iki iletileri yerel bir dosyaya içerir. Gecikme tetiklendiğinde, iş akışı kaldırılır ve iş akışı örneği deposundaki 5 bellekte yeniden yükleniyor önce saniye bekler.  
  
 İçinde barındırılan bir iş akışı hizmeti .xamlx dosyasıdır [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]bir iş akışı hizmeti ana kullanan Cassini iş akışı kullanır.  
  
 İş akışı barındırma ek olarak, iş akışı hizmeti ana bilgisayarı iş akışı örnekleri yükleme ve bunları yüklemeyi kaldırma yönetir. Örneği başlatmak için [!INCLUDE[wf](../../../../includes/wf-md.md)] tanımı (iş akışı hizmeti ana bilgisayar üzerinde) ayarlamak için bir ileti gönderen istemci <xref:System.ServiceModel.Activities.Receive> etkinliği iş akışı. Bu <xref:System.ServiceModel.Activities.Receive> sahip kendi <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> özelliğini `true`, iletiyi aldıktan sonra iş akışının yeni bir örneğini oluşturmak üzere etkinleştirme.  
  
 Başlatma sırasında bir kaldırma örneği davranış altında kalıcı deponun (veritabanı) örneğini kaldırın iş akışı hizmeti ana bilgisayarı belirtir yapılandırma dosyasının eklenir. Bu örnek için (gecikme tetiklendiğinde) iş akışı boşta göründükten hemen sonra örneğini kaldırır.  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  Açık bir [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] komut istemi.  
  
2.  DurableDelayXamlx\CS klasöre gidin.  
  
3.  Setup.cmd çalıştırın.  
  
4.  Çalıştırma [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] yönetici olarak.  
  
5.  DurableDelayXamlx.sln çözüm dosyasını açın.  
  
6.  İçinde **Çözüm Gezgini**, çözüme sağ tıklayın ve seçin **özellikleri**.  
  
7.  Seçin **birden fazla başlangıç projesi** ve her iki proje kümesine **Başlat**.  
  
8.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
9. Çözümü çalıştırmak için CTRL + F5 tuşuna basın.  
  
#### <a name="to-uninstall-this-sample"></a>Bu örnek kaldırmak için  
  
1.  Açık bir [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] komut istemi.  
  
2.  DurableDelayXamlx\CS klasöre gidin.  
  
3.  CleanUp.cmd çalıştırın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
