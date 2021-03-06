---
title: "Nasıl yapılır: DBML dosyasını değiştirerek özelleştirilmiş kod oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 743e938df0b9c7f12a9c3a11a4b5558137add529
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Nasıl yapılır: DBML dosyasını değiştirerek özelleştirilmiş kod oluşturma
Oluşturabileceğiniz [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu bir veritabanı işaretleme dili (.dbml) meta veri dosyasından. Bu yaklaşım uygulama eşleme kodu oluşturmadan önce varsayılan .dbml dosyasını özelleştirmek için bir fırsat sunar. Bu gelişmiş bir özelliktir.  
  
 Bu işlemdeki adımlar aşağıdaki gibidir:  
  
1.  Bir .dbml dosyası oluşturun.  
  
2.  .Dbml dosyasını değiştirmek için bir düzenleyici kullanın. .Dbml dosyanın şema tanımını (.xsd) dosyası için karşı doğrulamalısınız Not [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml dosyaları. Daha fazla bilgi için bkz: [LINQ-SQL kod oluşturma](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Oluştur [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu.  
  
 Aşağıdaki örnekler SQLMetal komut satırı aracını kullanın. Daha fazla bilgi için bkz: [SqlMetal.exe (kod üretme aracı)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, Northwind örnek veritabanından .dbml dosyası oluşturur. Veritabanı meta veriler için kaynak olarak veritabanının adını veya .mdf dosyasının adını kullanabilirsiniz.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod oluşturur [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu dosyasının .dbml dosyasından.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-SQL kod oluşturma](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe (kod üretme aracı)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Nesne modeli oluşturma](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
