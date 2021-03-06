---
title: "Verileri gruplandırma (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4aef8d10eaffb384fe919ffa6a1e742cb837f540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-data-c"></a>Verileri gruplandırma (C#)
Gruplandırma, böylece her grup içindeki öğeleri ortak bir özniteliği paylaşan gruplar halinde veri koyma işlemi için ifade eder.  
  
 Aşağıdaki çizimde bir karakter dizisi gruplandırma sonuçlarını gösterir. Her grup için karakterin anahtarıdır.  
  
 ![LINQ gruplandırma işlemleri](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Veri öğeleri Grup standart sorgu işleci yöntemler aşağıdaki bölümde listelenmektedir.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem adı|Açıklama|C# sorgu ifade sözdizimi|Daha Fazla Bilgi|  
|-----------------|-----------------|---------------------------------|----------------------|  
|GroupBy|Ortak bir özniteliği paylaşan grupları öğeleri. Her grubu tarafından temsil edilen bir <xref:System.Linq.IGrouping%602> nesnesi.|`group … by`<br /><br /> veya<br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|Elemanlara ekler bir <xref:System.Linq.Lookup%602> (bir-çok sözlük) dayalı bir anahtar Seçici işlevdir.|Yok.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Sorgu ifade sözdizimi örneği  
 Aşağıdaki kod örneğinde `group by` bile veya alışılmadık olup olmadıkları göre listesini Grup tamsayılar yan tümcesini.  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Linq>  
 [Standart sorgu işleçlerine genel bakış (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Group tümcesi](../../../../csharp/language-reference/keywords/group-clause.md)  
 [Nasıl yapılır: iç içe geçmiş grup oluşturma](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [Nasıl yapılır: dosyaları uzantıya (LINQ) (C#) göre gruplama](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [Nasıl yapılır: sorgu sonuçlarını gruplandırma](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [Nasıl yapılır: gruplandırma işleminde alt sorgu gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)  
 [Nasıl yapılır: bir dosya grupları (LINQ) (C#) kullanarak birden çok dosyaya bölme](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
