---
title: "Nasıl yapılır: Yapı Geçirme ile Metoda Sınıf Başvurusu Geçirme Arasındaki Farkı Bilme (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: "25"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b989c3cefe72c6c17d10dd91005dcecbfc84e389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a><span data-ttu-id="8e328-102">Nasıl yapılır: Yapı Geçirme ile Metoda Sınıf Başvurusu Geçirme Arasındaki Farkı Bilme (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="8e328-102">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method (C# Programming Guide)</span></span>
<span data-ttu-id="8e328-103">Aşağıdaki örnekte nasıl geçirme gösteren bir [yapısı](../../../csharp/language-reference/keywords/struct.md) bir yönteme geçirme öğesinden farklı bir [sınıfı](../../../csharp/language-reference/keywords/class.md) bir yönteme örnek.</span><span class="sxs-lookup"><span data-stu-id="8e328-103">The following example demonstrates how passing a [struct](../../../csharp/language-reference/keywords/struct.md) to a method differs from passing a [class](../../../csharp/language-reference/keywords/class.md) instance to a method.</span></span> <span data-ttu-id="8e328-104">Örnekte, bağımsız değişkenler (yapısı ve sınıf örneği) her ikisi de değeriyle geçirilir ve her iki yöntem bağımsız değişkeninin bir alanın değerini değiştirin.</span><span class="sxs-lookup"><span data-stu-id="8e328-104">In the example, both of the arguments (struct and class instance) are passed by value, and both methods change the value of one field of the argument.</span></span> <span data-ttu-id="8e328-105">Yapı geçirdiğinizde ne geçirilen bir sınıfın örneğini geçirdiğinizde ne geçirilen gelen değiştiğinden ancak, iki yöntem sonuçlarını aynı değildir.</span><span class="sxs-lookup"><span data-stu-id="8e328-105">However, the results of the two methods are not the same because what is passed when you pass a struct differs from what is passed when you pass an instance of a class.</span></span>  
  
 <span data-ttu-id="8e328-106">Bir yapı olduğundan bir [değer türü](../../../csharp/language-reference/keywords/value-types.md), ne zaman, [yapı değeriyle geçirmek](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) bir yöntem için yöntemi alır ve yapı bağımsız değişkeni bir kopyası üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="8e328-106">Because a struct is a [value type](../../../csharp/language-reference/keywords/value-types.md), when you [pass a struct by value](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) to a method, the method receives and operates on a copy of the struct argument.</span></span> <span data-ttu-id="8e328-107">Yöntemi arama yönteminde özgün yapısı hiçbir erişimi vardır ve bu nedenle herhangi bir şekilde değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e328-107">The method has no access to the original struct in the calling method and therefore can't change it in any way.</span></span> <span data-ttu-id="8e328-108">Yöntem yalnızca kopya değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e328-108">The method can change only the copy.</span></span>  
  
 <span data-ttu-id="8e328-109">Sınıf örneği bir [başvuru türüne](../../../csharp/language-reference/keywords/reference-types.md), değer türü.</span><span class="sxs-lookup"><span data-stu-id="8e328-109">A class instance is a [reference type](../../../csharp/language-reference/keywords/reference-types.md), not a value type.</span></span> <span data-ttu-id="8e328-110">Zaman [bir başvuru türü değeri tarafından geçirilen](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) bir yönteme yöntemi sınıf örneği referansı kopyasını alır.</span><span class="sxs-lookup"><span data-stu-id="8e328-110">When [a reference type is passed by value](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) to a method, the method receives a copy of the reference to the class instance.</span></span> <span data-ttu-id="8e328-111">Diğer bir deyişle, yöntem adresi olmayan örneğin kopyası örneğinin bir kopyasını alır.</span><span class="sxs-lookup"><span data-stu-id="8e328-111">That is, the method receives a copy of the address of the instance, not a copy of the instance itself.</span></span> <span data-ttu-id="8e328-112">Arama yönteminde sınıf örneği bir adresi olduğundan, çağrılan yöntem parametresinde adresi bir kopyası bulunur ve her iki adres aynı nesneye başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="8e328-112">The class instance in the calling method has an address, the parameter in the called method has a copy of the address, and both addresses refer to the same object.</span></span> <span data-ttu-id="8e328-113">Parametresi yalnızca bir kopya adresinin içerdiğinden, çağrılan yöntemin arama yönteminde sınıf örneğinin adresi değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e328-113">Because the parameter contains only a copy of the address, the called method cannot change the address of the class instance in the calling method.</span></span> <span data-ttu-id="8e328-114">Ancak, çağrılan yöntemin adresi özgün adresini ve kopya başvuru sınıf üyeleri erişmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e328-114">However, the called method can use the address to access the class members that both the original address and the copy reference.</span></span> <span data-ttu-id="8e328-115">Çağrılan yöntemi bir sınıf üyesi değişirse, özgün sınıf örneği arama yönteminde da değişir.</span><span class="sxs-lookup"><span data-stu-id="8e328-115">If the called method changes a class member, the original class instance in the calling method also changes.</span></span>  
  
 <span data-ttu-id="8e328-116">Aşağıdaki örnek çıkış fark gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="8e328-116">The output of the following example illustrates the difference.</span></span> <span data-ttu-id="8e328-117">Değeri `willIChange` alan sınıf örneğinin yöntemine yönelik çağrı değiştiren `ClassTaker` yöntemi adresi parametresinde belirtilen alanın sınıf örneğinin bulmak için kullandığından.</span><span class="sxs-lookup"><span data-stu-id="8e328-117">The value of the `willIChange` field of the class instance is changed by the call to method `ClassTaker` because the method uses the address in the parameter to find the specified field of the class instance.</span></span> <span data-ttu-id="8e328-118">`willIChange` Arama yöntemi yapıda alanının, yöntem çağrısı değişmez `StructTaker` bağımsız değişkeninin değeri yapısı kendisini adresini değil bir kopyasını bir kopyası olduğundan.</span><span class="sxs-lookup"><span data-stu-id="8e328-118">The `willIChange` field of the struct in the calling method is not changed by the call to method `StructTaker` because the value of the argument is a copy of the struct itself, not a copy of its address.</span></span> <span data-ttu-id="8e328-119">`StructTaker`kopyalama ve kopyalama kayboluyor ne zaman değişiklikleri çağrısı `StructTaker` tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="8e328-119">`StructTaker` changes the copy, and the copy is lost when the call to `StructTaker` is completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e328-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="8e328-120">Example</span></span>  
 [!code-csharp[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8e328-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8e328-121">See Also</span></span>  
 [<span data-ttu-id="8e328-122">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="8e328-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e328-123">Sınıfları</span><span class="sxs-lookup"><span data-stu-id="8e328-123">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="8e328-124">Yapılar</span><span class="sxs-lookup"><span data-stu-id="8e328-124">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="8e328-125">Parametreleri geçirme</span><span class="sxs-lookup"><span data-stu-id="8e328-125">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)