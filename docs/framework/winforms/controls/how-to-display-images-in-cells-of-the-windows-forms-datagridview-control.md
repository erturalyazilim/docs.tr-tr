---
title: "Nasıl yapılır: Windows Forms DataGridView Denetiminin Hücrelerinde Görüntü Görüntüleme"
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
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b2e06298d0ead9a2dd9fa554af0c42df5d61d56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="1b541-102">Nasıl yapılır: Windows Forms DataGridView Denetiminin Hücrelerinde Görüntü Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="1b541-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1b541-103">Resim veya grafik veri satırında görüntüleyebilirsiniz değerlerinden biri.</span><span class="sxs-lookup"><span data-stu-id="1b541-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="1b541-104">Genellikle, bu grafik bir çalışanın fotoğraf veya bir şirket logosu şeklinde.</span><span class="sxs-lookup"><span data-stu-id="1b541-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="1b541-105">Resimler ekleme basit veri içinde görüntülediğinizde <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="1b541-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1b541-106"><xref:System.Windows.Forms.DataGridView> Denetim yerel işler tarafından desteklenen herhangi bir resim biçimi <xref:System.Drawing.Image> OLE yanı sıra sınıfı resim bazı veritabanı tarafından kullanılan biçimi.</span><span class="sxs-lookup"><span data-stu-id="1b541-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="1b541-107">Varsa <xref:System.Windows.Forms.DataGridView> denetimin veri kaynağına sahip bir sütun görüntülerinin, tarafından otomatik olarak görüntülenir <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="1b541-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="1b541-108">Aşağıdaki kod örneğinde, katıştırılmış bir kaynaktan bir simge ayıklayın ve her bir görüntü sütunu hücrenin görüntülemek için bir bit eşlem Dönüştür gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="1b541-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="1b541-109">Karşılık gelen görüntülerle metinsel hücre değerlerini değiştirir başka bir örnek için bkz: [nasıl yapılır: Windows Forms DataGridView denetiminde veri biçimlendirmeyi özelleştirme](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1b541-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b541-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="1b541-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b541-111">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="1b541-111">Compiling the Code</span></span>  
 <span data-ttu-id="1b541-112">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="1b541-112">This example requires:</span></span>  
  
-   <span data-ttu-id="1b541-113">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="1b541-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="1b541-114">Adlı bir katıştırılmış simgesi Kaynak `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="1b541-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="1b541-115">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, ve <xref:System.Drawing?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="1b541-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b541-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1b541-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="1b541-117">Temel sütun, satır ve hücre özellikleri Windows Forms DataGridView denetiminde</span><span class="sxs-lookup"><span data-stu-id="1b541-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="1b541-118">Nasıl yapılır: Windows Forms DataGridView denetiminde veri biçimlendirmeyi özelleştirme</span><span class="sxs-lookup"><span data-stu-id="1b541-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)