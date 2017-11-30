---
title: "Nasıl yapılır: Olay İşleyicisi Çağırma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52b4b6ca8b03d8301535d6aeedc3bd0190d8527f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="4a246-102">Nasıl yapılır: Olay İşleyicisi Çağırma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a246-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="4a246-103">Bir *olay* bir eylem veya geçişi — fare gibi tıklatın ya da bir kredi sınırı aşıldı —, tanınmasını bazı programı bileşeni tarafından ve kod yazabilirsiniz yanıtlayın.</span><span class="sxs-lookup"><span data-stu-id="4a246-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="4a246-104">Bir *olay işleyicisi* bir olaya yanıt yazma kodudur.</span><span class="sxs-lookup"><span data-stu-id="4a246-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="4a246-105">Bir olay işleyicisi [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] olan bir `Sub` yordamı.</span><span class="sxs-lookup"><span data-stu-id="4a246-105">An event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="4a246-106">Ancak, normal olarak, aynı yolla diğer çağırmayın `Sub` yordamlar.</span><span class="sxs-lookup"><span data-stu-id="4a246-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="4a246-107">Bunun yerine, olay işleyicisi olarak yordamı tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="4a246-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="4a246-108">İle ya da bunu yapabilirsiniz bir [işleme](../../../../visual-basic/language-reference/statements/handles-clause.md) yan tümcesi ve [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) , değişken veya ile bir [AddHandler deyimi](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4a246-109">Kullanarak bir `Handles` yan tümcesi olan bir olay işleyici bildirmek için varsayılan yolu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a246-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="4a246-110">Tümleşik geliştirme ortamı (IDE) programı olduğunda olay işleyicileri tasarımcıları tarafından yazılan yolu budur.</span><span class="sxs-lookup"><span data-stu-id="4a246-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="4a246-111">`AddHandler` Açıklamadır olaylar dinamik olarak çalışma zamanında oluşturma için uygun.</span><span class="sxs-lookup"><span data-stu-id="4a246-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="4a246-112">Olay ortaya çıktığında [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] otomatik olarak olay işleyicisi yordamı çağırır.</span><span class="sxs-lookup"><span data-stu-id="4a246-112">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="4a246-113">Olay erişimi olan herhangi bir kod yürüterek oluşmasına neden bir [RaiseEvent deyimi](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="4a246-114">Birden fazla olay işleyicisi aynı olay ile ilişkilendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4a246-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="4a246-115">Bazı durumlarda bir olay işleyiciden ilişkisini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="4a246-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="4a246-116">Daha fazla bilgi için bkz: [olayları](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="4a246-117">İşler ve WithEvents kullanarak bir olay işleyicisi çağırmak için</span><span class="sxs-lookup"><span data-stu-id="4a246-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="4a246-118">Emin olun olay ile bildirilmiş bir [Event deyimi](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="4a246-119">Bir nesne değişkeni modülü veya sınıfı kullanarak düzeyi bildirme [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="4a246-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="4a246-120">`As` Yan tümcesi bu değişken için olayını sınıfı belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4a246-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="4a246-121">Olay işleme bildiriminde `Sub` yordamı, ekleme bir [işleme](../../../../visual-basic/language-reference/statements/handles-clause.md) belirten yan tümcesi `WithEvents` değişkeni ve olay adı.</span><span class="sxs-lookup"><span data-stu-id="4a246-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="4a246-122">Olay ortaya çıktığında [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] otomatik olarak çağırır `Sub` yordamı.</span><span class="sxs-lookup"><span data-stu-id="4a246-122">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4a246-123">Kodunuzu kullanabilirsiniz bir `RaiseEvent` ortaya olay yapmak için deyimi.</span><span class="sxs-lookup"><span data-stu-id="4a246-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4a246-124">Aşağıdaki örnek, bir olay tanımlar ve `WithEvents` olayını sınıfına başvuruyor değişkeni.</span><span class="sxs-lookup"><span data-stu-id="4a246-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="4a246-125">Olay işleme `Sub` yordamı kullanan bir `Handles` yan tümcesini sınıfı ve bunu işleyen olayı belirtin.</span><span class="sxs-lookup"><span data-stu-id="4a246-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="4a246-126">AddHandler kullanarak bir olay işleyicisi çağırmak için</span><span class="sxs-lookup"><span data-stu-id="4a246-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="4a246-127">Emin olun olay ile bildirilmiş bir `Event` deyimi.</span><span class="sxs-lookup"><span data-stu-id="4a246-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="4a246-128">Yürütme bir [AddHandler deyimi](../../../../visual-basic/language-reference/statements/addhandler-statement.md) olay işleme dinamik olarak bağlanmak için `Sub` olay yordamı.</span><span class="sxs-lookup"><span data-stu-id="4a246-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="4a246-129">Olay ortaya çıktığında [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] otomatik olarak çağırır `Sub` yordamı.</span><span class="sxs-lookup"><span data-stu-id="4a246-129">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4a246-130">Kodunuzu kullanabilirsiniz bir `RaiseEvent` ortaya olay yapmak için deyimi.</span><span class="sxs-lookup"><span data-stu-id="4a246-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4a246-131">Aşağıdaki örnek tanımlayan bir `Sub` işlemek için yordamına <xref:System.Windows.Forms.Form.Closing> olay bir biçimde.</span><span class="sxs-lookup"><span data-stu-id="4a246-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="4a246-132">Daha sonra kullanır [AddHandler deyimi](../../../../visual-basic/language-reference/statements/addhandler-statement.md) ilişkilendirilecek `catchClose` yordamı için bir olay işleyicisi olarak <xref:System.Windows.Forms.Form.Closing>.</span><span class="sxs-lookup"><span data-stu-id="4a246-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="4a246-133">Bir olay Olay işleyiciden yürüterek ilişkisini [RemoveHandler deyimi](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a246-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4a246-134">See Also</span></span>  
 [<span data-ttu-id="4a246-135">Yordamları</span><span class="sxs-lookup"><span data-stu-id="4a246-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4a246-136">Alt yordamlar</span><span class="sxs-lookup"><span data-stu-id="4a246-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="4a246-137">Sub deyimi</span><span class="sxs-lookup"><span data-stu-id="4a246-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="4a246-138">AddressOf işleci</span><span class="sxs-lookup"><span data-stu-id="4a246-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="4a246-139">Nasıl yapılır: bir yordam oluşturma</span><span class="sxs-lookup"><span data-stu-id="4a246-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="4a246-140">Nasıl yapılır: bir değer döndürmeyen bir yordam çağırma</span><span class="sxs-lookup"><span data-stu-id="4a246-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)