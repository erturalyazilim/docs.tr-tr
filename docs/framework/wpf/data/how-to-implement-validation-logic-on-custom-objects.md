---
title: "Nasıl yapılır: Özel Nesneler Üzerinde Doğrulama Mantığı Uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41a995223742e21f3bcc32d23c21882ac7eef465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Nasıl yapılır: Özel Nesneler Üzerinde Doğrulama Mantığı Uygulama
Bu örnek, özel bir nesne üzerinde doğrulama mantığı uygulamak ve onu bağladıktan gösterilmektedir.  
  
## <a name="example"></a>Örnek  
 Kaynak nesne uyguluyorsa iş katmanında doğrulama mantığını sağlayabilirsiniz <xref:System.ComponentModel.IDataErrorInfo>, aşağıdaki örnekte olduğu gibi:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Aşağıdaki örnekte, metin kutusunun metin özelliği bağlar `Age` özelliği `Person` verilen kaynak bildirimine bağlamak için kullanılabilir hale nesne `x:Key``data`. <xref:System.Windows.Controls.DataErrorValidationRule> Tarafından gerçekleştirilen doğrulama hatalarını denetler <xref:System.ComponentModel.IDataErrorInfo> uygulaması.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Alternatif olarak, kullanmak yerine <xref:System.Windows.Controls.DataErrorValidationRule>, ayarlayabileceğiniz <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> özelliğine `true`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [Bağlama doğrulaması Uygula](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
