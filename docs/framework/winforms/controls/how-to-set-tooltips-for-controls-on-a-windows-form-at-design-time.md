---
title: "Nasıl yapılır: Tasarım Zamanında Windows Formundaki Denetimler için ToolTips Ayarlama"
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
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81716be53468242734c3d722eb21e020e58f65ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="0f798-102">Nasıl yapılır: Tasarım Zamanında Windows Formundaki Denetimler için ToolTips Ayarlama</span><span class="sxs-lookup"><span data-stu-id="0f798-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="0f798-103">Ayarlayabileceğiniz bir <xref:System.Windows.Forms.ToolTip> kodunda ya da Windows Form Tasarımcısı dize.</span><span class="sxs-lookup"><span data-stu-id="0f798-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="0f798-104">Hakkında daha fazla bilgi için <xref:System.Windows.Forms.ToolTip> bileşeni Bkz [ToolTip bileşenine genel bakış](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0f798-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f798-105">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="0f798-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0f798-106">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="0f798-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0f798-107">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0f798-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="0f798-108">Bir araç ipucu programlı olarak ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="0f798-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="0f798-109">Araç İpucu görüntüler denetimi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0f798-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="0f798-110">Kullanım <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> yöntemi <xref:System.Windows.Forms.ToolTip> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="0f798-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="0f798-111">Bir araç ipucu Designer'da ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="0f798-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="0f798-112">Ekleme bir <xref:System.Windows.Forms.ToolTip> forma bileşen.</span><span class="sxs-lookup"><span data-stu-id="0f798-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="0f798-113">Araç ipucu görüntülemek veya forma ekler denetimi seçin.</span><span class="sxs-lookup"><span data-stu-id="0f798-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="0f798-114">İçinde **özellikleri** penceresindeki ayarlayın **araç ipucu ToolTip1 üzerinde** uygun bir metin dizesini değerine.</span><span class="sxs-lookup"><span data-stu-id="0f798-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f798-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0f798-115">See Also</span></span>  
 [<span data-ttu-id="0f798-116">ToolTip bileşenine genel bakış</span><span class="sxs-lookup"><span data-stu-id="0f798-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="0f798-117">Nasıl yapılır: Windows Forms ToolTip bileşeninin gecikmesini değiştirme</span><span class="sxs-lookup"><span data-stu-id="0f798-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="0f798-118">ToolTip bileşeni</span><span class="sxs-lookup"><span data-stu-id="0f798-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)