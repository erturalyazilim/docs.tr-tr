---
title: "Karar Yapıları (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38820b6ca0a8f716dcaa28644bb25eb4899bd511
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="0cbda-102">Karar Yapıları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cbda-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="0cbda-103">koşullarda test ve test sonuçlarını bağlı olarak farklı işlemler gerçekleştirmek olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="0cbda-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="0cbda-104">True veya false ifade çeşitli değerleri için veya bir dizi deyimi yürüttüğünüzde oluşturulan çeşitli özel durumlar için olan bir koşul için test edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cbda-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="0cbda-105">Aşağıdaki çizimde, true olan bir koşulu sınar ve doğru veya yanlış olmasına bağlı olarak farklı eylemleri gerçekleştirir karar yapısını gösterir.</span><span class="sxs-lookup"><span data-stu-id="0cbda-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="0cbda-106">![Akış Çizelgesi bir if... Then... Else yapım](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="0cbda-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="0cbda-107">Bir koşul true ve false olduğunda olduğunda farklı eylemler alma</span><span class="sxs-lookup"><span data-stu-id="0cbda-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="0cbda-108">If... Then... Else yapımı</span><span class="sxs-lookup"><span data-stu-id="0cbda-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="0cbda-109">`If...Then...Else`kurulumlarını için bir veya daha fazla koşullarda test ve her koşul bağlı olarak bir veya daha fazla deyimleri çalıştırmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="0cbda-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="0cbda-110">Koşullarda test ve aşağıdaki yollarla eylemleri gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="0cbda-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="0cbda-111">Bir koşul ise, bir veya daha fazla deyimlerini çalıştırın`True`</span><span class="sxs-lookup"><span data-stu-id="0cbda-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="0cbda-112">Bir koşul ise, bir veya daha fazla deyimlerini çalıştırın`False`</span><span class="sxs-lookup"><span data-stu-id="0cbda-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="0cbda-113">Bir koşul ise, bazı deyimleri çalıştırmak `True` ve diğerleri etkinleştirilmişse`False`</span><span class="sxs-lookup"><span data-stu-id="0cbda-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="0cbda-114">Önceki bir koşul ise, ek bir koşulu test`False`</span><span class="sxs-lookup"><span data-stu-id="0cbda-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="0cbda-115">Bu olanakları sunar denetim yapısı [varsa... Then... Else deyimi](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0cbda-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="0cbda-116">Yalnızca bir test ve çalıştırmak için bir deyim varsa tek satırlı sürüm kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cbda-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="0cbda-117">Koşullar ve Eylemler daha karmaşık bir dizi varsa, birden çok satır sürümü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cbda-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="0cbda-118">Seçin... Örnek oluşturma</span><span class="sxs-lookup"><span data-stu-id="0cbda-118">Select...Case Construction</span></span>  
 <span data-ttu-id="0cbda-119">`Select...Case` Yapım bir ifadenin bir kez değerlendirmek ve çalışma farklı olası değerlerine göre deyimlerinin farklı ayarlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="0cbda-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="0cbda-120">Daha fazla bilgi için bkz: [seçin... Case deyimi](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0cbda-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="0cbda-121">Try... Catch... Son olarak oluşturma</span><span class="sxs-lookup"><span data-stu-id="0cbda-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="0cbda-122">`Try...Catch...Finally`kurulumlarını deyimleri altında bir özel durum, deyimleri herhangi biri neden olursa, Denetim korur bir ortam kümesi çalıştırmanıza izin.</span><span class="sxs-lookup"><span data-stu-id="0cbda-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="0cbda-123">Farklı özel durumlar için farklı işlemler yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0cbda-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="0cbda-124">İsteğe bağlı olarak tüm çıkmadan önce çalışan bir kod bloğunu belirtebilirsiniz `Try...Catch...Finally` neler bağımsız olarak oluşturma.</span><span class="sxs-lookup"><span data-stu-id="0cbda-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="0cbda-125">Daha fazla bilgi için bkz: [deneyin... Catch... Finally ifadesi](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0cbda-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cbda-126">Bir anahtar sözcüğü tıklattığınızda birçok denetim yapıları için tüm anahtar sözcükleri yapısında vurgulanır.</span><span class="sxs-lookup"><span data-stu-id="0cbda-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="0cbda-127">Örneği için tıkladığınızda `If` içinde bir `If...Then...Else` yapım, tüm örneklerini `If`, `Then`, `ElseIf`, `Else`, ve `End If` yapısında vurgulanır.</span><span class="sxs-lookup"><span data-stu-id="0cbda-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="0cbda-128">Sonraki veya önceki vurgulanan anahtar sözcüğe taşımak için CTRL + SHIFT + Aşağı Ok veya CTRL + SHIFT + Yukarı Ok tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="0cbda-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbda-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0cbda-129">See Also</span></span>  
 [<span data-ttu-id="0cbda-130">Denetim akışı</span><span class="sxs-lookup"><span data-stu-id="0cbda-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="0cbda-131">Döngü yapıları</span><span class="sxs-lookup"><span data-stu-id="0cbda-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="0cbda-132">Diğer denetim yapıları</span><span class="sxs-lookup"><span data-stu-id="0cbda-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="0cbda-133">İç içe geçmiş denetim yapıları</span><span class="sxs-lookup"><span data-stu-id="0cbda-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="0cbda-134">Varsa işleci</span><span class="sxs-lookup"><span data-stu-id="0cbda-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)