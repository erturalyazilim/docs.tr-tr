---
title: LINQ to nesneler (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8de6308726ffeca8d4fa675f164037dc1fd967a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to nesneler (Visual Basic)
"Nesnelere LINQ" başvuruyor LINQ kullanımını terim tüm sorgular <xref:System.Collections.IEnumerable> veya <xref:System.Collections.Generic.IEnumerable%601> koleksiyonu veya bir ara LINQ sağlayıcısı gibi API kullanmadan, doğrudan [LINQ-SQL](https://msdn.microsoft.com/library/bb386976) veya [LINQ-XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13). LINQ numaralandırılabilir tüm koleksiyonlar gibi sorgulamak için kullanabileceğiniz <xref:System.Collections.Generic.List%601>, <xref:System.Array>, veya <xref:System.Collections.Generic.Dictionary%602>. Koleksiyon, kullanıcı tanımlı olabilir veya bir .NET Framework API tarafından döndürülen.  
  
 Bir temel anlamda nesnelere LINQ koleksiyonlar için yeni bir yaklaşım temsil eder. Karmaşık yazma gerekiyordu eski biçimde `For Each` koleksiyondan verileri almak üzere nasıl belirtilen döngüler. LINQ yaklaşımda, almak istediğiniz açıklar bildirim temelli bir kod yazın.  
  
 Ayrıca, üç ana avantajları geleneksel LINQ sorgularını teklif `For Each` döngüler:  
  
1.  Bunlar özellikle birden çok koşul filtre uygularken daha kısa ve okunabilir,.  
  
2.  Güçlü filtreleme, sıralama ve uygulama kodu en az özellikleriyle gruplandırma sağlarlar.  
  
3.  Bunlar çok az kayıpla veya hiç değişiklik ile diğer veri kaynakları için bağlantı noktası kurulmuş.  
  
 Genel olarak, daha karmaşık hayata geçirmek yerine geleneksel yineleme teknikleri LINQ kullanarak daha fazla avantajı, veriler üzerinde gerçekleştirmek istediğiniz işlem.  
  
 Bu bölümün amacı select bazı örnekler LINQ yaklaşımda göstermektir. Kapsamlı olması amaçlanmamıştır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [LINQ ve dizeler (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 LINQ Sorgu ve dizeler ve koleksiyonları dizeleri dönüştürmek için nasıl kullanılabileceği açıklanır. Ayrıca bu ilkeler göstermek konulara bağlantılar içerir.  
  
 [LINQ ve yansıma (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 LINQ yansıma nasıl kullandığını gösteren bir örnek bağlantılar.  
  
 [LINQ ve dosya dizinleri (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 LINQ dosya sistemleri ile etkileşim kurmak için nasıl kullanılabileceği açıklanır. Ayrıca bu kavramları göstermeye konulara bağlantılar içerir.  
  
 [Nasıl yapılır: LINQ (Visual Basic) ile ArrayList sorgulama](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 C# ArrayList sorgulama gösterir.  
  
 [Nasıl yapılır: özel yöntemler ekleme LINQ sorgularını (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 İçin genişletme yöntemleri ekleyerek LINQ sorguları için kullanabileceğiniz yöntemler kümesi genişletmek açıklanmaktadır <xref:System.Collections.Generic.IEnumerable%601> arabirimi.  
  
 [Dil ile tümleşik sorgu (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 LINQ açıklayan ve sorgular gerçekleştirebilir kod örnekleri sağlayın konulara bağlantılar sağlar.
