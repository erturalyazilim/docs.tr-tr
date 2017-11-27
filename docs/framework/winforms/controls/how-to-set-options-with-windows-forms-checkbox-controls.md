---
title: "Nasıl yapılır: Windows Forms CheckBox Denetimleriyle Seçenekleri Ayarlama"
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
f1_keywords: checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7d3ddb090488f6503c0765f6054308c28d4ab9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="f7a5d-102">Nasıl yapılır: Windows Forms CheckBox Denetimleriyle Seçenekleri Ayarlama</span><span class="sxs-lookup"><span data-stu-id="f7a5d-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="f7a5d-103">Windows Forms <xref:System.Windows.Forms.CheckBox> denetim Evet/Hayır seçenekleri veya kullanıcılara True/False vermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="f7a5d-104">Seçili olduğunda denetimi bir onay işareti görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="f7a5d-105">CheckBox denetimleriyle seçenekleri ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="f7a5d-105">To set options with CheckBox controls</span></span>  
  
1.  <span data-ttu-id="f7a5d-106">Değerini inceleyin <xref:System.Windows.Forms.CheckBox.Checked%2A> özelliğini durumunu belirlemek ve bir seçenek ayarlamak için bu değeri kullanın.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="f7a5d-107">Aşağıda, ne zaman kod örneğinde <xref:System.Windows.Forms.CheckBox> denetimin <xref:System.Windows.Forms.CheckBox.CheckedChanged> olayı, formun <xref:System.Windows.Forms.Control.AllowDrop%2A> özelliği ayarlanmış `false` onay kutusu işaretli değilse.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="f7a5d-108">Bu, kullanıcı etkileşimi kısıtlamak istediğiniz durumlarda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f7a5d-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f7a5d-109">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="f7a5d-110">CheckBox denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="f7a5d-110">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="f7a5d-111">Nasıl yapılır: Windows Forms CheckBox tıklamalarına yanıt verme</span><span class="sxs-lookup"><span data-stu-id="f7a5d-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="f7a5d-112">CheckBox denetimi</span><span class="sxs-lookup"><span data-stu-id="f7a5d-112">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)