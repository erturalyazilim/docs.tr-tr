---
title: Ara Materialization (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 46d347921e24bc5504c69534d7b5c087818a6c7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="intermediate-materialization-c"></a>Ara Materialization (C#)
Dikkatli değilse, bazı durumlarda, büyük ölçüde, uygulamanızın bellek ve performans profili sorgularınızda koleksiyonların erken materialization neden olarak değiştirebilirsiniz. Bazı standart sorgu işleçleri, tek bir öğe oluşturan önce kendi kaynak koleksiyonu materialization neden. Örneğin, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> önce tüm kaynak toplulukta tekrarlanan sonra tüm öğeleri sıralar ve son olarak ilk öğe verir. Bu, sıralı bir koleksiyonu ilk öğesini almak pahalı olduğunu gösterir; her öğe bundan sonra pahalı değil. Bu mantıklı: Bu sorgu işleci aksini yapmasını olanaksız olacaktır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, önceki örnekte değiştirir. `AppendString` Yöntem çağrılarını <xref:System.Linq.Enumerable.ToList%2A> kaynak yineleme önce. Bu materialization neden olur.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 Bu örnek şu çıkışı üretir:  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 Bu örnekte, gördüğünüz çağrısı <xref:System.Linq.Enumerable.ToList%2A> neden `AppendString` ilk öğe sağlayan önce tüm kaynak numaralandırılamadı. Kaynak uzun bir diziye olsaydı, bu uygulamanın bellek profili önemli ölçüde alter.  
  
 Standart sorgu işleçleri de birbirine zincirlenebilir. Bu öğreticinin son konusunda bu gösterilmektedir.  
  
-   [Zincirleme standart sorgu işleçleri birlikte (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici: Sorguları birlikte (C#) zincirleme](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
