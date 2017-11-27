---
title: "Nasıl yapılır: TileBrush için Döşeme Boyutunu Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 484419c05c3d607212ea6d565777cf49cbfdbc19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="64e01-102">Nasıl yapılır: TileBrush için Döşeme Boyutunu Ayarlama</span><span class="sxs-lookup"><span data-stu-id="64e01-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="64e01-103">Bu örnek için döşeme boyutunu nasıl ayarlayacağınızı gösterir bir <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="64e01-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="64e01-104">Varsayılan olarak, bir <xref:System.Windows.Media.TileBrush> tamamen boyama alanını dolduracak tek bir döşeme üretir.</span><span class="sxs-lookup"><span data-stu-id="64e01-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="64e01-105">Ayarlayarak bu davranışı geçersiz kılabilirsiniz <xref:System.Windows.Media.TileBrush.Viewport%2A> ve <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="64e01-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="64e01-106"><xref:System.Windows.Media.TileBrush.Viewport%2A> Özelliği için döşeme boyutunu belirtir bir <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="64e01-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="64e01-107">Varsayılan olarak, değeri <xref:System.Windows.Media.TileBrush.Viewport%2A> boyandığında alanının boyutunu göreli bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="64e01-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="64e01-108">Yapmak için <xref:System.Windows.Media.TileBrush.Viewport%2A> özelliğini belirtin, mutlak bir döşeme boyutunu ayarlamak <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> özelliğine <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="64e01-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64e01-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="64e01-109">Example</span></span>  
 <span data-ttu-id="64e01-110">Aşağıdaki örnek kullanan bir <xref:System.Windows.Media.ImageBrush>, bir tür <xref:System.Windows.Media.TileBrush>, bir dikdörtgeni döşeme ile boyamak için.</span><span class="sxs-lookup"><span data-stu-id="64e01-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="64e01-111">Örnek çıktı alanının (dikdörtgen) yüzde 50 yüzde 50 her bölme ayarlar.</span><span class="sxs-lookup"><span data-stu-id="64e01-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="64e01-112">Sonuç olarak, dikdörtgen dört tane yansıması ile boyanır.</span><span class="sxs-lookup"><span data-stu-id="64e01-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="64e01-113">Aşağıdaki çizimde örnek üretir çıkış gösterir.</span><span class="sxs-lookup"><span data-stu-id="64e01-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="64e01-114">![Resim fırçası ile döşeme örneği](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="64e01-114">![Example of tiling with an image brush](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="64e01-115">Sonraki örnekte bir <xref:System.Windows.Media.ImageBrush>, ayarlar, <xref:System.Windows.Media.TileBrush.Viewport%2A> için `0,0,25,25` ve kendi <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> için <xref:System.Windows.Media.BrushMappingMode.Absolute>ve başka bir dikdörtgen boyamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="64e01-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="64e01-116">Sonuç olarak, fırça 25 piksel genişliği ve yüksekliği 25 piksel sahip döşeme üretir.</span><span class="sxs-lookup"><span data-stu-id="64e01-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="64e01-117">Aşağıdaki çizimde örnek üretir çıkış gösterir.</span><span class="sxs-lookup"><span data-stu-id="64e01-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="64e01-118">![A döşeli bir 0,0,0,25,0,25 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="64e01-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="64e01-119">Önceki örneklerde daha büyük bir örneğin parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="64e01-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="64e01-120">Tam bir örnek için bkz: [ImageBrush örneği](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="64e01-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="64e01-121">Bu örnek kullansa <xref:System.Windows.Media.ImageBrush> sınıfı, <xref:System.Windows.Media.TileBrush.Viewport%2A> ve <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> özellikleri aynı şekilde davranır diğer <xref:System.Windows.Media.TileBrush> , yani, nesne için <xref:System.Windows.Media.DrawingBrush> ve <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="64e01-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="64e01-122">Hakkında daha fazla bilgi için <xref:System.Windows.Media.ImageBrush> ve diğer <xref:System.Windows.Media.TileBrush> nesneleri bkz [görüntüleri, çizimler ve görsellerle boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="64e01-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e01-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="64e01-123">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="64e01-124">Görüntüleri, çizimler ve görsellerle boyama</span><span class="sxs-lookup"><span data-stu-id="64e01-124">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="64e01-125">Bir TileBrush farklı döşeme desenleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="64e01-125">Create Different Tile Patterns with a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)