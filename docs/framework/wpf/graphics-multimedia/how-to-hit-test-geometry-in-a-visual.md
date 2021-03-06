---
title: "Nasıl yapılır: Görselde Tıklama Testi Geometrisi"
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
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ab125fe4031b5408eb202f21ce0fdf4314781f1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Nasıl yapılır: Görselde Tıklama Testi Geometrisi
Bu örnek, bir veya daha fazla oluşan görsel bir nesne üzerinde bir isabet testi yapmak gösterilmiştir <xref:System.Windows.Media.Geometry> nesneleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl alınacağını gösterir <xref:System.Windows.Media.DrawingGroup> kullanan bir görsel nesnesinden <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> yöntemi. İsabet testi her çizimin işlenmiş içeriğinde gerçekleştirilir <xref:System.Windows.Media.DrawingGroup> hangi geometrinin isabet belirlemek için.  
  
> [!NOTE]
>  Çoğu durumda, kullanacağınız <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> bir nokta herhangi bir görsel işlenmiş içeriğiyle kesiştiğinden olup olmadığını belirlemek amacıyla yöntemi.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A> Yöntemdir belirtilen kullanarak isabet testi olanak tanıyan bir aşırı yüklenmiş yöntemin <xref:System.Windows.Point> veya <xref:System.Windows.Media.Geometry>. Geometri vuruş, vuruş dolgu sınırlarının dışına genişletebilirsiniz. Bu durumda, çağrı yapmak isteyebilirsiniz <xref:System.Windows.Media.Geometry.StrokeContains%2A> ek olarak <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Ayrıca, sağlayabilirsiniz bir <xref:System.Windows.Media.ToleranceType> Bezier düzleştirme amacıyla kullanılır.  
  
> [!NOTE]
>  Bu örnek dönüşümleri dikkate almaz veya kırpmayı geometriye uygulanabilir. Ayrıca, doğrudan ilişkili çizimler olmadığından bu örnek bir stilde denetimi ile çalışmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görsel katmanda isabet sınaması](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Geometri parametre olarak kullanan isabet testi](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
