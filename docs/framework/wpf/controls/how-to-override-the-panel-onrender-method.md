---
title: "Nasıl yapılır: Panel OnRender Yöntemini Geçersiz Kılma"
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
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 774c612b09d5cb0ffdf36024a7e6a543f407cf67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="f4af6-102">Nasıl yapılır: Panel OnRender Yöntemini Geçersiz Kılma</span><span class="sxs-lookup"><span data-stu-id="f4af6-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="f4af6-103">Bu örnek nasıl geçersiz kılınacağını gösterir <xref:System.Windows.Controls.Panel.OnRender%2A> yöntemi <xref:System.Windows.Controls.Panel> düzen öğesine özel grafik efektleri eklemek için.</span><span class="sxs-lookup"><span data-stu-id="f4af6-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4af6-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4af6-104">Example</span></span>  
 <span data-ttu-id="f4af6-105">Kullanım <xref:System.Windows.Controls.Panel.OnRender%2A> işlenen panel öğesine grafik efektleri eklemek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="f4af6-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="f4af6-106">Örneğin, özel kenarlık veya arka plan efektleri eklemek için bu yöntemi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4af6-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="f4af6-107">A <xref:System.Windows.Media.DrawingContext> nesne çizim şekil, metin, görüntüler veya videolar için yöntemler sağlar bir bağımsız değişken olarak geçirilir.</span><span class="sxs-lookup"><span data-stu-id="f4af6-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="f4af6-108">Sonuç olarak, bu yöntem panel nesnesi özelleştirmesi için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="f4af6-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f4af6-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f4af6-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="f4af6-110">Paneller Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="f4af6-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="f4af6-111">Özel Radyal paneli örneği</span><span class="sxs-lookup"><span data-stu-id="f4af6-111">Custom Radial Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="f4af6-112">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="f4af6-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)