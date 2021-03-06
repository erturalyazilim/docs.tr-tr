---
title: Option Explicit Deyimi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d39b3d7cf5096e3b263938d32e017eae5708e042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit Deyimi (Visual Basic)
Bir dosyadaki tüm değişkenlerin açıkça bildirilmesini zorlar veya değişkenlerin örtük bildirimleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Bölümler  
 `On`  
 İsteğe bağlı. Etkinleştirir `Option Explicit` denetleniyor. Varsa `On` veya `Off` belirtilmezse, varsayılan `On`.  
  
 `Off`  
 İsteğe bağlı. Devre dışı bırakır `Option Explicit` denetleniyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman `Option Explicit On` veya `Option Explicit` görünür bir dosyada, açıkça bildirmelidir tüm değişkenleri kullanarak `Dim` veya `ReDim` deyimleri. Bildirilmemiş bir değişken adı kullanmayı denerseniz, derleme zamanı sırasında bir hata oluşur. `Option Explicit Off` Deyimi değişkenlerin örtük bildirimi sağlar.  
  
 Kullandıysanız, `Option Explicit` ifadesi, başka bir kaynak kod deyimleri önce bir dosyada görünmelidir.  
  
> [!NOTE]
>  Ayarı `Option Explicit` için `Off` genellikle iyi bir uygulama değildir. Bir değişken adı konumlarda programını çalıştırdığınızda, beklenmeyen sonuçlara neden olacağından bir veya daha fazla hata hatalı.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Ne zaman Option Explicit deyimi mevcut değil  
 Kaynak kodu içermiyorsa bir `Option Explicit` deyimi, **Option Explicit** ayarı [derleme sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) kullanılır. Komut satırı derleyicisi kullanılırsa, [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) derleyici seçeneği kullanılır.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Option Explicit IDE'de ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, bir proje seçin. Üzerinde **proje** menüsünde tıklatın **özellikleri**. Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Tıklatın **derleme** sekmesi.  
  
3.  Değer kümesinde **Option Explicit** kutusu.  
  
 Yeni bir proje oluşturduğunuzda **Option Explicit** ayarı **derleme** sekmesini ayarlanmış **Option Explicit** ayarı **VB varsayılanları**iletişim kutusu. Erişim için **VB varsayılan olarak** iletişim kutusundaki **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarı **VB varsayılanları** olan `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Option Explicit komut satırında ayarlamak için  
  
-   Dahil [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) derleyici seçeneği **vbc** komutu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Option Explicit` tüm değişkenlerin açıkça bildirilmesini zorlamak için deyimi. Bildirilmemiş bir değişkeni kullanılmaya çalışılıyor derleme zamanında bir hataya neden olur.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dim deyimi](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim deyimi](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Compare deyimi](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Strict deyimi](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Visual Basic Varsayılanları, projeler, Seçenekler iletişim kutusu](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
