---
title: "İş Akışında Sözleşmeleri Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c13da32e304e54d1826c6dd4ad83d5fbb17702a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="using-contracts-in-workflow"></a>İş Akışında Sözleşmeleri Kullanma
Bir hizmet uygularken, bir dizi hizmet ve gönderen ve alan verileri açıklayan sözleşme tanımlayın. Verileri veri sözleşmeleri ve ileti sözleşmeleri temsil edilir; her ikisi de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve iş akışı Hizmetleri veri sözleşmesi ve ileti sözleşmesi tanımlarını hizmeti açıklamaları bir parçası olarak kullanın. Hizmet, hizmet işlemleri tanımlamak için meta verileri (WSDL biçiminde) gösterir. İçinde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], hizmet sözleşmeleri ve işlem sözleşmeleri hizmeti ve desteklediği işlemleri tanımlayın. Ancak, bir iş akışı hizmetinde bu sözleşmeleri iş sürecinin parçası olan; Bunlar, meta verilerde sözleşme çıkarım adlı bir işlem tarafından sunulur.  
  
## <a name="contract-inference"></a>Sözleşme çıkarımı  
 Bir iş akışı hizmeti kullanarak barındırıldığında <xref:System.ServiceModel.Activities.WorkflowServiceHost>, iş akışı tanımı incelenir ve bir sözleşme Mesajlaşma etkinlikleriyle iş akışında bulunan kümesini temel alınarak oluşturulur. Özellikle aşağıdaki etkinlikleri ve özellikleri sözleşme oluşturmak için kullanılır:  
  
 <xref:System.ServiceModel.Activities.Receive>Etkinlik  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <xref:System.ServiceModel.Activities.SendReply>Etkinlik  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>Etkinlik  
  
 Sözleşme çıkarım nihai sonucu WCF hizmeti ve işlem sözleşmeleri aynı veri yapılarını kullanarak hizmet açıklamasıdır. Bu bilgiler daha sonra WSDL için iş akışı hizmeti kullanıma sunmak için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş akışı Hizmetleri](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Mesajlaşma etkinlikleri](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [Nasıl yapılır: Mesajlaşma etkinlikleriyle iş akışı hizmeti oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [Nasıl yapılır: varolan bir hizmet sözleşmesini tüketen bir iş akışı hizmeti oluşturma](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
