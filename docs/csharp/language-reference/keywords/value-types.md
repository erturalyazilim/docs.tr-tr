---
title: "Değer Türleri (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 281b811f2a8a1f2c364405b563f9f103899b492c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-c-reference"></a><span data-ttu-id="80f7b-102">Değer Türleri (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="80f7b-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="80f7b-103">Değer türleri iki ana kategoriye oluşur:</span><span class="sxs-lookup"><span data-stu-id="80f7b-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="80f7b-104">Yapılar</span><span class="sxs-lookup"><span data-stu-id="80f7b-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="80f7b-105">Numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="80f7b-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="80f7b-106">Yapılar kategorileri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="80f7b-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="80f7b-107">Sayısal türler</span><span class="sxs-lookup"><span data-stu-id="80f7b-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="80f7b-108">Tam sayı türleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="80f7b-109">Kayan nokta türleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [<span data-ttu-id="80f7b-110">ondalık</span><span class="sxs-lookup"><span data-stu-id="80f7b-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [<span data-ttu-id="80f7b-111">bool</span><span class="sxs-lookup"><span data-stu-id="80f7b-111">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="80f7b-112">Kullanıcı tanımlı yapılar.</span><span class="sxs-lookup"><span data-stu-id="80f7b-112">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="80f7b-113">Değer türleri başlıca özellikleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-113">Main Features of Value Types</span></span>  
 <span data-ttu-id="80f7b-114">Değer türleri üzerinde doğrudan bağlı değişkenlerin değerlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="80f7b-114">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="80f7b-115">Bir değer türü değişkeni kapsanan değeri için başka bir kopya atama.</span><span class="sxs-lookup"><span data-stu-id="80f7b-115">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="80f7b-116">Bu nesne, ancak nesnenin kendisini değil bir başvuru kopyaladığı atama başvuru türü değişkenlerin farklıdır.</span><span class="sxs-lookup"><span data-stu-id="80f7b-116">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="80f7b-117">Tüm değer türlerini örtük olarak türetilmiş <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80f7b-117">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="80f7b-118">Farklı olarak başvuru türleri ile yeni bir tür değeri türünden türetilemez.</span><span class="sxs-lookup"><span data-stu-id="80f7b-118">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="80f7b-119">Ancak, başvuru türleri, ister yapılar arabirimleri uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80f7b-119">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="80f7b-120">Başvuru türlerinin aksine, bir değer türü içeremez `null` değeri.</span><span class="sxs-lookup"><span data-stu-id="80f7b-120">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="80f7b-121">Ancak, [boş değer atanabilir türler](../../../csharp/programming-guide/nullable-types/index.md) özelliğinin izin atanacak değer türleri için `null`.</span><span class="sxs-lookup"><span data-stu-id="80f7b-121">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="80f7b-122">Her değer türünün varsayılan değer bu tür başlatır bir örtük varsayılan oluşturucusu vardır.</span><span class="sxs-lookup"><span data-stu-id="80f7b-122">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="80f7b-123">Değer türleri varsayılan değerleri hakkında daha fazla bilgi için bkz: [varsayılan değerler tablosu](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="80f7b-123">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="80f7b-124">Basit türler başlıca özellikleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-124">Main Features of Simple Types</span></span>  
 <span data-ttu-id="80f7b-125">Tüm basit türleri--C# dili bu sayıya--, .NET Framework sistem türlerinin adlardır.</span><span class="sxs-lookup"><span data-stu-id="80f7b-125">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="80f7b-126">Örneğin, [int](../../../csharp/language-reference/keywords/int.md) bir diğer adı <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80f7b-126">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="80f7b-127">Diğer adlar tam bir listesi için bkz: [yerleşik türler tablosu](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="80f7b-127">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="80f7b-128">Sabit ifadeler, işlenenleri tüm basit tür sabittir, derleme zamanında değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="80f7b-128">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="80f7b-129">Değişmez değerler kullanarak basit türler başlatılabilir.</span><span class="sxs-lookup"><span data-stu-id="80f7b-129">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="80f7b-130">Örneğin, 'A' türündeki bir hazır değer olan `char` ve 2001 değişmez değer türü `int`.</span><span class="sxs-lookup"><span data-stu-id="80f7b-130">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="80f7b-131">Değer türleri başlatma</span><span class="sxs-lookup"><span data-stu-id="80f7b-131">Initializing Value Types</span></span>  
 <span data-ttu-id="80f7b-132">C# yerel değişkenler kullanıldıkları önce başlatılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="80f7b-132">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="80f7b-133">Örneğin, aşağıdaki örnekte olduğu gibi başlatma olmadan yerel bir değişken bildirin:</span><span class="sxs-lookup"><span data-stu-id="80f7b-133">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```  
int myInt;  
```  
  
 <span data-ttu-id="80f7b-134">Bunu başlatılmadan önce kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="80f7b-134">You cannot use it before you initialize it.</span></span> <span data-ttu-id="80f7b-135">Şu deyimi kullanarak başlatabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="80f7b-135">You can initialize it using the following statement:</span></span>  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="80f7b-136">Bu deyim şu deyimi eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="80f7b-136">This statement is equivalent to the following statement:</span></span>  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="80f7b-137">Doğal olarak, bildirim ve başlatma aşağıdaki örneklerde olduğu gibi aynı deyimde elinizde olabilir:</span><span class="sxs-lookup"><span data-stu-id="80f7b-137">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="80f7b-138">– veya –</span><span class="sxs-lookup"><span data-stu-id="80f7b-138">–or–</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="80f7b-139">Kullanarak [yeni](../../../csharp/language-reference/keywords/new.md) işleci belirli türdeki varsayılan oluşturucuyu çağırır ve varsayılan değer değişkenine atar.</span><span class="sxs-lookup"><span data-stu-id="80f7b-139">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="80f7b-140">Önceki örnekte, varsayılan oluşturucu değer atanmışsa `0` için `myInt`.</span><span class="sxs-lookup"><span data-stu-id="80f7b-140">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="80f7b-141">Varsayılan Oluşturucu çağırarak atanan değerler hakkında daha fazla bilgi için bkz: [varsayılan değerler tablosu](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="80f7b-141">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="80f7b-142">Kullanıcı tanımlı türler ile kullanmak [yeni](../../../csharp/language-reference/keywords/new.md) varsayılan oluşturucu çağrılamıyor.</span><span class="sxs-lookup"><span data-stu-id="80f7b-142">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="80f7b-143">Örneğin, aşağıdaki deyim, varsayılan oluşturucu çağırır `Point` yapısı:</span><span class="sxs-lookup"><span data-stu-id="80f7b-143">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="80f7b-144">Bu çağrısından sonra kesinlikle atanacak yapı olarak kabul edilir; diğer bir deyişle, tüm üyeleri varsayılan değerlerine başlatılır.</span><span class="sxs-lookup"><span data-stu-id="80f7b-144">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="80f7b-145">New işleci hakkında daha fazla bilgi için bkz: [yeni](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="80f7b-145">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="80f7b-146">Sayısal türler çıktısını biçimlendirme hakkında daha fazla bilgi için bkz: [sayısal sonuçlar tablosunu biçimlendirme](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="80f7b-146">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f7b-147">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="80f7b-147">See Also</span></span>  
 [<span data-ttu-id="80f7b-148">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="80f7b-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="80f7b-149">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="80f7b-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="80f7b-150">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="80f7b-151">Türler</span><span class="sxs-lookup"><span data-stu-id="80f7b-151">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="80f7b-152">Türler için başvuru tabloları</span><span class="sxs-lookup"><span data-stu-id="80f7b-152">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="80f7b-153">Başvuru türleri</span><span class="sxs-lookup"><span data-stu-id="80f7b-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)