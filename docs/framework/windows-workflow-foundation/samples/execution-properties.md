---
title: "Yürütme özellikleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fed33544654e6929997567198c0f07346e715d1e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="execution-properties"></a>Yürütme özellikleri
Bu örnek tanımlamak ve bir yürütme özelliği özel bir aktivite içinde nasıl kullanılacağını göstermektedir. Bu örnekte, yürütme özelliği konsolun ön plan rengini belirler. Örnek iş akışı yürütme nasıl farklı mantıksal yollar gösterir (biri dallandırır bir <xref:System.Activities.Statements.Parallel> etkinlik) farklı konsol renkleri etkinliklerin araya eklemeli yürütülmesini rağmen koruyabilirsiniz (dalları arasında <xref:System.Activities.Statements.Parallel> etkinlik).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örnek çalıştırın  
  
1.  ExecutionProperties.sln örnek çözümü açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    > [!NOTE]
    >  Kullanılan özel etkinlikler çözümü aynı zamanda oluşturulması gerekir çünkü çözüm oluşturulmadan önce ThreeColors.xaml görüntüleme bir hata görüntüler.  
  
2.  Derleme ve çözümü çalıştırın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`