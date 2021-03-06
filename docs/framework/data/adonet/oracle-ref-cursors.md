---
title: "Oracle REF imleçler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 277e12e59ea85be4d22e28a59bd7404e5e0111f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-ref-cursors"></a>Oracle REF imleçler
.NET Framework veri sağlayıcısı Oracle için Oracle destekleyen **REF İMLEÇ** veri türü. Oracle REF imleçlerle çalışmak için veri sağlayıcısı kullanarak, aşağıdaki davranışları dikkate almanız.  
  
> [!NOTE]
>  Bazı davranışları Microsoft OLE DB Sağlayıcısı'nın Oracle (MSDAORA) farklı.  
  
-   Performansı artırmak için Oracle veri sağlayıcısı otomatik olarak bağlanmaz **REF İMLEÇ** veri türleri, MSDAORA yaptığı gibi bunları açıkça belirtmediğiniz sürece.  
  
-   Veri sağlayıcısı REF İMLEÇ parametrelerini belirtmek için kullanılan {sonuç} kaçış dahil olmak üzere tüm ODBC kaçış sıraları desteklemez.  
  
-   REF imleçler döndüren bir saklı yordamı yürütme için parametre tanımlayın <xref:System.Data.OracleClient.OracleParameterCollection> ile bir <xref:System.Data.OracleClient.OracleType> , **imleç** ve <xref:System.Data.OracleClient.OracleParameter.Direction%2A> , **çıkış**. Veri sağlayıcısı yalnızca çıkış parametreleri REF imleçler bağlamayı destekler. Sağlayıcı REF imleçler giriş parametreleri olarak desteklemez.  
  
-   Alma bir <xref:System.Data.OracleClient.OracleDataReader> parametresi değeri desteklenmiyor. Tür değerler <xref:System.DBNull> komut yürütme sonra.  
  
-   Yalnızca **CommandBehavior** REF imleçlerle çalışır numaralandırma değeri (örneğin, çağrılırken <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) olan **CloseConnection**; diğerleri yoksayılır.  
  
-   REF imleçler sırasını **OracleDataReader** parametrelerinde terabayt bağlıdır **OracleParameterCollection**. <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> Özelliği yoksayılır.  
  
-   PL/SQL **tablo** veri türü desteklenmiyor. Ancak, REF imleçler daha verimlidir. Kullanmanız gerekiyorsa bir **tablo** veri türü, OLE DB .NET veri sağlayıcısı MSDAORA ile kullanın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [REF İMLEÇ örnekleri](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 REF imleçler kullanarak gösteren üç örnekleri içerir.  
  
 [Bir OracleDataReader REF İMLEÇ parametreleri](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Değeri olarak okur ve REF CURSOR parametresiyle döndüren bir PL/SQL saklı yordamı yürütme yapmayı gösteren bir **OracleDataReader**.  
  
 [Bir OracleDataReader kullanarak birden çok REF imleçler veri alma](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Kullanarak değerlerini okur ve iki REF İMLEÇ parametreleri döndüren bir PL/SQL saklı yordamı yürütme yapmayı gösteren bir **OracleDataReader**.  
  
 [Kullanarak bir veri kümesi doldurma ya da daha fazla REF imleçler](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Doldurur ve iki REF İMLEÇ parametreleri döndüren bir PL/SQL saklı yordamı yürütme yapmayı gösteren bir <xref:System.Data.DataSet> satırlarla döndürülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oracle ve ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
