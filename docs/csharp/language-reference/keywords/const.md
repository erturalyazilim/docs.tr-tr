---
title: "const (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords: const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f54b686b170622ca1ead736a9f614c9bbef52dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="const-c-reference"></a>const (C# Başvurusu)
Kullandığınız `const` sabit bir alan veya sabit bir yerel bildirmek için anahtar sözcüğü. Sabit alanları ve yerel değişkenleri değil ve değiştirilemeyebilir. Sabitler numaraları, Boole değerleri, dize veya null bir başvuru olabilir. Herhangi bir zamanda değiştirmeniz beklediğiniz bilgileri temsil eden bir sabit oluşturmayın. Örneğin, sabit bir alan, bir hizmet, bir ürün sürüm numarası veya bir şirket markası adını fiyat depolamak için kullanmayın. Zaman içinde bu değerleri değiştirebilirsiniz ve derleyicileri sabitleri yayıldığından Kitaplıklarınızı ile derlenen diğer kod değişiklikleri görmek için derlenmesi gerekir. Ayrıca bkz. [readonly](../../../csharp/language-reference/keywords/readonly.md) anahtar sözcüğü. Örneğin:  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sabit bildiriminde türü bildirimi tanıtır üyeleri türünü belirtir. Yerel bir sabit Başlatıcı veya sabit bir alan için hedef türü örtük olarak dönüştürülebilir sabit bir ifade olması gerekir.  
  
 Bir sabit ifadesine derleme zamanında tam olarak değerlendirilecek bir ifade değil. Başvuru türleri sabitleri için bu nedenle, yalnızca olası değerler `string` ve bir null başvuru.  
  
 Sabit bildiriminde birden çok sabitleri gibi bildirebilirsiniz:  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 `static` Değiştiricisi Sabit bildiriminde izin verilmez.  
  
 Bir sabit bir sabit ifadesine gibi katılabilmesi için:  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  [Readonly](../../../csharp/language-reference/keywords/readonly.md) anahtar sözcüğü farklı olarak `const` anahtar sözcüğü. A `const` alan alan bildirimi sırasında yalnızca başlatılabilir. A `readonly` bildirimi sırasında veya bir oluşturucuya alan başlatılabilir. Bu nedenle, `readonly` alanları kullanılan Oluşturucusu bağlı olarak farklı değerlere sahip olabilir. Ayrıca, ancak bir `const` alandır derleme zamanı sabiti `readonly` alan, bu satırı olduğu gibi çalışma zamanı sabitleri için kullanılabilir:`public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a>Örnek  
 Bu örnek, yerel değişkenleri olarak sabitleri kullanımı gösterilmiştir.  
  
 [!code-csharp[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [C# anahtar sözcükleri](../../../csharp/language-reference/keywords/index.md)  
 [Değiştiriciler](../../../csharp/language-reference/keywords/modifiers.md)  
 [salt okunur](../../../csharp/language-reference/keywords/readonly.md)
