---
title: Bilinen sorunlar ve dikkat edilmesi gerekenler LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 85fea34f6044c99a58fd27dbf5a03198741294ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>Bilinen sorunlar ve dikkat edilmesi gerekenler LINQ to Entities
Bu bölüm ile ilgili bilinen sorunlar hakkında bilgi sağlar [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgular.  
  
-   [LINQ sorguları, önbelleğe alınamıyor](#LINQQueriesThatAreNotCached)  
  
-   [Kayıp bilgi sıralama](#OrderingInfoLost)  
  
-   [İmzasız tamsayılar desteklenmiyor](#UnsignedIntsUnsupported)  
  
-   [Tür dönüştürme hataları](#TypeConversionErrors)  
  
-   [Skaler olmayan değişkenleri desteklenmiyor başvurma](#RefNonScalarClosures)  
  
-   [İç içe geçmiş sorgular SQL Server 2000 ile başarısız olabilir](#NestedQueriesSQL2000)  
  
-   [Anonim bir tür yansıtma](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>LINQ sorguları, önbelleğe alınamıyor  
 .NET Framework 4. 5'ile başlayarak, LINQ to Entities sorgularında otomatik olarak önbelleğe alınır. Ancak, LINQ to Entities sorgularında geçerli `Enumerable.Contains` bellek içi koleksiyonlara işleci otomatik olarak önbelleğe alınmaz. Ayrıca derlenmiş LINQ sorgularını bellek içi koleksiyonlarda kümesini parametreleştirme izin verilmiyor.  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>Kayıp bilgi sıralama  
 Anonim bir tür sütunları yansıtma karşı yürütülen bazı sorgular kaybolur sipariş bilgilerini neden olacak bir [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] veritabanı "80" için bir uyumluluk düzeyi ayarlayın.  Order by listesinde bir sütun adı Seçici içinde bir sütun adı eşleştiğinde aşağıdaki örnekte gösterildiği gibi oluşur:  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>İmzasız tamsayılar desteklenmiyor  
 Bir işaretsiz tamsayı türünde belirten bir [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] çünkü sorgu desteklenmiyor [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] imzasız tamsayılar desteklemiyor. İşaretsiz tamsayıya belirtirseniz bir <xref:System.ArgumentException> özel durum sorgu ifade çevirisi sırasında aşağıdaki örnekte gösterildiği gibi. Bir sıra kimliği 48000 ile bu örnek sorgular.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>Tür dönüştürme hataları  
 Visual Basic'te bir özellik SQL Server bit türünde bir sütun 1 kullanmanın bir değerle eşlendiğinde, `CByte` işlevi, bir <xref:System.Data.SqlClient.SqlException> bir "Aritmetik Taşma Hatası" iletisiyle atılır. Aşağıdaki örnek sorgularda `Product.MakeFlag` AdventureWorks örnek veritabanını ve özel bir Durum sütununda üzerinden sorgu sonuçlarını yinelendiğinde oluşur.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>Skaler olmayan değişkenleri desteklenmiyor başvurma  
 Sorguda bir varlık gibi bir skaler olmayan değişkenleri başvuran desteklenmiyor. Böyle bir sorguyu yürütüldüğünde, bir <xref:System.NotSupportedException> bildiren bir ileti ile özel durum "türünde sabit değer oluşturulamıyor `EntityType`. Yalnızca ilkel türler ('Örneğin Int32, String ve GUID') bu bağlamda desteklenir."  
  
> [!NOTE]
>  Skaler değişkenleri koleksiyonu başvuran desteklenir.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>İç içe geçmiş sorgular SQL Server 2000 ile başarısız olabilir  
 Üç veya daha çok düzey derinliğinde iç içe geçmiş Transact-SQL sorguları oluşturdukları ile SQL Server 2000, LINQ to Entities sorgularında başarısız olabilir.  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>Anonim bir tür yansıtma  
 İlk sorguyu yolunuzu kullanarak ilgili nesneleri içerecek şekilde tanımlarsanız <xref:System.Data.Objects.ObjectQuery%601.Include%2A> yöntemi <xref:System.Data.Objects.ObjectQuery%601> ve anonim bir tür için döndürülen nesnelerin projeye LINQ kullanın, INCLUDE yönteminde belirtilen nesnelerin sorguda dahil edilmez sonuçları.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 İlişkili nesneleri almak için döndürülen türleri anonim bir tür için proje yok.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-varlıklar](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
