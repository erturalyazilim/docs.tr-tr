---
title: DomainUpDown Denetimi (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37cec82876edadfed5cda338ca12775ad19ae732
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="a72ac-102">DomainUpDown Denetimi (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a72ac-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="a72ac-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> denetim arar düğmeleri çiftini ve bir metin kutusu birleşimini gibi listesini yukarı veya aşağı taşıma.</span><span class="sxs-lookup"><span data-stu-id="a72ac-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="a72ac-104">Denetim görüntüler ve seçenekler listesinden bir metin dizesini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="a72ac-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="a72ac-105">Kullanıcı düğmeleri listesini taşımak için yukarı ve aşağı tıklatarak yukarı ve aşağı ok tuşlarına basarak veya listeden bir öğe eşleşen bir dize yazarak dize seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a72ac-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="a72ac-106">Öğe adları alfabetik olarak sıralanan bir listesinden seçmek için bu denetim için bir olası kullanımı içindir.</span><span class="sxs-lookup"><span data-stu-id="a72ac-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="a72ac-107">(Sıralamak için ayarlanmış <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> özelliğine `true`.) Bu denetim işlevi liste kutusu veya birleşik giriş kutusu çok benzer, ancak çok az alanı kaplar.</span><span class="sxs-lookup"><span data-stu-id="a72ac-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="a72ac-108">Anahtar özellikler denetiminin <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, ve <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="a72ac-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="a72ac-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A> Özellik metin değerleri denetiminde görüntülenen nesnelerin listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="a72ac-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="a72ac-110">Varsa <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> ayarlanır `false`, kullanıcı türleri ve listesindeki bir değeri ile eşleşen metin denetimi otomatik olarak tamamlar.</span><span class="sxs-lookup"><span data-stu-id="a72ac-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="a72ac-111">Varsa <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> ayarlanır `true`, son öğenin kaydırma yönlendirilirsiniz ilk öğeye listesinde ve tersi.</span><span class="sxs-lookup"><span data-stu-id="a72ac-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="a72ac-112">Denetimin anahtar yöntemleri <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> ve <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="a72ac-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="a72ac-113">Bu denetim yalnızca metin dizelerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a72ac-113">This control displays only text strings.</span></span> <span data-ttu-id="a72ac-114">Sayısal değerler görüntüleyen bir denetim istiyorsanız kullanın <xref:System.Windows.Forms.NumericUpDown> denetim.</span><span class="sxs-lookup"><span data-stu-id="a72ac-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="a72ac-115">Daha fazla bilgi için bkz: [NumericUpDown denetimi](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="a72ac-115">For more information, see [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a72ac-116">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="a72ac-116">In This Section</span></span>  
 [<span data-ttu-id="a72ac-117">DomainUpDown denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="a72ac-117">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="a72ac-118">Genel kavramlarını tanıtır <xref:System.Windows.Forms.DomainUpDown> göz atın ve metin dizelerini listesinden olanak tanıyan denetim.</span><span class="sxs-lookup"><span data-stu-id="a72ac-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="a72ac-119">Nasıl yapılır: öğeleri Windows Forms DomainUpDown denetimlerine programlı olarak Ekle</span><span class="sxs-lookup"><span data-stu-id="a72ac-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="a72ac-120">Metin dizelerini belirtin açıklar <xref:System.Windows.Forms.DomainUpDown> denetim görüntülemelidir.</span><span class="sxs-lookup"><span data-stu-id="a72ac-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="a72ac-121">Nasıl yapılır: öğeleri Windows Forms DomainUpDown denetimlerinden kaldırma</span><span class="sxs-lookup"><span data-stu-id="a72ac-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="a72ac-122">Gelen öğelerinin nasıl silineceğini açıklar <xref:System.Windows.Forms.DomainUpDown> denetim kodu.</span><span class="sxs-lookup"><span data-stu-id="a72ac-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a72ac-123">Başvuru</span><span class="sxs-lookup"><span data-stu-id="a72ac-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="a72ac-124">Bu sınıf tanımlar ve tüm üyeleri bağlantılar içerir.</span><span class="sxs-lookup"><span data-stu-id="a72ac-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="a72ac-125">Bu sınıf tanımlar ve tüm üyeleri bağlantılara sahip...</span><span class="sxs-lookup"><span data-stu-id="a72ac-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a72ac-126">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="a72ac-126">Related Sections</span></span>  
 [<span data-ttu-id="a72ac-127">Windows Forms'ta kullanabileceğiniz denetimleri</span><span class="sxs-lookup"><span data-stu-id="a72ac-127">Controls You Can Use On Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="a72ac-128">Windows Forms denetimleri, tam bir listesi ile bunların kullanılması hakkında bilgi için bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="a72ac-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>