---
title: "Nasıl yapılır: Göreli Değerler Kullanarak Dönüşümün Kaynağını Belirtme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec61fdedc78b785dccf2c235cd17fd20b6d5abc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Nasıl yapılır: Göreli Değerler Kullanarak Dönüşümün Kaynağını Belirtme
Bu örnek göreli değerlerin kökenini belirlemek için nasıl kullanılacağını gösterir bir <xref:System.Windows.UIElement.RenderTransform%2A> için uygulanan bir <xref:System.Windows.FrameworkElement>.  
  
 Ne zaman döndürme, ölçeklendirme veya eğme bir <xref:System.Windows.FrameworkElement> kullanarak <xref:System.Windows.UIElement.RenderTransform%2A> özelliği, varsayılan ayar, öğenin sol üst köşesindeki dönüştürme uygulanır. Döndürme, ölçeklendirme veya öğenin Merkezi'nden eğme istiyorsanız, öğenin merkezine dönüştürme merkezi ayarlayarak dengeleyebilirsiniz. Ancak, bu çözüm öğe boyutunu bilmeniz gerekir. Ayarlamak için öğenin merkezine dönüşüm uygulamanın daha kolay bir yoludur kendi <xref:System.Windows.UIElement.RenderTransformOrigin%2A> özelliğine (0,5, 0,5) dönüştürme üzerinde merkez değerini ayarlamak yerine.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir <xref:System.Windows.Media.RotateTransform> döndürmek için bir <xref:System.Windows.Controls.Button> 45 derece saat yönünde. Örnek bir merkezi belirtmediğinden düğmesi, sol üst köşe noktası hakkında (0, 0) döndürür. <xref:System.Windows.Media.RotateTransform> Uygulanan <xref:System.Windows.UIElement.RenderTransform%2A> özelliği.  
  
 Aşağıdaki çizimde, izleyen örnek için dönüşüm sonucunu gösterir.  
  
 ![RenderTransform kullanılarak dönüştürülen düğme](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
RenderTransform özelliğini kullanarak 45 derece saat yönünde bir döndürme  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Aşağıdaki örnekte de kullanan bir <xref:System.Windows.Media.RotateTransform> döndürmek için bir <xref:System.Windows.Controls.Button> 45 derece saat yönünde; ancak, bu örnek ayarlar <xref:System.Windows.UIElement.RenderTransformOrigin%2A> için düğmesinin (0,5, 0,5). Sonuç olarak, döndürme, sol üst köşe yerine düğmenin merkezine uygulanır.  
  
 Aşağıdaki çizimde, izleyen örnek için dönüşüm sonucunu gösterir.  
  
 ![Ortasından dönüştürülen düğme](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
RenderTransformOrigin'i ile RenderTransform özelliğini kullanarak 45 derece döndürme (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Dönüştürme hakkında daha fazla bilgi için <xref:System.Windows.FrameworkElement> nesneleri bkz [dönüştüren genel bakış](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Media.Transform>  
 [Dönüşümler genel bakış](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
