---
title: "Ön Atomization XName nesnelerin (LINQ-XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32613771da42b3e8260b1608f20ad6c195008faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="691ac-102">Ön Atomization XName nesnelerin (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="691ac-102">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="691ac-103">LINQ-XML performansını artırmak için bir yoldur önceden küçük parçalara ayrılamıyor için <xref:System.Xml.Linq.XName> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="691ac-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="691ac-104">Ön atomization anlamına gelir dizeye atadığınız bir <xref:System.Xml.Linq.XName> , oluşturucuları kullanarak XML ağaç oluşturmadan önce nesne <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XAttribute> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="691ac-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="691ac-105">Ardından, oluşturucuya bir dizeye geçiliyor yerine, kullandığınız örtük bir dönüştürme için <xref:System.Xml.Linq.XName>, başlatılmış geçirdiğiniz <xref:System.Xml.Linq.XName> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="691ac-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="691ac-106">Belirli adları yinelenen büyük bir XML ağacı oluştururken bu performansı artırır.</span><span class="sxs-lookup"><span data-stu-id="691ac-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="691ac-107">Bunu yapmak için bildirme ve başlatma <xref:System.Xml.Linq.XName> XML ağacını oluşturmak ve ardından kullanmaya başlamadan önce nesneleri <xref:System.Xml.Linq.XName> öğe ve öznitelik adları için dizelerini belirtme yerine nesneleri.</span><span class="sxs-lookup"><span data-stu-id="691ac-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="691ac-108">Çok sayıda öğe (ve özniteliklerin) oluşturuyorsanız, bu teknik aynı ada sahip önemli ölçüde performans artışı sağlar.</span><span class="sxs-lookup"><span data-stu-id="691ac-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="691ac-109">Bunu kullanmalısınız varsa karar vermek için senaryonuzun öncesi atomization test etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="691ac-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="691ac-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="691ac-110">Example</span></span>  
 <span data-ttu-id="691ac-111">Aşağıdaki örnekte bu gösterir.</span><span class="sxs-lookup"><span data-stu-id="691ac-111">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="691ac-112">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="691ac-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="691ac-113">Aşağıdaki örnek, XML belgesi bir ad alanındaki olduğu aynı tekniği gösterir:</span><span class="sxs-lookup"><span data-stu-id="691ac-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="691ac-114">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="691ac-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="691ac-115">Aşağıdaki örnek, ne, büyük olasılıkla gerçek dünyada karşınıza çıkacak için daha benzer.</span><span class="sxs-lookup"><span data-stu-id="691ac-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="691ac-116">Bu örnekte, öğenin içeriğinin bir sorgu tarafından sağlanır:</span><span class="sxs-lookup"><span data-stu-id="691ac-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="691ac-117">Önceki örnekte, adları değil önceden atomized aşağıdaki örnek, daha iyi gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="691ac-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="691ac-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="691ac-118">See Also</span></span>  
 [<span data-ttu-id="691ac-119">Performans (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="691ac-119">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)  
 [<span data-ttu-id="691ac-120">Atomized XName ve XNamespace nesneleri (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="691ac-120">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)