---
title: "Nasıl yapılır: Veritabanı değişiklikleri gönderme"
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
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 039eaac26833651fbd82dc1a69a31f394c1464c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-submit-changes-to-the-database"></a>Nasıl yapılır: Veritabanı değişiklikleri gönderme
Nesnelerinizi kaç değişiklikler bağımsız olarak, değişiklikler yalnızca bellek içi çoğaltmalar için yapılır. Veritabanındaki gerçek veriler için herhangi bir değişiklik yaptınız. Açıkça çağrısı tamamlanana kadar değişiklikleriniz sunucusuna iletilmez <xref:System.Data.Linq.DataContext.SubmitChanges%2A> üzerinde <xref:System.Data.Linq.DataContext>.  
  
 Bu arama yaparken <xref:System.Data.Linq.DataContext> değişikliklerinizi eşdeğer SQL komutlarını içine çevirmek çalışır. Bu eylemler geçersiz kılmak için kendi özel mantık kullanabilirsiniz, ancak gönderme sırası bir hizmet tarafından düzenlenmiş <xref:System.Data.Linq.DataContext> olarak bilinen *işlemci değiştirmek*. Olayların sırası aşağıdaki gibidir:  
  
1.  Çağırdığınızda <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] yeni örnekleri kendisine eklenmiş olan olup olmadığını belirlemek için bilinen nesne kümesini inceler. Varsa, bu yeni örnekler izlenen nesneler kümesine eklenir.  
  
2.  Bekleyen değişiklikleri bulunan tüm nesneleri aralarındaki bağımlılıkları temel nesneleri dizisini içine sıralanır. Değişiklikleri bağımlı nesneler üzerinde nesneleri bağımlılıklarını sonra sıralanamadı.  
  
3.  Gerçek değişiklikleri hemen iletilmeden önce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tekil komutlar dizi kapsülleyen bir işlem başlatır.  
  
4.  Nesnelere değişiklikler çevrilmiş tek tek SQL komutları ve sunucuya gönderilen.  
  
 Bu noktada, veritabanı tarafından algılanan tüm hataları gönderme işleminin vermemesine neden ve özel durum oluşturuldu. Veritabanında yapılan tüm değişiklikler geri hiçbir gönderimlerini sürekli olarak oluştuysa alınır. <xref:System.Data.Linq.DataContext> Tüm değişiklikleri tam kaydını sürdürüyor. Bu nedenle çağrısı ve sorunu düzeltmek deneyebilirsiniz <xref:System.Data.Linq.DataContext.SubmitChanges%2A> yeniden, aşağıdaki kod örneğinde olduğu gibi.  
  
## <a name="example"></a>Örnek  
 Gönderme işlemi başarıyla tamamlandığında, <xref:System.Data.Linq.DataContext> değişiklik izleme bilgilerini yoksayarak tarafından yapılan değişiklikleri nesneleri kabul eder.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: algılamak ve çakışan gönderimlerini gidermek](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 [Nasıl yapılır: değişiklik çakışmalarını yönetin](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Örnek veritabanları yükleme](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Sağlama ve veri değişiklikleri gönderme](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
