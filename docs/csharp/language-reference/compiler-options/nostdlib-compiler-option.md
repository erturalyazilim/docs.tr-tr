---
title: "-nostdlib (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="nostdlib-c-compiler-options"></a>/nostdlib (C# Derleyici Seçenekleri)
**/ nostdlib** tüm sistem ad alanını tanımlayan mscorlib.dll alma engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tanımlayın veya kendi sistem ad alanı ve nesneleri oluşturmak istiyorsanız bu seçeneği kullanın.  
  
 Belirtmezseniz, **/nostdlib**, mscorlib.dll programınıza içeri aktarılacak (belirtme aynı **/nostdlib-**). Belirtme **/nostdlib** belirtme aynı **/nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Açık **özellikleri** projesi için sayfa.  
  
2.  Tıklatın **yapı** Özellikler sayfası.  
  
3.  Tıklatın **Gelişmiş** düğmesi.  
  
4.  Değiştirme **mscorlib.dll başvurmadığından** özelliği.  
  
 Bu derleyici seçeneği programlı olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)
