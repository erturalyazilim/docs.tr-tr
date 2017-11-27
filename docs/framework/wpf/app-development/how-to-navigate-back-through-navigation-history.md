---
title: "Nasıl yapılır: geri gezinti geçmişinde gezinme"
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
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c715bda86fe6a4a010d80000db89619fc8bf8b7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="29d02-102">Nasıl yapılır: geri gezinti geçmişinde gezinme</span><span class="sxs-lookup"><span data-stu-id="29d02-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="29d02-103">Bu örnek, Gezinme geçmişi arkada girişleri için gezinme göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="29d02-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29d02-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="29d02-104">Example</span></span>  
 <span data-ttu-id="29d02-105">İçinde barındırılan içerikten çalışan kod bir <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> kullanmak <xref:System.Windows.Navigation.NavigationService>, veya [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] geri geçmişinde gezinme, bir kerede bir girdiye gidebilir.</span><span class="sxs-lookup"><span data-stu-id="29d02-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="29d02-106">Gezinme geri bir girişi gerektiren olduğunu girişleri geri gezinti geçmişinde incelenerek ilk denetimi **CanGoBack** gezinme yedeklenmeden önce bir girdi çağırarak özelliği **GoBack** yöntem.</span><span class="sxs-lookup"><span data-stu-id="29d02-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="29d02-107">Bu aşağıdaki örnekte gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="29d02-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="29d02-108">**CanGoBack** ve **GoBack** tarafından uygulanan <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, ve <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="29d02-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29d02-109">Çağırırsanız **GoBack**, ve geri gezinti geçmişinde hiçbir girdi yoksa bir <xref:System.InvalidOperationException> tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="29d02-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>