---
title: "Nasıl yapılır: EntityCommand kullanarak parametreli varlık SQL sorgusu yürütme"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1531e18a6be3e7ab5c0cec4f19f33692fd04383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Nasıl yapılır: EntityCommand kullanarak parametreli varlık SQL sorgusu yürütme
Bu konuda nasıl yürütüleceği gösterilmektedir bir [!INCLUDE[esql](../../../../../includes/esql-md.md)] kullanarak parametreye sahip sorgu bir <xref:System.Data.EntityClient.EntityCommand> nesnesi.  
  
### <a name="to-run-the-code-in-this-example"></a>Bu örnekte kodu çalıştırmak için  
  
1.  Ekleme [AdventureWorks satış modeli](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) projenize ve kullanmak için projenizin yapılandırma [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: Varlık veri modeli Sihirbazı'nı](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Uygulamanız için kod sayfasında aşağıdakileri ekleyin `using` deyimleri (`Imports` Visual Basic'te):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki parametreli bir sorgu dizesi oluşturmak gösterilmiştir. Daha sonra oluşturur bir <xref:System.Data.EntityClient.EntityCommand>, iki parametreyi ekler <xref:System.Data.EntityClient.EntityParameter> , koleksiyonunu <xref:System.Data.EntityClient.EntityCommand>ve toplulukta tekrarlanan `Contact` öğeleri.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: parametreleştirilmiş sorgu yürütme](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [Varlık SQL dili](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
