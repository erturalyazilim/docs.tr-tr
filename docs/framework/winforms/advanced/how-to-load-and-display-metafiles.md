---
title: "Nasıl yapılır: Meta Dosyalarını Yükleme ve Görüntüleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="9e345-102">Nasıl yapılır: Meta Dosyalarını Yükleme ve Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="9e345-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="9e345-103"><xref:System.Drawing.Imaging.Metafile> Devraldığı sınıfı <xref:System.Drawing.Image> sınıfı, kaydetme, görüntüleme ve vektör görüntüleri inceleyerek için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="9e345-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e345-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="9e345-104">Example</span></span>  
 <span data-ttu-id="9e345-105">Ekranda bir vektör görüntüsü (meta dosyası) görüntülemek için gereken bir <xref:System.Drawing.Imaging.Metafile> nesne ve <xref:System.Drawing.Graphics> nesne.</span><span class="sxs-lookup"><span data-stu-id="9e345-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9e345-106">Bir dosya (veya bir akış) adını geçişi için bir <xref:System.Drawing.Imaging.Metafile> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="9e345-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="9e345-107">Oluşturduktan sonra bir <xref:System.Drawing.Imaging.Metafile> nesne, bu geçirmek <xref:System.Drawing.Imaging.Metafile> nesnesini <xref:System.Drawing.Graphics.DrawImage%2A> yöntemi bir <xref:System.Drawing.Graphics> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="9e345-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="9e345-108">Örnekte bir <xref:System.Drawing.Imaging.Metafile> EMF (Gelişmiş Meta dosyası) dosyasından nesnesi ve ardından, sol üst köşede ile resim çizer (60, 10).</span><span class="sxs-lookup"><span data-stu-id="9e345-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="9e345-109">Aşağıda belirtilen konumda çizilmiş meta dosyası gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="9e345-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="9e345-110">![Görüntü konumu](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="9e345-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e345-111">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="9e345-111">Compiling the Code</span></span>  
 <span data-ttu-id="9e345-112">Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="9e345-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e345-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9e345-113">See Also</span></span>  
 [<span data-ttu-id="9e345-114">Resimler, bit eşlemler, simgeler ve meta dosyaları ile çalışma</span><span class="sxs-lookup"><span data-stu-id="9e345-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)