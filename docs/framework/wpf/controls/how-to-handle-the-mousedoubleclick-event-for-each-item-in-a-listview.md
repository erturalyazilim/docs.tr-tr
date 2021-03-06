---
title: "Nasıl yapılır: ListView'daki Her Öğe için MouseDoubleClick Olayını İşleme"
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
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53c40e9e3b02bdf33a073a93d28b619e399e375f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Nasıl yapılır: ListView'daki Her Öğe için MouseDoubleClick Olayını İşleme
Bir öğe için bir olay işlemek için bir <xref:System.Windows.Controls.ListView>, her bir olay işleyicisi eklemeniz gerekir <xref:System.Windows.Controls.ListViewItem>. Zaman bir <xref:System.Windows.Controls.ListView> bağlı açıkça oluşturmayın bir veri kaynağı için bir <xref:System.Windows.Controls.ListViewItem>, ancak ekleyerek olay her öğe için işleyebilir bir <xref:System.Windows.EventSetter> stili için bir <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir veri bağlama oluşturur <xref:System.Windows.Controls.ListView> ve oluşturan bir <xref:System.Windows.Style> her bir olay işleyicisi ekleme <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Aşağıdaki örnek tanıtıcıları <xref:System.Windows.Controls.Control.MouseDoubleClick> olay.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Bağlamak için en yaygın olmasına rağmen bir <xref:System.Windows.Controls.ListView> bir veri kaynağı için her bir olay işleyicisi eklemek için bir stil kullanabilirsiniz <xref:System.Windows.Controls.ListViewItem> bir harici veriye bağlı olarak <xref:System.Windows.Controls.ListView> olup olmadığını açıkça oluşturduğunuz bakılmaksızın bir <xref:System.Windows.Controls.ListViewItem>.  Hakkında daha fazla bilgi için açıkça ve örtülü olarak oluşturulan <xref:System.Windows.Controls.ListViewItem> denetimleri, bkz: <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.XmlElement>  
 [Veri bağlama genel bakış](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Stil ve şablon oluşturma](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Bir XMLDataProvider ve XPath sorgularını kullanarak XML verilere bağlama](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [ListView Genel Bakış](../../../../docs/framework/wpf/controls/listview-overview.md)
