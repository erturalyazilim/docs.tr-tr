---
title: "Nasıl yapılır: Dosyadan Metin Okuma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 026f6ae4dd9aee340d6a9ffb931d0525ae75654a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-text-from-a-file"></a>Nasıl yapılır: Dosyadan Metin Okuma
Aşağıdaki örnek, masaüstü uygulamaları için .NET kullanılarak bir metin dosyasındaki metnin nasıl zaman uyumlu ve zaman uyumsuz olarak okunacağını gösterir. Örneğini oluştururken hem örneklerde <xref:System.IO.StreamReader> sınıfı, dosya için göreli veya mutlak yol sağlayın. Aşağıdaki örnek, uygulamayla aynı klasörde TestFile.txt adında bir dosya bulunduğunu kabul eder.  
  
 Windows Çalışma Zamanı, dosyalara okuma ve yazma için farklı akış türleri sağladığından, bu kod örnekleri Windows Mağazası uygulamaları için geliştirme uygulamaz. Windows mağazası uygulaması bağlamında bir dosyadan metin okuma gösteren örnek için bkz: [hızlı başlangıç: Okuma ve dosyalara yazma](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx). .NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme gösteren örnekler için bkz [nasıl yapılır: .NET Framework akışları arasında dönüştürme ve Windows çalışma zamanı akışları](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example"></a>Örnek  
 İlk örnek bir konsol uygulamasında zaman uyumlu okuma işlemini gösterir. Bu örnekte, metin dosyası kullanarak bir akış okuyucusunu açıldığında, içeriği bir dizeye kopyalanır ve konsola çıktı dizedir.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>Örnek  
 İkinci örnek bir Windows Presentation Foundation (WPF) uygulamasında zaman uyumsuz okuma işlemini gösterir.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [Zaman uyumsuz dosya g/ç](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: Nasıl yapılır: bir dizin listesi oluşturma](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Hızlı Başlangıç: Okuma ve dosyalara yazma](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [Nasıl yapılır: .NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Nasıl yapılır: açın ve bir günlük dosyasına Ekle](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Nasıl yapılır: bir dosyaya metin yazma](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Nasıl yapılır: bir dizeden karakterleri okuma](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Nasıl yapılır: bir dizeye karakter yazma](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Dosya ve akış t-O](../../../docs/standard/io/index.md)
