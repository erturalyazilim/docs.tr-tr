---
title: "Nasıl Yapılır: Visual Basic'te Dosyalara Metin Yazma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfdae490a7d78e44f230e22f8431d5ee91461c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a>Nasıl Yapılır: Visual Basic'te Dosyalara Metin Yazma
<xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> Yöntemi, dosyalara metin yazma için kullanılabilir. Belirtilen dosya mevcut değilse oluşturulur.  
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-write-text-to-a-file"></a>Bir dosyaya metin yazma  
  
-   Kullanım `WriteAllText` metin dosyasını ve yazılacak metnini belirten bir dosyaya yazmak için yöntem. Bu örnek satır Yazar `"This is new text."` adlı dosyaya `test.txt`, varolan herhangi bir metin dosyasındaki metni ekleme.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a>Dizeleri bir dizi bir dosyaya yazmak için  
  
-   Dize toplulukta döngüsü. Kullanım `WriteAllText` metni eklenecek dize ve hedef dosya belirten bir dosyaya yazmak için yöntem ve ayar `append` için `True`.  
  
     Bu örnek, dosya adlarını Yazar `Documents and Settings` dizininden `FileList.txt`, satır ekleme dönüş her okunabilirliği arasında.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Aşağıdaki koşullar özel bir duruma neden olabilir:  
  
-   Yolu şu nedenlerden biri için geçerli değil: sıfır uzunlukta bir dize değil, yalnızca boşluk içeriyor, geçersiz karakterler içeriyor veya bir aygıt yol olduğundan (ile başlayan \\ \\.\\) (<xref:System.ArgumentException>).  
  
-   Çünkü yolu geçerli değil `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File`var olmayan bir yola işaret eden (<xref:System.IO.FileNotFoundException> veya <xref:System.IO.DirectoryNotFoundException>).  
  
-   Dosya başka bir işlem tarafından kullanılıyor veya bir g/ç hatası oluştuğunda (<xref:System.IO.IOException>).  
  
-   Yolu sistem tarafından tanımlanan uzunluk üst sınırını aşıyor (<xref:System.IO.PathTooLongException>).  
  
-   Yolda bir dosya veya dizin adı biçimi geçersiz veya iki nokta üst üste (:) içerir (<xref:System.NotSupportedException>).  
  
-   Kullanıcı yolunu görüntülemek için gerekli izinlere sahip değil (<xref:System.Security.SecurityException>).  
  
-   Tam ve çağrısı disktir `WriteAllText` başarısız (<xref:System.IO.IOException>).  
  
 Kısmi güven bağlamda çalıştırıyorsanız, kodu nedeniyle yeterli ayrıcalığa sahip bir özel durum. Daha fazla bilgi için bkz: [kod erişim güvenliği Temelleri](https://msdn.microsoft.com/library/33tceax8).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>  
 [Nasıl yapılır: metin dosyalarını okuma](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
