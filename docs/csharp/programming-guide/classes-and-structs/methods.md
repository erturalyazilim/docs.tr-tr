---
title: "Yöntemler (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
caps.latest.revision: "41"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ff6e59f70a5718f6616fa9a585dd84144e1774a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="methods-c-programming-guide"></a><span data-ttu-id="99f9e-102">Yöntemler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="99f9e-102">Methods (C# Programming Guide)</span></span>
<span data-ttu-id="99f9e-103">Bir dizi deyimi içeren kod bloğu bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-103">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="99f9e-104">Bir program yöntemini çağırarak ve tüm gerekli yöntemi bağımsız değişkenleri belirtme yürütülecek deyimleri neden olur.</span><span class="sxs-lookup"><span data-stu-id="99f9e-104">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="99f9e-105">C# ' ta yürütülen her yönerge bir yöntem bağlamında gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-105">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="99f9e-106">Main yöntemi her C# uygulaması için giriş noktasıdır ve program başlatıldığında, ortak dil çalışma zamanı tarafından (CLR) adı verilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-106">The Main method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99f9e-107">Bu konu, adlandırılmış yöntemleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="99f9e-107">This topic discusses named methods.</span></span> <span data-ttu-id="99f9e-108">Anonim işlevler hakkında daha fazla bilgi için bkz: [anonim işlevler](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-108">For information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="method-signatures"></a><span data-ttu-id="99f9e-109">Yöntem imzaları</span><span class="sxs-lookup"><span data-stu-id="99f9e-109">Method Signatures</span></span>  
 <span data-ttu-id="99f9e-110">İçinde bildirilen yöntemleri bir [sınıfı](../../../csharp/language-reference/keywords/class.md) veya [yapısı](../../../csharp/language-reference/keywords/struct.md) erişim düzeyini gibi belirterek `public` veya `private`, isteğe bağlı değiştiricileri gibi `abstract` veya `sealed`, dönüş değer, yöntemi ve herhangi bir yöntem parametre adı.</span><span class="sxs-lookup"><span data-stu-id="99f9e-110">Methods are declared in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) by specifying the access level such as `public` or `private`, optional modifiers such as `abstract` or `sealed`, the return value, the name of the method, and any method parameters.</span></span> <span data-ttu-id="99f9e-111">Bu bölümleri yöntemi imzası birleştirilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-111">These parts together are the signature of the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99f9e-112">Bir yöntemin dönüş türü yöntemi için yöntem aşırı yükleme amacıyla imza parçası değil.</span><span class="sxs-lookup"><span data-stu-id="99f9e-112">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="99f9e-113">Ancak, bir temsilci ve işaret yöntemi uyumluluğu belirlerken yöntemi imzası parçası olan.</span><span class="sxs-lookup"><span data-stu-id="99f9e-113">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>  
  
 <span data-ttu-id="99f9e-114">Yöntem parametreleri parantez içine alınmış ve virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-114">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="99f9e-115">Boş parantez yöntemi hiçbir parametre gerektirmiyor gösterir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-115">Empty parentheses indicate that the method requires no parameters.</span></span> <span data-ttu-id="99f9e-116">Bu sınıf, üç yöntem içerir:</span><span class="sxs-lookup"><span data-stu-id="99f9e-116">This class contains three methods:</span></span>  
  
 [!code-csharp[csProgGuideObjects#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_1.cs)]  
  
## <a name="method-access"></a><span data-ttu-id="99f9e-117">Yöntem erişimi</span><span class="sxs-lookup"><span data-stu-id="99f9e-117">Method Access</span></span>  
 <span data-ttu-id="99f9e-118">Bir nesne üzerinde bir yöntemi çağırmak için bir alan erişim gibi olur.</span><span class="sxs-lookup"><span data-stu-id="99f9e-118">Calling a method on an object is like accessing a field.</span></span> <span data-ttu-id="99f9e-119">Nesne adından sonra bir süre, yöntemi ve parantez adını ekleyin.</span><span class="sxs-lookup"><span data-stu-id="99f9e-119">After the object name, add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="99f9e-120">Bağımsız değişkenler ayraç içinde listelenmiştir ve virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-120">Arguments are listed within the parentheses, and are separated by commas.</span></span> <span data-ttu-id="99f9e-121">Yöntemlerinin `Motorcycle` sınıfı bu nedenle aşağıdaki örnekteki çağrılabilir:</span><span class="sxs-lookup"><span data-stu-id="99f9e-121">The methods of the `Motorcycle` class can therefore be called as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_2.cs)]  
  
## <a name="method-parameters-vs-arguments"></a><span data-ttu-id="99f9e-122">Yöntem parametreleri vs. Arguments</span><span class="sxs-lookup"><span data-stu-id="99f9e-122">Method Parameters vs. Arguments</span></span>  
 <span data-ttu-id="99f9e-123">Yöntem tanımı adlarını ve gerekli olan herhangi bir parametre türlerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-123">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="99f9e-124">Kod çağrıları yöntemi çağrılırken, her parametre için bağımsız değişken olarak adlandırılan somut değerleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="99f9e-124">When calling code calls the method, it provides concrete values called arguments for each parameter.</span></span> <span data-ttu-id="99f9e-125">Bağımsız değişken parametre türü ile uyumlu olması gerekir, ancak çağıran kod içinde kullanılan bağımsız değişken adı (varsa) aynı adlı parametre yönteminde tanımlanmış olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="99f9e-125">The arguments must be compatible with the parameter type but the argument name (if any) used in the calling code does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="99f9e-126">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="99f9e-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#74](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_3.cs)]  
  
## <a name="passing-by-reference-vs-passing-by-value"></a><span data-ttu-id="99f9e-127">Başvuru vs geçirerek. Değere göre geçirme</span><span class="sxs-lookup"><span data-stu-id="99f9e-127">Passing by Reference vs. Passing by Value</span></span>  
 <span data-ttu-id="99f9e-128">Varsayılan olarak, bir değer türü bir yönteme geçirildiğinde nesne yerine bir kopyasını geçirilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-128">By default, when a value type is passed to a method, a copy is passed instead of the object itself.</span></span> <span data-ttu-id="99f9e-129">Bu nedenle, bağımsız değişkenin değişiklikleri arama yönteminde özgün kopya üzerinde etkisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="99f9e-129">Therefore, changes to the argument have no effect on the original copy in the calling method.</span></span> <span data-ttu-id="99f9e-130">Ref anahtar sözcüğünü kullanarak bir değer türü başvurusu tarafından geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-130">You can pass a value-type by reference by using the ref keyword.</span></span> <span data-ttu-id="99f9e-131">Daha fazla bilgi için bkz: [değer türü parametrelerini geçirme](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-131">For more information, see [Passing Value-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span></span> <span data-ttu-id="99f9e-132">Yerleşik değer türlerinin listesi için bkz: [değer türleri tablosu](../../../csharp/language-reference/keywords/value-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-132">For a list of built-in value types, see [Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md).</span></span>  
  
 <span data-ttu-id="99f9e-133">Nesneye bir başvurusu, başvuru türünde bir nesne için bir yöntem geçirildiğinde geçirilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-133">When an object of a reference type is passed to a method, a reference to the object is passed.</span></span> <span data-ttu-id="99f9e-134">Diğer bir deyişle, nesnenin kendisini değil ancak nesnenin konumunu belirten bir bağımsız değişken yöntemi alır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-134">That is, the method receives not the object itself but an argument that indicates the location of the object.</span></span> <span data-ttu-id="99f9e-135">Bu başvuru kullanarak nesne üyesi değiştirirseniz, değeri tarafından nesneyi geçirin olsa bile değişiklik arama yönteminde bağımsız yansıtılır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-135">If you change a member of the object by using this reference, the change is reflected in the argument in the calling method, even if you pass the object by value.</span></span>  
  
 <span data-ttu-id="99f9e-136">Kullanarak bir başvuru türü oluşturma `class` aşağıdaki örnekte gösterildiği gibi anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="99f9e-136">You create a reference type by using the `class` keyword, as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideObjects#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_4.cs)]  
  
 <span data-ttu-id="99f9e-137">Şimdi, bu tür bir yönteme dayalı bir nesne geçirirseniz, nesneye bir başvurusu geçirilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-137">Now, if you pass an object that is based on this type to a method, a reference to the object is passed.</span></span> <span data-ttu-id="99f9e-138">Aşağıdaki örnekte bir nesne türü geçirir `SampleRefType` yöntemine `ModifyObject`.</span><span class="sxs-lookup"><span data-stu-id="99f9e-138">The following example passes an object of type `SampleRefType` to method `ModifyObject`.</span></span>  
  
 [!code-csharp[csProgGuideObjects#75](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_5.cs)]  
  
 <span data-ttu-id="99f9e-139">Bu bağımsız değişken değeri tarafından bir yönteme geçirir, örneğin önceki örnekte temelde aynı şeyi yapar.</span><span class="sxs-lookup"><span data-stu-id="99f9e-139">The example does essentially the same thing as the previous example in that it passes an argument by value to a method.</span></span> <span data-ttu-id="99f9e-140">Ancak, bir başvuru türü kullanıldığından, sonuç farklıdır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-140">But, because a reference type is used, the result is different.</span></span> <span data-ttu-id="99f9e-141">İçinde yapılan değişiklik `ModifyObject` için `value` parametre alan `obj`, ayrıca değiştirir `value` bağımsız değişken alan `rt`, `TestRefType` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="99f9e-141">The modification that is made in `ModifyObject` to the `value` field of the parameter, `obj`, also changes the `value` field of the argument, `rt`, in the `TestRefType` method.</span></span> <span data-ttu-id="99f9e-142">`TestRefType` Yöntemi 33 çıkış olarak görüntüler.</span><span class="sxs-lookup"><span data-stu-id="99f9e-142">The `TestRefType` method displays 33 as the output.</span></span>  
  
 <span data-ttu-id="99f9e-143">Başvuru türleri başvuruya göre ve değerine göre geçirmek hakkında daha fazla bilgi için bkz: [başvuru türü parametreleri geçirme](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) ve [başvuru türleri](../../../csharp/language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-143">For more information about how to pass reference types by reference and by value, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) and [Reference Types](../../../csharp/language-reference/keywords/reference-types.md).</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="99f9e-144">Dönüş Değerleri</span><span class="sxs-lookup"><span data-stu-id="99f9e-144">Return Values</span></span>  
<span data-ttu-id="99f9e-145">Yöntemleri bir değer çağırana geri dönebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-145">Methods can return a value to the caller.</span></span> <span data-ttu-id="99f9e-146">Dönüş türü, yöntem adı önce listelenen türü değil `void`, yöntem kullanarak değeri döndürebilir `return` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="99f9e-146">If the return type, the type listed before the method name, is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="99f9e-147">With deyimi `return` anahtar sözcüğünü dönüş türüyle eşleşen bir değeri tarafından yöntemi çağırana bu değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="99f9e-147">A statement with the `return` keyword followed by a value that matches the return type will return that value to the method caller.</span></span> 

<span data-ttu-id="99f9e-148">Değeri veya, C# 7 ile başlayan çağırana döndürülebilecek değeri [başvuruya göre](ref-returns.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-148">The value can be returned to the caller by value or, starting with C# 7, [by reference](ref-returns.md).</span></span> <span data-ttu-id="99f9e-149">Değerleri çağırana döndürülen başvuruya göre `ref` anahtar sözcüğü yöntemi imzada kullanılır ve her izleyen `return` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="99f9e-149">Values are returned to the caller by reference if the `ref` keyword is used in the method signature and it follows each `return` keyword.</span></span> <span data-ttu-id="99f9e-150">Örneğin, aşağıdaki yöntemi imza ve return deyimi belirtmek yöntemi bir değişken adlarını döndürür `estDistance` çağırana başvuruya.</span><span class="sxs-lookup"><span data-stu-id="99f9e-150">For example, the following method signature and return statement indicate that the method returns a variable names `estDistance` by reference to the caller.</span></span>

```csharp
public ref double GetEstimatedDistance()
{
   return ref estDistance;
}
```

<span data-ttu-id="99f9e-151">`return` Anahtar sözcüğü yönteminin yürütülmesi de durdurulur.</span><span class="sxs-lookup"><span data-stu-id="99f9e-151">The `return` keyword also stops the execution of the method.</span></span> <span data-ttu-id="99f9e-152">Dönüş türü ise `void`, `return` deyimi bir değer olmadan yönteminin yürütülmesi durdurmak hala faydalıdır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-152">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="99f9e-153">Olmadan `return` anahtar sözcüğü yöntemi durduracak kod bloğunu sonuna ulaştığında yürütülüyor.</span><span class="sxs-lookup"><span data-stu-id="99f9e-153">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span> <span data-ttu-id="99f9e-154">Void olmayan yöntemleriyle dönüş türü kullanmak için gerekli `return` bir değer döndürmek üzere anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="99f9e-154">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="99f9e-155">Örneğin, bu iki yöntem kullanmak `return` tamsayılar döndürmek için anahtar sözcüğü:</span><span class="sxs-lookup"><span data-stu-id="99f9e-155">For example, these two methods use the `return` keyword to return integers:</span></span>  
  
 [!code-csharp[csProgGuideObjects#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_6.cs)]  
  
 <span data-ttu-id="99f9e-156">Bir yönteminden döndürülen bir değer kullanmak için arama yöntemi aynı türde bir değer yeterli olacaktır yöntem çağrısının kendisini her yerde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-156">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="99f9e-157">Dönüş değeri bir değişkene de atayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-157">You can also assign the return value to a variable.</span></span> <span data-ttu-id="99f9e-158">Örneğin, aşağıdaki iki kod örnekleri aynı hedefe gerçekleştirirsiniz:</span><span class="sxs-lookup"><span data-stu-id="99f9e-158">For example, the following two code examples accomplish the same goal:</span></span>  
  
 [!code-csharp[csProgGuideObjects#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_7.cs)]  
  
 [!code-csharp[csProgGuideObjects#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_8.cs)]  
  
 <span data-ttu-id="99f9e-159">Yerel bir değişken, bu durumda, kullanarak `result`depolamak için bir değer isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-159">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="99f9e-160">Tüm kapsamını yöntemi için bağımsız değişken özgün değeri depolamak gerekiyorsa gerekli olabilir veya kod okunabilirliğini yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-160">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>  

<span data-ttu-id="99f9e-161">Bir yöntem başvurusundan tarafından döndürülen bir değer kullanmak için bildirmelisiniz bir [ref yerel](ref-returns.md#ref-locals) değerini değiştirmek istiyorsanız, değişkeni.</span><span class="sxs-lookup"><span data-stu-id="99f9e-161">To use a value returned by reference from a method, you must declare a [ref local](ref-returns.md#ref-locals) variable if you intend to modify its value.</span></span> <span data-ttu-id="99f9e-162">Örneğin, varsa `Planet.GetEstimatedDistance` yöntemi döndürür bir <xref:System.Double> değeri başvuruya göre bunu aşağıdaki gibi bir kodla ref yerel değişken olarak tanımlayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="99f9e-162">For example, if the `Planet.GetEstimatedDistance` method returns a <xref:System.Double> value by reference, you can define it as a ref local variable with code like the following:</span></span>

```csharp
ref int distance = plant 
```

<span data-ttu-id="99f9e-163">Bir yöntemi, çok boyutlu bir dizi döndürme `M`, dizinin değiştiren içeriği çağıran işlevi diziye aktarılırsa gerekli olmadığı `M`.</span><span class="sxs-lookup"><span data-stu-id="99f9e-163">Returning a multi-dimensional array from a method, `M`, that modifies the array's contents is not necessary if the calling function passed the array into `M`.</span></span>  <span data-ttu-id="99f9e-164">Sonuçta elde edilen diziden döndürebilir `M` iyi stili veya değerleri, ancak işlev akışını çünkü C# değerine göre tüm başvuru türleri geçirir ve bir dizi başvurusu dizi yönelik işaretçinin değeri gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-164">You may return the resulting array from `M` for good style or functional flow of values, but it is not necessary because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="99f9e-165">Yönteminde `M`, aşağıdaki örnekte gösterildiği gibi dizinin içeriğini herhangi bir değişiklik observable dizi başvuruyor herhangi bir kod tarafından şunlardır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-165">In the method `M`, any changes to the array's contents are observable by any code that has a reference to the array, as shown in the following example.</span></span>  
  
```csharp  
static void Main(string[] args)  
        {  
            int[,] matrix = new int[2, 2];  
            FillMatrix(matrix);  
            // matrix is now full of -1  
        }  
  
        public static void FillMatrix(int[,] matrix)  
        {  
            for (int i = 0; i < matrix.GetLength(0); i++)  
            {  
                for (int j = 0; j < matrix.GetLength(1); j++)  
                {  
                    matrix[i, j] = -1;  
                }  
            }  
        }  
```  
  
 <span data-ttu-id="99f9e-166">Daha fazla bilgi için bkz: [iade](../../../csharp/language-reference/keywords/return.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-166">For more information, see [return](../../../csharp/language-reference/keywords/return.md).</span></span>  
  
## <a name="async-methods"></a><span data-ttu-id="99f9e-167">Zaman uyumsuz yöntemleri</span><span class="sxs-lookup"><span data-stu-id="99f9e-167">Async Methods</span></span>  
 <span data-ttu-id="99f9e-168">Async özelliği kullanarak, açık geri aramalar kullanarak veya birden çok yöntem veya lambda ifadeleri kodunuzu el ile bölme olmadan zaman uyumsuz yöntemleri çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-168">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span> 
  
 <span data-ttu-id="99f9e-169">Bir yöntem ile işaretlerseniz [zaman uyumsuz](../../../csharp/language-reference/keywords/async.md) kullanabileceğiniz değiştiricisi, [await](../../../csharp/language-reference/keywords/await.md) yönteminde işleci.</span><span class="sxs-lookup"><span data-stu-id="99f9e-169">If you mark a method with the [async](../../../csharp/language-reference/keywords/async.md) modifier, you can use the [await](../../../csharp/language-reference/keywords/await.md) operator in the method.</span></span> <span data-ttu-id="99f9e-170">Denetim async yöntemi bekleme deyimde ulaştığında çağırana denetimini döndürür ve yöntemi ediyor awaited görevi tamamlanana kadar bekletilir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-170">When control reaches an await expression in the async method, control returns to the caller, and progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="99f9e-171">Görev tamamlandığında, yürütme yönteminde devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-171">When the task is complete, execution can resume in the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99f9e-172">Bir zaman uyumsuz yöntem henüz tamamlanmadı ilk awaited nesne bulduğu veya zaman uyumsuz yönteminin sonuna alır çağırana döndürür hangisi önce gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-172">An async method returns to the caller when either it encounters the first awaited object that’s not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>  
  
 <span data-ttu-id="99f9e-173">Zaman uyumsuz yöntem dönüş türüne sahip olabilir <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, ya da geçersiz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-173">An async method can have a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, or void.</span></span> <span data-ttu-id="99f9e-174">Dönüş türü void dönüş türü void gerekli olduğu öncelikle olay işleyicileri tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-174">The void return type is used primarily to define event handlers, where a void return type is required.</span></span> <span data-ttu-id="99f9e-175">Void döndüren bir zaman uyumsuz yöntem beklemenin ve void döndüren bir yöntem arayan yöntemi atar özel durumlarını yakalama olamaz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-175">An async method that returns void can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="99f9e-176">Aşağıdaki örnekte, `DelayAsync` dönüş türüne sahip bir zaman uyumsuz yöntem <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="99f9e-176">In the following example, `DelayAsync` is an async method that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="99f9e-177">`DelayAsync`sahip bir `return` deyimi bir tamsayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="99f9e-177">`DelayAsync` has a `return` statement that returns an integer.</span></span> <span data-ttu-id="99f9e-178">Bu nedenle yöntemi bildirimi `DelayAsync` dönüş türüne sahip olmalıdır `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="99f9e-178">Therefore the method declaration of `DelayAsync` must have a return type of `Task<int>`.</span></span> <span data-ttu-id="99f9e-179">Dönüş türü olduğundan `Task<int>`, değerlendirmesi `await` ifadesinde `DoSomethingAsync` aşağıdaki ifadeyi gösterdiği gibi bir tamsayı üretir: `int result = await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="99f9e-179">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer as the following statement demonstrates: `int result = await delayTask`.</span></span>  
  
 <span data-ttu-id="99f9e-180">`startButton_Click` Yöntemi geçersiz dönüş türüne sahip bir zaman uyumsuz yöntem örneğidir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-180">The `startButton_Click` method is an example of an async method that has a return type of void.</span></span> <span data-ttu-id="99f9e-181">Çünkü `DoSomethingAsync` bir zaman uyumsuz yöntem çağrısı için görev `DoSomethingAsync` , aşağıdaki deyimi gösterildiği beklemenin gerekir: `await DoSomethingAsync();`.</span><span class="sxs-lookup"><span data-stu-id="99f9e-181">Because `DoSomethingAsync` is an async method, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `await DoSomethingAsync();`.</span></span> <span data-ttu-id="99f9e-182">`startButton_Click` Yöntemi ile tanımlanması gerekir `async` değiştirici yöntem sahip olduğu bir `await` ifade.</span><span class="sxs-lookup"><span data-stu-id="99f9e-182">The `startButton_Click` method must be defined with the `async` modifier because the method has an `await` expression.</span></span>  
  
 [!code-csharp[csAsyncMethod#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_9.cs)]  
  
 <span data-ttu-id="99f9e-183">Herhangi bir zaman uyumsuz yöntem bildiremezsiniz [ref](../../../csharp/language-reference/keywords/ref.md) veya [çıkışı](../../../csharp/language-reference/keywords/out.md) parametreleri, ancak bu tür parametrelerine sahip yöntemleri çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-183">An async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters, but it can call methods that have such parameters.</span></span>  
  
 <span data-ttu-id="99f9e-184">Zaman uyumsuz yöntemleri hakkında daha fazla bilgi için bkz [zaman uyumsuz programlama ile async ve await](../../../csharp/programming-guide/concepts/async/index.md), [akış denetimi zaman uyumsuz programlarda](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), ve [zaman uyumsuz dönüş türleri](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="99f9e-184">For more information about async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="99f9e-185">İfade gövdesi tanımları</span><span class="sxs-lookup"><span data-stu-id="99f9e-185">Expression Body Definitions</span></span>  
 <span data-ttu-id="99f9e-186">Yalnızca hemen ifade ile sonuç ya da tek bir deyimde yönteminin gövdesi olarak sahip yöntemi tanımı yaygındır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-186">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="99f9e-187">Bu tür yöntemlerini kullanarak tanımlamak için bir söz dizimi kısayol yoktur `=>`:</span><span class="sxs-lookup"><span data-stu-id="99f9e-187">There is a syntax shortcut for defining such methods using `=>`:</span></span>  
  
```csharp  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);   
public void Print() => Console.WriteLine(First + " " + Last);  
// Works with operators, properties, and indexers too.  
public static Complex operator +(Complex a, Complex b) => a.Add(b);  
public string Name => First + " " + Last;   
public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 <span data-ttu-id="99f9e-188">Yöntem döndürüyorsa `void` veya yönteminin gövdesi bir deyim ifadesi (aynı Lambda'lar gibi) olması gerekir async yöntemi.</span><span class="sxs-lookup"><span data-stu-id="99f9e-188">If the method returns `void` or is an async method, then the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="99f9e-189">Özellikler ve dizin oluşturucular için bunlar salt okunur olmalıdır ve kullanmadığınız `get` erişimci anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="99f9e-189">For properties and indexers, they must be read only, and you don't use the `get` accessor keyword.</span></span>  
  
## <a name="iterators"></a><span data-ttu-id="99f9e-190">Yineleyiciler</span><span class="sxs-lookup"><span data-stu-id="99f9e-190">Iterators</span></span>  
 <span data-ttu-id="99f9e-191">Yineleyici özel bir yineleme listesini veya bir dizi gibi bir koleksiyon üzerinden gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="99f9e-191">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="99f9e-192">Yineleyici kullanan [verim return](../../../csharp/language-reference/keywords/yield.md) her öğeye aynı anda geri dönmek için deyimi.</span><span class="sxs-lookup"><span data-stu-id="99f9e-192">An iterator uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="99f9e-193">Zaman bir [verim return](../../../csharp/language-reference/keywords/yield.md) deyimi ulaşıldığında geçerli kod konumda anımsanacak.</span><span class="sxs-lookup"><span data-stu-id="99f9e-193">When a [yield return](../../../csharp/language-reference/keywords/yield.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="99f9e-194">Yineleyici sonraki çağrıldığında yürütme o konumdan yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="99f9e-194">Execution is restarted from that location when the iterator is called the next time.</span></span>  
  
 <span data-ttu-id="99f9e-195">Yineleyici kullanarak istemci kodundan çağıran bir [foreach](../../../csharp/language-reference/keywords/foreach-in.md) deyimi.</span><span class="sxs-lookup"><span data-stu-id="99f9e-195">You call an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span>  
  
 <span data-ttu-id="99f9e-196">Yineleyici dönüş türü olabilir <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, veya <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="99f9e-196">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="99f9e-197">Daha fazla bilgi için bkz: [yineleyiciler](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="99f9e-197">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="99f9e-198">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="99f9e-198">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99f9e-199">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="99f9e-199">See Also</span></span>  
 [<span data-ttu-id="99f9e-200">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="99f9e-200">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="99f9e-201">Sınıflar ve yapılar</span><span class="sxs-lookup"><span data-stu-id="99f9e-201">Classes and Structs</span></span>](index.md)  
 [<span data-ttu-id="99f9e-202">Erişim değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="99f9e-202">Access Modifiers</span></span>](access-modifiers.md)  
 [<span data-ttu-id="99f9e-203">Statik sınıflar ve statik sınıf üyeleri</span><span class="sxs-lookup"><span data-stu-id="99f9e-203">Static Classes and Static Class Members</span></span>](static-classes-and-static-class-members.md)  
 [<span data-ttu-id="99f9e-204">Devralma</span><span class="sxs-lookup"><span data-stu-id="99f9e-204">Inheritance</span></span>](inheritance.md)  
 [<span data-ttu-id="99f9e-205">Soyut ve korumalı sınıflar ve sınıf üyeleri</span><span class="sxs-lookup"><span data-stu-id="99f9e-205">Abstract and Sealed Classes and Class Members</span></span>](abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="99f9e-206">parametreleri</span><span class="sxs-lookup"><span data-stu-id="99f9e-206">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
 [<span data-ttu-id="99f9e-207">Döndür</span><span class="sxs-lookup"><span data-stu-id="99f9e-207">return</span></span>](../../../csharp/language-reference/keywords/return.md)  
 [<span data-ttu-id="99f9e-208">çıkışı</span><span class="sxs-lookup"><span data-stu-id="99f9e-208">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
 [<span data-ttu-id="99f9e-209">Ref</span><span class="sxs-lookup"><span data-stu-id="99f9e-209">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="99f9e-210">Parametreleri geçirme</span><span class="sxs-lookup"><span data-stu-id="99f9e-210">Passing Parameters</span></span>](passing-parameters.md)