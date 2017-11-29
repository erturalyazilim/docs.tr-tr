---
title: "&gt;İşleci (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc7c173ecc97bd3ca3b76a92ccbabc0f40062ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="c8c6c-102">&gt;İşleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="c8c6c-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="c8c6c-103">Tüm sayısal ve numaralandırma türlerinin bir "büyüktür" ilişkisel işleci tanımlama (`>`) döndüren `true` ilk işlenen saniyeden büyükse, `false` Aksi takdirde.</span><span class="sxs-lookup"><span data-stu-id="c8c6c-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8c6c-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c8c6c-104">Remarks</span></span>  
 <span data-ttu-id="c8c6c-105">Kullanıcı tanımlı türler aşırı yükleme `>` işleci (bkz [işleci](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c8c6c-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c8c6c-106">Varsa `>` aşırı yüklendi [ < ](../../../csharp/language-reference/operators/less-than-operator.md) da aşırı yüklenmiş gerekir.</span><span class="sxs-lookup"><span data-stu-id="c8c6c-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="c8c6c-107">İkili İşleç aşırı, karşılık gelen atama işleci varsa, aynı zamanda örtük olarak aşırı yüklü değildir.</span><span class="sxs-lookup"><span data-stu-id="c8c6c-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8c6c-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="c8c6c-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c8c6c-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c8c6c-109">See Also</span></span>  
 [<span data-ttu-id="c8c6c-110">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="c8c6c-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c8c6c-111">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="c8c6c-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c8c6c-112">C# işleçleri</span><span class="sxs-lookup"><span data-stu-id="c8c6c-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="c8c6c-113">açık</span><span class="sxs-lookup"><span data-stu-id="c8c6c-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)