---
title: "(Varlık SQL) var."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a8e483124205d986ad7a44b47815ed6aa2845744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="exists-entity-sql"></a>(Varlık SQL) var.
Bir koleksiyonu boş olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Bir koleksiyonu döndüren herhangi geçerli bir ifade.  
  
 DEĞİL  
 EXISTS sonucunu tasarruflarını belirtir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`koleksiyon boş değilse; Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 EXISTS biridir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri ayarlayın. Tüm [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kümesi işleçleri soldan sağa değerlendirilir. Öncelik bilgilerini [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri, bakın [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki varlık SQL sorgu EXISTS işlecini koleksiyonu boş olup olmadığını belirlemek için kullanır. Sorgu AdventureWorks satış modelini temel alır. Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:  
  
1.  Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Varlık SQL Başvurusu](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
