---
title: Visual Basic'de Me, My, MyBase ve MyClass
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bebf404cd65d1b3a2c4059d3a7c986f0157dfe2d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic'de Me, My, MyBase ve MyClass
`Me`, `My`, `MyBase`, ve `MyClass` içinde [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] adlarının benzer ancak farklı amaçlar. Bu konuda bunları ayırt etmek için bunların her biri açıklanmaktadır.  
  
## <a name="me"></a>Beni  
 `Me` Anahtar sözcüğü bir sınıf veya yapı içinde kod şu anda yürütülmekte olan belirli örneğine başvurmak için bir yol sağlar. `Me`bir nesne değişkeni veya geçerli örneğine başvurma yapısı değişkeni gibi davranır. Kullanarak `Me` başka bir sınıf, yapı veya modülü bir yordam için bir sınıf veya yapı şu anda yürütülen örneği hakkında bilgi geçirme özellikle yararlıdır.  
  
 Örneğin, aşağıdaki yordamda bir modülde olduğunu varsayalım.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Bu yordam çağrısı ve geçerli örneği geçirin <xref:System.Windows.Forms.Form> şu deyimi kullanarak bağımsız değişken olarak sınıfı.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>Benim  
 `My` Özelliği için bir dizi kolay ve sezgisel erişim sağlar [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] etkinleştirme sınıfları [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bilgisayar, uygulama, ayarları, kaynaklar vb. ile etkileşim kurmak için kullanıcı.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` Anahtar sözcüğü sınıfının geçerli örneği için temel sınıf başvuran bir nesne değişkeni gibi davranır. `MyBase`yaygın olarak geçersiz kılınan veya türetilen bir sınıfta gölgeli taban sınıfı üyeleri erişmek için kullanılır. `MyBase.New`bir temel sınıf oluşturucu türetilmiş bir sınıf oluşturucudan açıkça çağırmak için kullanılır.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` Anahtar sözcüğü olarak ilk olarak uygulanan sınıfının geçerli örneği başvuran bir nesne değişkeni gibi davranır. `MyClass`benzer `Me`, ancak yöntemi değilmiş gibi onu tüm yöntemi çağrılarını kabul edilir `NotOverridable`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devralma temelleri](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
