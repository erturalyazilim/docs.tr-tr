---
title: "Veri bağlama ve LINQ-DataSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3b097f9bca790d1f19da9d75f834c6277507d8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-and-linq-to-dataset"></a>Veri bağlama ve LINQ-DataSet
*Veri bağlama* uygulama kullanıcı Arabirimi iş mantığı arasında bir bağlantı kurar işlemidir. Bağlama doğru ayarları varsa ve veri değeri değiştiğinde veri uygun bildirimleri sağlarsa, veriye bağlı öğeleri değişiklikleri otomatik olarak yansıtır. <xref:System.Data.DataSet> Tutarlı bir ilişkisel programlama modeli, içerdiği veri kaynağını bakılmaksızın sağlayan veri bellek içi gösterimidir. ADO.NET 2.0 <xref:System.Data.DataView> depolanan verilerini sıralama ve filtreleme sağlar bir <xref:System.Data.DataTable>. Bu işlevsellik, genellikle veri bağlama uygulamalarda kullanılır. Kullanarak bir <xref:System.Data.DataView>farklı sıralamalar olan bir tabloda veri getirebilir ve veri satırı durum ya da bir filtre ifadesi göre göre filtre uygulayabilirsiniz. Hakkında daha fazla bilgi için <xref:System.Data.DataView> nesne için bkz: [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]üzerinden karmaşık ve güçlü sorgular oluşturmak geliştiriciler sağlayan bir <xref:System.Data.DataSet> kullanarak [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Ancak, bir [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sorgunun döndürdüğü numaralandırması <xref:System.Data.DataRow> kolayca bağlama senaryolarda kullanılmayan nesneler. Bağlama kolaylaştırmak için oluşturabileceğiniz bir <xref:System.Data.DataView> gelen bir [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sorgu. Bu <xref:System.Data.DataView> filtreleme ve sorguda belirtilen sıralama kullanır, ancak daha iyi veri bağlaması için uygundur. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]işlevselliğini genişleten <xref:System.Data.DataView> sağlayarak [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] ifade tabanlı filtreleme ve sıralama, veren çok daha karmaşık ve güçlü filtreleme ve sıralama daha dize tabanlı filtreleme ve sıralama işlemleri.  
  
 Unutmayın <xref:System.Data.DataView> sorgu temsil eder ve sorgu en üstünde bir görünüm değil. <xref:System.Data.DataView> Gibi UI denetimine bağlı bir <xref:System.Windows.Forms.DataGrid> veya <xref:System.Windows.Forms.DataGridView>, basit veri bağlama modelini sağlama. A <xref:System.Data.DataView> de oluşturulabilir bir <xref:System.Data.DataTable>, bu tablonun varsayılan görünüm sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [DataView nesnesi oluşturma](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Oluşturma hakkında bilgi sağlayan bir <xref:System.Data.DataView>.  
  
 [DataView ile filtreleme](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Filtrele açıklar <xref:System.Data.DataView>.  
  
 [DataView ile sıralama](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 İle sıralama açıklar <xref:System.Data.DataView>.  
  
 [DataView DataRowView koleksiyonunda sorgulama](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Sorgulama hakkında bilgi sağlayan <xref:System.Data.DataRowView> koleksiyonu kullanıma sunulan <xref:System.Data.DataView>.  
  
 [DataView performansı](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Hakkında bilgi sağlar <xref:System.Data.DataView> ve performans.  
  
 [Nasıl yapılır: bir DataView nesnesi bir Windows Forms DataGridView denetimine bağlama](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 ' E nasıl bağlanacağını açıklar bir <xref:System.Data.DataView> nesnesine bir <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlama Kılavuzu](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
