---
title: "Nasıl yapılır: denetim Namespace önekleri (Visual Basic) (LINQ-XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a48feeb25cc8d28d57edc7421f73b2829f8c19ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>Nasıl yapılır: denetim Namespace önekleri (Visual Basic) (LINQ-XML)
Bu konu, ad alanı öneklerini nasıl kontrol edebilir açıklar.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnek iki ad alanı bildirir. Gerektiğini belirtir `http://www.adventure-works.com` ad alanı öneki var. `aw`ve `www.fourthcoffee.com` ad alanı öneki var. `fc`.  
  
### <a name="code"></a>Kod  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnek şu çıkışı üretir:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML ad alanları (Visual Basic) ile çalışma](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
