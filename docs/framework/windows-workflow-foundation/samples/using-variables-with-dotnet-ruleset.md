---
title: ".NET Framework 3.5 Ruleset ile değişkenlerini kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5d0be8f8d88581e889ea2a659037f424a9a1c89
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>.NET Framework 3.5 Ruleset ile değişkenlerini kullanma
Bu örneği kullanan bir iş akışının nasıl oluşturulacağını gösterir <xref:System.Activities.Statements.Interop> yazılmış özel bir aktivite tümleştirmek için etkinlik [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] İlkesi ve kuralları kullanır. İş akışı değişkenleri özel etkinlik tarafından kullanıma sunulan bağımlılık özellikleri bağlayarak verileri özel etkinlik geçirir.  
  
## <a name="sample-walkthrough"></a>Örnek gözden geçirme  
  
#### <a name="to-examine-travelrulelibrary"></a>TravelRuleLibrary incelemek için  
  
1.  Kullanarak [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], InteropWith35RuleSet.sln çözüm dosyasını açın.  
  
2.  İş Akışı Tasarımcısı'nda TravelRuleSet.cs açın.  
  
     İçeren özel bir sıralı etkinlik bir <xref:System.Workflow.Activities.PolicyActivity> görüntülenir.  
  
3.  Kuralları incelemek için DiscountPolicy İlkesi etkinliği çift tıklatın.  
  
     Kuralları göstermek için kural Düzenleyicisi açılır.  
  
4.  Sağ tıklayın `DiscountPolicy` seçip **görünümü kodu** seçeneği C# kodu etkinliğin yanında kodu inceleyin.  
  
     Bağımlılık özelliği ayarını gözlemlemek `DiscountLevel`. Bu bağımsız değişkenler için eşdeğerdir [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]bağımsız değişkenleri, görmek [değişkenleri ve bağımsız değişkenler](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Bu kullanan bir sıralı iş akışı projedir <xref:System.Activities.Statements.Interop> oluşturulan özel kural kümesi ile tümleştirmek için etkinlik `TravelRuleLibrary` projesi. Değişkenleri, en üst düzey oluşturulur <xref:System.Activities.Statements.Sequence> etkinlik. <xref:System.Activities.Statements.Interop> Etkinlik ile tümleştirmek için kullanılan `TravelRuleSet` etkinlik. Üzerinde bildirilen değişkenlerin <xref:System.Activities.Statements.Sequence> bağımlılık özelliği bağlamak için kullanılır.  
  
## <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], InteropWith35RuleSet.sln çözüm dosyasını açın.  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Çözümü çalıştırmak için CTRL + F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`