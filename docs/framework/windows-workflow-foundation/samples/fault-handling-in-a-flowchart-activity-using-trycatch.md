---
title: "TryCatch kullanarak akış etkinliğinde işleme hatası"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d8bccc1b9505f685fd4e358216e76c22ec751e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>TryCatch kullanarak akış etkinliğinde işleme hatası
Bu örnek göstermektedir nasıl <xref:System.Activities.Statements.TryCatch> etkinlik karmaşık denetim akışı etkinliği içinde kullanılabilir.  
  
 Bu örnekte, bir promosyon kodu ve alt sayısını değişkenleri olarak geçirilir bir <xref:System.Activities.Statements.Flowchart> promosyon kodu karşılık gelen formül temelinde bir hesaplar etkinlik. Örnek kesinlik temelli kodu ve iş akışı Tasarımcısı sürümlerini örnek içerir.  
  
 Aşağıdaki tabloda değişkenleri ayrıntıları `CreateFlowchartWithFaults` etkinlik.  
  
|Parametreler|Açıklama|  
|----------------|-----------------|  
|promoCode|Promosyon kodu. Türü: dize<br /><br /> Parantez içindeki açıklamasıyla olası değerler:<br /><br /> -Tek (tek)<br />-MNK (Evli ile Çocuğunuz yok.)<br />-MWK (Evli çocuklar ile.)|  
|numKids|Alt öğe sayısı. Tür: int|  
  
 `CreateFlowchartWithFaults` Etkinliği kullanan bir <xref:System.Activities.Statements.FlowSwitch%601> anahtarlarını etkinlik `promoCode` bağımsız değişkeni ve aşağıdaki formülü kullanarak hesaplar.  
  
|Değeri`promoCode`|İndirim (%)|  
|--------------------------|--------------------|  
|Tek|10|  
|MNK|15|  
|MWK|15 + (1-1 /`numberOfKids`)\*10 **Not:** potansiyel olarak, bu hesaplama atabilirsiniz bir <xref:System.DivideByZeroException>. İndirim hesaplama, bu nedenle, kaydırılan bir <xref:System.Activities.Statements.TryCatch> yakalar etkinlik <xref:System.DivideByZeroException> özel durumu ve indirim sıfır olarak ayarlar.|  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], FlowchartWithFaultHandling.sln çözüm dosyasını açın.  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Çözümü çalıştırmak için F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, bilgisayarınızda yüklü. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi iş akışları](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [Özel durumlar](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
