---
title: "ListBox Yerine Ne Zaman Windows Forms ComboBox Kullanılır?"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b4eb1ce70b1ec4b249eb126b608c9f8578d327c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="8f8c6-102">ListBox Yerine Ne Zaman Windows Forms ComboBox Kullanılır?</span><span class="sxs-lookup"><span data-stu-id="8f8c6-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="8f8c6-103"><xref:System.Windows.Forms.ComboBox> Ve <xref:System.Windows.Forms.ListBox> denetimleri benzer davranışları sahiptir ve bazı durumlarda değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="8f8c6-104">Bir ya da başka bir görev için daha uygun olduğunda zamanlar vardır.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="8f8c6-105">Genellikle, önerilen seçenek listesini yoktur ve listede nedir için giriş sınırlama getirmek istediğinizde bir liste kutusu uygun olduğunda bir birleşik giriş kutusu uygundur.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="8f8c6-106">Birleşik giriş kutusu bir metin kutusu alanı içerdiğinden, listede olmayan seçimler yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="8f8c6-107">Özel durum olduğunda <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> özelliği ayarlanmış <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="8f8c6-108">Bu durumda, ilk harfi yazarsanız denetimi bir öğe seçin.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="8f8c6-109">Ayrıca, birleşik giriş kutuları, bir form üzerinde alanı kaydedin.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="8f8c6-110">Aşağı oka kullanıcı kadar tam listesi görüntülenmeyen için birleşik giriş kutusu kolayca bir liste kutusu değil nerelerde küçük bir alanda uygun olamaz.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="8f8c6-111">Bir özel durum olduğunda <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> özelliği ayarlanmış <xref:System.Windows.Forms.ComboBoxStyle.Simple>: tam listesi görüntülenir ve birleşik giriş kutusu bir liste kutusu olduğundan daha fazla yer alır.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8c6-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="8f8c6-113">Nasıl yapılır: ekleme ve kaldırma öğeleri bir Windows Forms ComboBox, ListBox veya CheckedListBox denetimi</span><span class="sxs-lookup"><span data-stu-id="8f8c6-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="8f8c6-114">Nasıl yapılır: bir Windows içeriğini sıralama Forms ComboBox, ListBox veya CheckedListBox denetimi</span><span class="sxs-lookup"><span data-stu-id="8f8c6-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="8f8c6-115">Windows Forms denetimleri seçenekleri listelemek için kullanılır</span><span class="sxs-lookup"><span data-stu-id="8f8c6-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)