---
title: "Zaman uyumsuz işlemler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b616a6cf08dd47a9e46e8e887efbc88469dedfd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="asynchronous-operations"></a>Zaman uyumsuz işlemler
Komut yürütmeleri gibi bazı veritabanı işlemlerini tamamlamak için önemli zaman alabilir. Böyle bir durumda, tek iş parçacıklı uygulamalar diğer işlemleri ya da gerekir komutu kendi işlemleri devam etmeden önce tamamlanmasını bekleyin. Buna karşılık, uzun süre çalışan işlemi bir arka plan iş parçacığı atamak için ön plan iş parçacığı işlemi etkin kalmasını sağlar. Bir Windows uygulaması'nda, örneğin, uzun süre çalışan işlemi için bir arka plan iş parçacığı temsilci işlemi yürütülürken yanıt verebilir durumda kalması kullanıcı arabirimi iş parçacığı sağlar.  
  
 .NET Framework geliştiricilerin arka plan iş parçacıkları yararlanabilir ve kullanıcı arabirimi veya diğer işlemlerin tamamlanmasını yüksek öncelikli iş parçacıkları boş için kullanabileceği birkaç standart zaman uyumsuz tasarım desenleri sağlar. ADO.NET bu aynı tasarım desenleri destekler, <xref:System.Data.SqlClient.SqlCommand> sınıfı. Özellikle, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, ve <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> ile eşleştirilmiş yöntemleri <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A>, ve <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> yöntemleri zaman uyumsuz destek sağlar.  
  
> [!NOTE]
>  Zaman uyumsuz programlama bir .NET Framework'ün çekirdek özelliğidir ve ADO.NET standart tasarım modeli yararlanır. Geliştiricilere sunulan farklı zaman uyumsuz teknikleri hakkında daha fazla bilgi için bkz: [çağırma zaman uyumlu yöntemleri zaman uyumsuz olarak](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Zaman uyumsuz teknikler kullanılarak rağmen ADO.NET ile özellikleri tüm özel durumlar eklemez, geliştiricilerin ADO.NET diğer alanlarda .NET Framework zaman uyumsuz özellikler kullanır olasıdır. Avantajları ve birden çok iş parçacıklı uygulamalar oluşturma Tuzaklar haberdar olmanız önemlidir. Bu bölümde noktasında birkaç önemli sorunları çıkışı, geliştiricilerin izleyin örnekleri birden çok iş parçacıklı işlevselliğine sahiptir uygulamaları oluştururken dikkate almanız gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Geri aramalar kullanarak Windows uygulamaları](../../../../../docs/framework/data/adonet/sql/windows-applications-using-callbacks.md)  
 Form ve içeriklerini ayrı bir iş parçacığı ile etkileşimi doğru şekilde işlememesi nasıl güvenli bir şekilde, bir zaman uyumsuz komutu çalıştırılacağını gösteren bir örnek sağlar.  
  
 [Bekleme tanıtıcıları kullanarak ASP.NET uygulamaları](../../../../../docs/framework/data/adonet/sql/aspnet-apps-using-wait-handles.md)  
 Tüm komutların tamamlanma işlemi yönetmek için bekleme tanıtıcıları kullanarak bir ASP.NET sayfasından birden çok eşzamanlı komut yürütmek nasıl gösteren bir örnek sağlar.  
  
 [Konsol uygulamaları yoklama](../../../../../docs/framework/data/adonet/sql/polling-in-console-applications.md)  
 Bir konsol uygulamasından bir zaman uyumsuz komutunun yürütülmesinin tamamlanmasını beklemek için yoklama kullanımını gösteren bir örnek sağlar. Bu yöntem aynı zamanda bir sınıf kitaplığı veya başka bir uygulama kullanıcı arabirimi olmadan geçerli değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL Server ve ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Zaman uyumlu yöntemleri zaman uyumsuz olarak çağırma](../../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
