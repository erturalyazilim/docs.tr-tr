---
title: "Nasıl yapılır: Bir Windows Formda Sesi Döngü Olarak Çalma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e61a15a7a249a90ce9eca035ebe6fd67275bb74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a>Nasıl yapılır: Bir Windows Formda Sesi Döngü Olarak Çalma
Aşağıdaki kod örneğinde ses sürekli olarak yürütür. Olduğunda kodda `stopPlayingButton_Click` olay işleyicisi çalışır, durakları oynatılmakta ses. Ses çalma, hiçbir şey olmaz.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem ve System.Windows.Forms derlemelerine başvurular.  
  
-   Dosya adı yerine `"c:\Windows\Media\chimes.wav"` geçerli bir dosya adı ile.  
  
 Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.  Ayrıca bkz. [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Dosya işlemleri içinde uygun özel durum işleme blok içine alınması.  
  
 Aşağıdaki koşullar özel bir duruma neden olabilir:  
  
-   Yol adı yanlış biçimlendirilmiş. Örneğin, geçerli olmayan karakterler içeriyor veya yalnızca boşluk olan (<xref:System.ArgumentException> sınıfı).  
  
-   Yolun salt okunurdur (<xref:System.IO.IOException> sınıfı).  
  
-   Yol adı `Nothing` (<xref:System.ArgumentNullException> sınıfı).  
  
-   Yol adı çok uzun (<xref:System.IO.PathTooLongException> sınıfı).  
  
-   Yol geçersiz (<xref:System.IO.DirectoryNotFoundException> sınıfı).  
  
-   Yalnızca bir iki nokta üst üste yoludur ":" (<xref:System.NotSupportedException> sınıfı).  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Dosya adına dayanarak dosyanın içeriği ile ilgili kararlar vermeyin. Örneğin, dosya Form1.vb bir Visual Basic kaynak dosyası olmayabilir. Verileri uygulamanızda kullanmadan önce tüm girişleri doğrulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>  
 [Nasıl yapılır: bir Windows formdan ses çalma](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [SoundPlayer sınıfına genel bakış](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
