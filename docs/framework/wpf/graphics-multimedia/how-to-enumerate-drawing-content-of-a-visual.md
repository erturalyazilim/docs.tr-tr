---
title: "Nasıl yapılır: Görselin Çizim İçeriğini Numaralandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e498bc8e425198e479d7ce0b2328e0efa3ede70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="c328e-102">Nasıl yapılır: Görselin Çizim İçeriğini Numaralandırma</span><span class="sxs-lookup"><span data-stu-id="c328e-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="c328e-103"><xref:System.Windows.Media.Drawing> Nesne içeriğini numaralandırmak için nesne modeli sağlar bir <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="c328e-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c328e-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="c328e-104">Example</span></span>  
 <span data-ttu-id="c328e-105">Aşağıdaki örnek kullanır <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> alma yöntemi <xref:System.Windows.Media.DrawingGroup> değerini bir <xref:System.Windows.Media.Visual> ve onu numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="c328e-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c328e-106">Görsel içeriği numaralandırılırken alma <xref:System.Windows.Media.Drawing> nesneleri ve vektör grafikleri yönerge listesi olarak işleyici verinin temeldeki gösterimini değil.</span><span class="sxs-lookup"><span data-stu-id="c328e-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="c328e-107">Daha fazla bilgi için bkz: [WPF Grafik işleme genel bakış](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c328e-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="c328e-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c328e-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="c328e-109">Çizim nesnelerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="c328e-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="c328e-110">WPF Grafik işleme genel bakış</span><span class="sxs-lookup"><span data-stu-id="c328e-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)