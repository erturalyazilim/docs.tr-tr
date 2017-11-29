---
title: "Bir veri kümesini XML kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28c1668dcb9678b65db62c0040adcd116221b92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="837b6-102">Bir veri kümesini XML kullanma</span><span class="sxs-lookup"><span data-stu-id="837b6-102">Using XML in a DataSet</span></span>
<span data-ttu-id="837b6-103">ADO.NET ile doldurmak için bir <xref:System.Data.DataSet> bir XML akışı veya belge.</span><span class="sxs-lookup"><span data-stu-id="837b6-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="837b6-104">XML akışı veya belge için sağlamak için kullanabileceğiniz <xref:System.Data.DataSet> verileri, şema bilgileri veya her ikisi de.</span><span class="sxs-lookup"><span data-stu-id="837b6-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="837b6-105">Varolan veriler veya şema bilgileri zaten var XML akışı veya belge sağlanan bilgileri birleştirilebilir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="837b6-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="837b6-106">ADO.NET ayrıca bir XML temsili oluşturmanıza imkan tanır bir <xref:System.Data.DataSet>, ile veya olmadan taşımak için şema <xref:System.Data.DataSet> başka tarafından kullanım için HTTP üzerinden uygulama veya XML etkin platform.</span><span class="sxs-lookup"><span data-stu-id="837b6-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="837b6-107">İçinde bir XML temsili bir <xref:System.Data.DataSet>, verileri XML'de yazılır ve gösteriminde dahil satır içi ise şema, XML Şeması Tanım Dili (XSD) kullanılarak yazılır.</span><span class="sxs-lookup"><span data-stu-id="837b6-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="837b6-108">XML ve XML Şeması sağlar uygun bir biçim içeriğini aktarmak için bir <xref:System.Data.DataSet> uzak istemcilere gelen ve giden.</span><span class="sxs-lookup"><span data-stu-id="837b6-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="837b6-109">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="837b6-109">In This Section</span></span>  
 [<span data-ttu-id="837b6-110">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="837b6-110">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 <span data-ttu-id="837b6-111">Okuma ve içeriğini yazmak için kullanılan XML biçimi DiffGram hakkında ayrıntılar sağlar bir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="837b6-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="837b6-112">Bir veri kümesini XML dosyası şuradan yükleniyor</span><span class="sxs-lookup"><span data-stu-id="837b6-112">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 <span data-ttu-id="837b6-113">İçeriği yüklerken dikkate alınması gereken farklı seçenekler açıklanır bir <xref:System.Data.DataSet> bir XML belgesinden.</span><span class="sxs-lookup"><span data-stu-id="837b6-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="837b6-114">XML verileri olarak DataSet içeriğini yazma</span><span class="sxs-lookup"><span data-stu-id="837b6-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="837b6-115">İçeriği oluşturmak nasıl ele bir <xref:System.Data.DataSet> XML verilerini ve farklı XML biçimlendirme seçeneklerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="837b6-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="837b6-116">XML'den veri kümesi şema bilgileri yükleniyor</span><span class="sxs-lookup"><span data-stu-id="837b6-116">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="837b6-117">Anlatılmaktadır <xref:System.Data.DataSet> şeması yüklemek için kullanılan yöntemleri bir <xref:System.Data.DataSet> XML'den.</span><span class="sxs-lookup"><span data-stu-id="837b6-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="837b6-118">Veri kümesi şema bilgileri XSD olarak yazma</span><span class="sxs-lookup"><span data-stu-id="837b6-118">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="837b6-119">Bir XML şeması ve bir oluşturmak nasıl kullanıldığı açıklanır bir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="837b6-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="837b6-120">Veri kümesi ve XmlDataDocument eşitleme</span><span class="sxs-lookup"><span data-stu-id="837b6-120">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="837b6-121">Hem ilişkisel hem de hiyerarşik görünümlerini tek bir veri kümesi için zaman uyumlu erişim .NET Framework'teki kullanılabilir yetenek açıklanır ve arasında zaman uyumlu bir ilişki oluşturmayı gösteren bir <xref:System.Data.DataSet> ve bir <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="837b6-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="837b6-122">İç içe geçme DataRelations</span><span class="sxs-lookup"><span data-stu-id="837b6-122">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="837b6-123">Önem düzeyi açıklanmaktadır iç içe geçmiş <xref:System.Data.DataRelation> nesneleri içeriğini temsil eden olduğunda bir <xref:System.Data.DataSet> XML verileri olarak ve bunların nasıl oluşturulacağı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="837b6-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="837b6-124">Türetilen DataSet ilişkisel yapısından XML Şeması (XSD)</span><span class="sxs-lookup"><span data-stu-id="837b6-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="837b6-125">İlişkisel yapısı veya şema açıklayan bir <xref:System.Data.DataSet> XML şemasından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="837b6-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="837b6-126">Veri kümesi ilişkisel XML yapısından çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="837b6-126">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="837b6-127">Sonuçta elde edilen ilişkisel yapısı veya şema açıklar bir <xref:System.Data.DataSet> XML öğeleri çıkarımı yapılan olduğunda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="837b6-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="837b6-128">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="837b6-128">Related Sections</span></span>  
 [<span data-ttu-id="837b6-129">ADO.NET genel bakış</span><span class="sxs-lookup"><span data-stu-id="837b6-129">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="837b6-130">ADO.NET açıklar mimarisi ve bileşenleri ve bunları uygulama verilerini yönetmek için de mevcut veri kaynaklarına erişmek için kullanma.</span><span class="sxs-lookup"><span data-stu-id="837b6-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837b6-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="837b6-131">See Also</span></span>  
 [<span data-ttu-id="837b6-132">Veri kümeleri, DataTable ve DataView</span><span class="sxs-lookup"><span data-stu-id="837b6-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="837b6-133">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="837b6-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)