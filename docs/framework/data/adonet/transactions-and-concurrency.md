---
title: "İşlemler ve eşzamanlılık"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4e06f54ed27a555daa30f16f452cd03c8e188a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="transactions-and-concurrency"></a>İşlemler ve eşzamanlılık
Bir işlem tek bir komutu veya bir paket olarak yürütme komut grubunu oluşur. İşlemler, iş birden çok işlem tek bir birime birleştirmenize izin verir. İşlem bir noktada bir hata oluşursa, tüm güncelleştirmeler geri ön işlem durumlarına geri alınabilir.  
  
 Bir işlem ACID özellikleri uymalıdır — kararlılık, tutarlılık, yalıtım ve dayanıklılık — veri tutarlılığı garanti etmek için. Microsoft SQL Server, bir istemci uygulaması bir güncelleştirme gerçekleştirdiğinde, günlüğe kaydetme ve işlem yönetim olanakları kilitleme sağlayarak destek işlemleri gibi çoğu ilişkisel veritabanı sistemleri ekleme veya silme işlemi.  
  
> [!NOTE]
>  Kilitleri uzun tutulur, birden fazla kaynak gerektiren işlemler eşzamanlılık düşürebilirsiniz. Bu nedenle, işlemleri olabildiğince kısa tutun.  
  
 Bir işlem aynı veritabanı veya sunucu birden çok tablo içeriyorsa, ardından saklı yordamlarda açık işlemleri genellikle daha iyi gerçekleştirin. Transact-SQL kullanarak SQL Server saklı yordamlarda işlemleri oluşturabilirsiniz `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, ve `ROLLBACK TRANSACTION` deyimleri. Daha fazla bilgi için SQL Server Books Online'a bakın.  
  
 Bir işlem arasında gibi farklı kaynak yöneticileri içeren işlemlerin [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] ve Oracle, dağıtılmış bir işlem gerektirir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Yerel işlemler](../../../../docs/framework/data/adonet/local-transactions.md)  
 Bir veritabanında işlemleri gerçekleştirmek üzere gösterilmiştir.  
  
 [Dağıtılmış işlemler](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 ADO.NET dağıtılmış işlemleri gerçekleştirmeyi açıklar.  
  
 [SQL Server ile System.Transactions tümleştirme](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Açıklar <xref:System.Transactions> ile tümleştirme [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] dağıtılmış işlemler ile çalışmak için.  
  
 [İyimser eşzamanlılık](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 İyimser ve kötümser eşzamanlılık ve eşzamanlılık ihlali test nasıl açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem temelleri](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [Bir veri kaynağına bağlanma](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Komutları ve parametreleri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapters ve DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
