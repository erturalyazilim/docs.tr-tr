---
title: "Yordam Parametreleri ve Bağımsız Değişkenler (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 726667950cfb227a0359bd6238c202883561749c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="86c57-102">Yordam Parametreleri ve Bağımsız Değişkenler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86c57-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="86c57-103">Çoğu durumda, bir yordam, onu çağrıldı koşullar hakkında bazı bilgiler gerekir.</span><span class="sxs-lookup"><span data-stu-id="86c57-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="86c57-104">Yinelenen veya paylaşılan görevleri gerçekleştiren bir yordam her çağrı için farklı bilgileri kullanır.</span><span class="sxs-lookup"><span data-stu-id="86c57-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="86c57-105">Bu bilgiler değişkenlerinin, sabitleri ve onu çağırdığınızda, yordama geçirdiğiniz ifadeler oluşur.</span><span class="sxs-lookup"><span data-stu-id="86c57-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="86c57-106">A *parametresi* yordamı, çağırdığınızda temin etmeniz bekliyor bir değeri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="86c57-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="86c57-107">Yordam bildirimi parametrelerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="86c57-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="86c57-108">Hiçbir parametre, bir parametre veya birden fazla ile bir yordam tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="86c57-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="86c57-109">Parametreleri belirtir yordamı tanımının bir parçası olarak adlandırılan *parametre listesi*.</span><span class="sxs-lookup"><span data-stu-id="86c57-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="86c57-110">Bir *bağımsız değişkeni* yordam çağrısı, sağladığınız değeri bir yordam parametresini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="86c57-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="86c57-111">Yordam çağrıları, çağrıyı yapan kod bağımsız değişkenler sağlar.</span><span class="sxs-lookup"><span data-stu-id="86c57-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="86c57-112">Bağımsız değişkenleri belirten yordam çağrısı parçası olarak adlandırılan *bağımsız değişken listesi*.</span><span class="sxs-lookup"><span data-stu-id="86c57-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="86c57-113">Yordamı çağırma kod aşağıda gösterilmiştir `safeSquareRoot` iki farklı yerde.</span><span class="sxs-lookup"><span data-stu-id="86c57-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="86c57-114">İlk çağrıda değişkenin değeri olarak geçirir `x` (4.0) parametresine `number`ve dönüş değeri `root` (2.0) değişkenine atanan `y`.</span><span class="sxs-lookup"><span data-stu-id="86c57-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="86c57-115">Değişmez değer 9.0 için ikinci çağrı geçirir `number`ve dönüş değeri (3.0) değişkenine atar `z`.</span><span class="sxs-lookup"><span data-stu-id="86c57-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="86c57-116">![Parametresi için bağımsız değişken geçirme grafik diyagramı](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="86c57-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="86c57-117">Bir parametre bağımsız değişken geçirme</span><span class="sxs-lookup"><span data-stu-id="86c57-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="86c57-118">Daha fazla bilgi için bkz: [arasındaki farklar parametreler ve bağımsız değişkenler](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="86c57-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="86c57-119">Parametre veri türü</span><span class="sxs-lookup"><span data-stu-id="86c57-119">Parameter Data Type</span></span>  
 <span data-ttu-id="86c57-120">Kullanarak bir veri türü için bir parametre tanımlayın `As` bildiriminden yan tümcesinde.</span><span class="sxs-lookup"><span data-stu-id="86c57-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="86c57-121">Örneğin, aşağıdaki işlev bir dize ve tamsayı kabul eder.</span><span class="sxs-lookup"><span data-stu-id="86c57-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="86c57-122">Tür denetleme geçiş yaparsanız ([Option Strict deyimi](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) olan `Off,` `As` yan tümcesi olduğunu isteğe bağlı, herhangi bir parametre kullanıyorsa, tüm parametreleri bunu kullanmalı dışında.</span><span class="sxs-lookup"><span data-stu-id="86c57-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="86c57-123">Tür denetleme ise `On`, `As` yan tümcesi tüm yordam parametreleri için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="86c57-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="86c57-124">Çağıran kodu bir bağımsız değişken bir veri türü, karşılık gelen bir parametre farklı gibi sağlayın bekliyor varsa `Byte` için bir `String` parametresi, aşağıdakilerden birini yapmalısınız:</span><span class="sxs-lookup"><span data-stu-id="86c57-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="86c57-125">Tedarik yalnızca bağımsız değişken parametre veri türü genişletmek veri türleriyle;</span><span class="sxs-lookup"><span data-stu-id="86c57-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="86c57-126">Ayarlama `Option Strict Off` örtük daraltma dönüşümleri; izin vermek veya</span><span class="sxs-lookup"><span data-stu-id="86c57-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="86c57-127">Dönüştürme anahtar sözcüğü açıkça veri türüne dönüştürmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="86c57-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="86c57-128">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="86c57-128">Type Parameters</span></span>  
 <span data-ttu-id="86c57-129">A *genel yordam* de bir veya daha fazla tanımlar *tür parametrelerindeki* normal parametrelerinin yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="86c57-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="86c57-130">Veri türleri farklı veri türleri tek tek her çağrı gereksinimlerini uyarlayabilirsiniz şekilde yordam çağrıları her zaman geçmesi için çağıran kodu genel bir yordam sağlar.</span><span class="sxs-lookup"><span data-stu-id="86c57-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="86c57-131">Bkz: [Visual Basic'de genel yordamlar](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="86c57-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c57-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="86c57-132">See Also</span></span>  
 [<span data-ttu-id="86c57-133">Yordamları</span><span class="sxs-lookup"><span data-stu-id="86c57-133">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="86c57-134">Alt yordamlar</span><span class="sxs-lookup"><span data-stu-id="86c57-134">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="86c57-135">İşlev yordamları</span><span class="sxs-lookup"><span data-stu-id="86c57-135">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="86c57-136">Özellik yordamları</span><span class="sxs-lookup"><span data-stu-id="86c57-136">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="86c57-137">İşleç yordamları</span><span class="sxs-lookup"><span data-stu-id="86c57-137">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="86c57-138">Nasıl yapılır: bir yordamın parametresini tanımlama</span><span class="sxs-lookup"><span data-stu-id="86c57-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="86c57-139">Nasıl yapılır: bir yordama bağımsız değişkenler geçirme</span><span class="sxs-lookup"><span data-stu-id="86c57-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="86c57-140">Bağımsız değişkenleri değere ve başvuruya göre geçirme</span><span class="sxs-lookup"><span data-stu-id="86c57-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="86c57-141">Yordam aşırı yüklemesi</span><span class="sxs-lookup"><span data-stu-id="86c57-141">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="86c57-142">Visual Basic'de tür dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="86c57-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)