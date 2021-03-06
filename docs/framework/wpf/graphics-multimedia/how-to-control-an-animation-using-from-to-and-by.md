---
title: "Nasıl yapılır: Bir Animasyonu Gelen, İçin ve Göre Kullanarak Denetleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Nasıl yapılır: Bir Animasyonu Gelen, İçin ve Göre Kullanarak Denetleme
"From/To/By" veya "temel animasyon" iki hedef değer arasında bir geçiş oluşturur (bkz [animasyon genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) giriş animasyon farklı türleri için). Temel animasyonun hedef değerlerini ayarlamak için kullanın, <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri.  Aşağıdaki tabloda özetlenmiştir nasıl <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri kullanılabilir birlikte veya ayrı ayrı animasyonun hedef değerlerini belirlemek için.  
  
|Belirtilen özellikleri|Bunun sonucunda oluşan davranışı|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliğini özelliğin temel değerini veya önceki bir animasyon animasyonun önceki animasyonun nasıl yapılandırıldığına bağlı olarak değeri, çıktı.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>ve<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliği tarafından belirtilen değere <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>ve<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|İle belirtilen değer animasyon ilerler <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> özelliğini toplamı tarafından belirtilen değere <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özellikleri.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Animasyonun ilerler animasyonlu özelliğin temel değerinden veya önceki bir animasyon değeri tarafından belirtilen değere çıkışını <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Bu değer ve tarafından belirtilen değeri toplamı değerine özelliğin temel değerini animasyon ilerler veya önceki animasyonun çıktı <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> özelliği.|  
  
> [!NOTE]
>  Her ikisini birden ayarlamayın <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> özelliği ve <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> aynı animasyon özelliği.  
  
 İkiden fazla hedef değerleri arasında hareketli hale getirmeyi veya diğer ilişkilendirme yöntemlerini kullanmak üzere bir anahtar çerçevesi animasyonu kullanın. Bkz: [anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) daha fazla bilgi için.  
  
 Tek bir özellik için birden çok animasyon uygulama hakkında daha fazla bilgi için bkz: [anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Aşağıdaki örnek, ayarı farklı etkilerini gösterir <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, ve <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> animasyonları özellikleri.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Animasyon genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Öğesinden, için ve animasyon hedef değerleri örneği](http://go.microsoft.com/fwlink/?LinkID=159988)
