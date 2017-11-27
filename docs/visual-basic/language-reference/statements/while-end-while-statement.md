---
title: While...End While Deyimi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f831f233eaa4f1c38d56f3a89bda9b0cf1bccaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="3ce8e-102">While...End While Deyimi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ce8e-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="3ce8e-103">Verilen bir koşul olduğu sürece bir dizi ifadeleri çalıştırır `True`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce8e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3ce8e-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="3ce8e-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="3ce8e-105">Parts</span></span>  
  
|<span data-ttu-id="3ce8e-106">Terim</span><span class="sxs-lookup"><span data-stu-id="3ce8e-106">Term</span></span>|<span data-ttu-id="3ce8e-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="3ce8e-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="3ce8e-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-108">Required.</span></span> <span data-ttu-id="3ce8e-109">`Boolean`ifade.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-109">`Boolean` expression.</span></span> <span data-ttu-id="3ce8e-110">Varsa `condition` olan `Nothing`, Visual Basic da işler `False`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="3ce8e-111">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-111">Optional.</span></span> <span data-ttu-id="3ce8e-112">Bir veya daha fazla deyimleri aşağıdaki `While`, her çalıştırma `condition` olan `True`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="3ce8e-113">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-113">Optional.</span></span> <span data-ttu-id="3ce8e-114">Sonraki yinelemesini denetim aktarır `While` bloğu.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="3ce8e-115">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-115">Optional.</span></span> <span data-ttu-id="3ce8e-116">Denetimin dışarı aktarır `While` bloğu.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="3ce8e-117">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-117">Required.</span></span> <span data-ttu-id="3ce8e-118">Tanımını sonlandırır `While` bloğu.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ce8e-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3ce8e-119">Remarks</span></span>  
 <span data-ttu-id="3ce8e-120">Kullanım bir `While...End While` yapısı deyimleri sonsuz numarası bir kez, bir dizi yinelenecek istediğinizde bir koşul devam ettiği sürece `True`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="3ce8e-121">Koşulu test burada veya ne sonuç daha fazla esneklik test, bu, tercih edebilirsiniz için istiyorsanız [yapın... Loop deyimi](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="3ce8e-122">İfadeler kümesi birkaç kez yineleyin istiyorsanız [için... Sonraki deyim](../../../visual-basic/language-reference/statements/for-next-statement.md) genellikle daha iyi bir seçimdir.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce8e-123">`While` Anahtar sözcüğü kullanılan de [yapın... Loop deyimi](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While tümcesi](../../../visual-basic/language-reference/queries/skip-while-clause.md) ve [Take While tümcesi](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="3ce8e-124">Varsa `condition` olan `True`, tüm, `statements` kadar çalışma `End While` deyimi karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="3ce8e-125">Denetim sonra geri döner `While` deyimi, ve `condition` yeniden teslim edilebilir.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="3ce8e-126">Varsa `condition` hala `True`, işlem tekrarlanır.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="3ce8e-127">Varsa `False`, Denetim geçişleri izleyen deyimine `End While` deyimi.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="3ce8e-128">`While` Döngü başlamadan önce koşul ifadesi her zaman denetler.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="3ce8e-129">Döngü koşulunu kalırken devam `True`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="3ce8e-130">Varsa `condition` olan `False` döngü ilk girdiğinizde bile bir kez çalıştırmaz.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="3ce8e-131">`condition` Genellikle bir karşılaştırma sonuçlarından iki değer, ancak veren herhangi bir ifade olabilir bir [Boole veri türü](../../../visual-basic/language-reference/data-types/boolean-data-type.md) değeri (`True` veya `False`).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="3ce8e-132">Bu ifade için dönüştürülen sayısal bir tür gibi başka bir veri türünde bir değer içerebilir `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="3ce8e-133">Geçirebilmenize `While` içinde başka bir döngü yerleştirerek döngüler.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="3ce8e-134">Ayrıca, değişik içinde bir diğer denetim yapıları yerleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="3ce8e-135">Daha fazla bilgi için bkz: [iç içe geçmiş denetim yapıları](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="3ce8e-136">Çıkış sırasında</span><span class="sxs-lookup"><span data-stu-id="3ce8e-136">Exit While</span></span>  
 <span data-ttu-id="3ce8e-137">[Çıkmak sırada](../../../visual-basic/language-reference/statements/exit-statement.md) deyimi, çıkmak için başka bir yol sağlayabilir bir `While` döngü.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="3ce8e-138">`Exit While`aşağıdaki deyim denetim hemen aktarır `End While` deyimi.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="3ce8e-139">Tipik olarak kullandığınız `Exit While` bazı koşul değerlendirildikten sonra (örneğin, bir `If...Then...Else` yapısı).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="3ce8e-140">Gereksiz veya hatalı bir değer veya bir sonlandırma isteği gibi yineleme devam mümkün kılan bir koşul algılama döngü çıkmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="3ce8e-141">Kullanabileceğiniz `Exit While` test zaman neden olabilecek bir koşul için bir *sonsuz bir döngüde*, bir son derece büyük ya da hatta sonsuz sayıda çalışacak bir döngü değil.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="3ce8e-142">Daha sonra kullanabilirsiniz `Exit While` döngü kaçınmak için.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="3ce8e-143">Herhangi bir sayıda yerleştirebilirsiniz `Exit While` deyimlerinde herhangi bir yere `While` döngü.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="3ce8e-144">Kullanıldığında içinde iç içe geçmiş `While` döngüler, `Exit While` denetimi en içteki döngü dışında ve iç içe geçme sonraki daha yüksek düzeyde uygulamasına aktarır.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="3ce8e-145">`Continue While` Deyimi hemen sonraki döngü için Denetim aktarır.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="3ce8e-146">Daha fazla bilgi için bkz: [devam deyimi](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3ce8e-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ce8e-147">Örnek</span><span class="sxs-lookup"><span data-stu-id="3ce8e-147">Example</span></span>  
 <span data-ttu-id="3ce8e-148">Aşağıdaki örnekte, döngü deyimlerinde kadar çalışmaya devam `index` değişkenidir 10'dan büyük.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3ce8e-149">Örnek</span><span class="sxs-lookup"><span data-stu-id="3ce8e-149">Example</span></span>  
 <span data-ttu-id="3ce8e-150">Aşağıdaki örnek kullanımını göstermektedir `Continue While` ve `Exit While` deyimleri.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="3ce8e-151">Örnek</span><span class="sxs-lookup"><span data-stu-id="3ce8e-151">Example</span></span>  
 <span data-ttu-id="3ce8e-152">Aşağıdaki örnek, bir metin dosyasındaki tüm satırları okur.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="3ce8e-153"><xref:System.IO.File.OpenText%2A> Yöntemi dosyayı açar ve döndürür bir <xref:System.IO.StreamReader> karakterleri okur.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="3ce8e-154">İçinde `While` koşulu <xref:System.IO.StreamReader.Peek%2A> yöntemi `StreamReader` dosyanın ek karakterler içerip içermediğini belirler.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3ce8e-155">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3ce8e-155">See Also</span></span>  
 [<span data-ttu-id="3ce8e-156">Döngü yapıları</span><span class="sxs-lookup"><span data-stu-id="3ce8e-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="3ce8e-157">Yapın... Loop deyimi</span><span class="sxs-lookup"><span data-stu-id="3ce8e-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="3ce8e-158">İçin... Sonraki deyim</span><span class="sxs-lookup"><span data-stu-id="3ce8e-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="3ce8e-159">Boole veri türü</span><span class="sxs-lookup"><span data-stu-id="3ce8e-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="3ce8e-160">İç içe geçmiş denetim yapıları</span><span class="sxs-lookup"><span data-stu-id="3ce8e-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="3ce8e-161">Exit deyimi</span><span class="sxs-lookup"><span data-stu-id="3ce8e-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="3ce8e-162">Continue deyimi</span><span class="sxs-lookup"><span data-stu-id="3ce8e-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)