---
title: Yineleyiciler (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d4994ea57d9fd0df8dfca7ffa40c280499caee6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iterators-c"></a><span data-ttu-id="22e5a-102">Yineleyiciler (C#)</span><span class="sxs-lookup"><span data-stu-id="22e5a-102">Iterators (C#)</span></span>
<span data-ttu-id="22e5a-103">Bir *yineleyici* koleksiyonlarına listeler ve dizi gibi adım için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="22e5a-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="22e5a-104">İterator yöntemi veya `get` erişimci gerçekleştiren özel bir yineleme içinde bir koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="22e5a-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="22e5a-105">İterator yöntemi kullanır [verim return](../../../csharp/language-reference/keywords/yield.md) her öğeye aynı anda geri dönmek için deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-105">An iterator method uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="22e5a-106">Zaman bir `yield return` deyimi ulaşıldığında geçerli kod konumda anımsanacak.</span><span class="sxs-lookup"><span data-stu-id="22e5a-106">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="22e5a-107">Yürütme o konumdan yineleyici işlevi bir sonraki zamana yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="22e5a-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="22e5a-108">İle yineleyici istemci kodundan kullanmasını bir [foreach](../../../csharp/language-reference/keywords/foreach-in.md) deyimi veya bir LINQ Sorgu kullanarak.</span><span class="sxs-lookup"><span data-stu-id="22e5a-108">You consume an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="22e5a-109">Aşağıdaki örnekte, ilk yinelemesi `foreach` döngüye neden olur, devam etmek yürütme `SomeNumbers` yineleyici yöntemi ilk kadar `yield return` deyimi ulaşıldığında.</span><span class="sxs-lookup"><span data-stu-id="22e5a-109">In the following example, the first iteration of the `foreach` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="22e5a-110">Bu yineleme 3 değerini döndürür ve yineleyici yöntemi geçerli konumda korunur.</span><span class="sxs-lookup"><span data-stu-id="22e5a-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="22e5a-111">Döngü sonraki yinelemesinde nereden yürütülmeye yineleyici yönteminde ulaştığında yeniden durdurma kapalı, solda bir `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="22e5a-112">Bu yineleme 5 değerini döndürür ve yineleyici yöntemi geçerli konuma yeniden korunur.</span><span class="sxs-lookup"><span data-stu-id="22e5a-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="22e5a-113">Yineleyici yönteminin sonuna gelindiğinde döngü tamamlar.</span><span class="sxs-lookup"><span data-stu-id="22e5a-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
```csharp  
static void Main()  
{  
    foreach (int number in SomeNumbers())  
    {  
        Console.Write(number.ToString() + " ");  
    }  
    // Output: 3 5 8  
    Console.ReadKey();  
}  
  
public static System.Collections.IEnumerable SomeNumbers()  
{  
    yield return 3;  
    yield return 5;  
    yield return 8;  
}  
```  
  
 <span data-ttu-id="22e5a-114">Yineleyici yönteminin dönüş türü veya `get` erişimci olabilir <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, veya <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="22e5a-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="22e5a-115">Kullanabileceğiniz bir `yield break` yinelemeyi sonlandırmak için deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-115">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="22e5a-116">Yineleyiciler C# Visual Studio 2005'te tanıtıldı.</span><span class="sxs-lookup"><span data-stu-id="22e5a-116">Iterators were introduced in C# in Visual Studio 2005.</span></span>  
  
 <span data-ttu-id="22e5a-117">**Bu konudaki**</span><span class="sxs-lookup"><span data-stu-id="22e5a-117">**In this topic**</span></span>  
  
-   [<span data-ttu-id="22e5a-118">Basit yineleyici</span><span class="sxs-lookup"><span data-stu-id="22e5a-118">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="22e5a-119">Koleksiyon sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="22e5a-119">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="22e5a-120">Yineleyiciler genel bir listesi ile kullanma</span><span class="sxs-lookup"><span data-stu-id="22e5a-120">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="22e5a-121">Sözdizimi bilgileri</span><span class="sxs-lookup"><span data-stu-id="22e5a-121">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="22e5a-122">Teknik uygulama</span><span class="sxs-lookup"><span data-stu-id="22e5a-122">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="22e5a-123">Yineleyiciler kullanımı</span><span class="sxs-lookup"><span data-stu-id="22e5a-123">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="22e5a-124">Bu konuda basit yineleyici örnek dışındaki tüm örnekler için dahil [kullanarak](../../../csharp/language-reference/keywords/using-directive.md) yönergeleri için `System.Collections` ve `System.Collections.Generic` ad alanları.</span><span class="sxs-lookup"><span data-stu-id="22e5a-124">For all examples in this topic except the Simple Iterator example, include [using](../../../csharp/language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="22e5a-125"><a name="BKMK_SimpleIterator"></a>Basit yineleyici</span><span class="sxs-lookup"><span data-stu-id="22e5a-125"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="22e5a-126">Aşağıdaki örnek bir tek sahip `yield return` içinde deyimi bir [için](../../../csharp/language-reference/keywords/for.md) döngü.</span><span class="sxs-lookup"><span data-stu-id="22e5a-126">The following example has a single `yield return` statement that is inside a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="22e5a-127">İçinde `Main`, her yinelemesinden `foreach` deyimi gövde oluşturur diğerine geçer yineleyici işlevi çağrısı `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-127">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>  
  
```csharp  
static void Main()  
{  
    foreach (int number in EvenSequence(5, 18))  
    {  
        Console.Write(number.ToString() + " ");  
    }  
    // Output: 6 8 10 12 14 16 18  
    Console.ReadKey();  
}  
  
public static System.Collections.Generic.IEnumerable<int>  
    EvenSequence(int firstNumber, int lastNumber)  
{  
    // Yield even numbers in the range.  
    for (int number = firstNumber; number <= lastNumber; number++)  
    {  
        if (number % 2 == 0)  
        {  
            yield return number;  
        }  
    }  
}  
```  
  
##  <span data-ttu-id="22e5a-128"><a name="BKMK_CollectionClass"></a>Koleksiyon sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="22e5a-128"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="22e5a-129">Aşağıdaki örnekte, `DaysOfTheWeek` uygulayan sınıf <xref:System.Collections.IEnumerable> gerektirir arabirimi bir <xref:System.Collections.IEnumerable.GetEnumerator%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-129">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="22e5a-130">Derleyici örtülü olarak çağırır `GetEnumerator` döndürür yöntemi bir <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="22e5a-130">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="22e5a-131">`GetEnumerator` Yöntemi döndürür her dize aynı anda kullanarak `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-131">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>  
  
```csharp  
static void Main()  
{  
    DaysOfTheWeek days = new DaysOfTheWeek();  
  
    foreach (string day in days)  
    {  
        Console.Write(day + " ");  
    }  
    // Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey();  
}  
  
public class DaysOfTheWeek : IEnumerable  
{  
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };  
  
    public IEnumerator GetEnumerator()  
    {  
        for (int index = 0; index < days.Length; index++)  
        {  
            // Yield each day of the week.  
            yield return days[index];  
        }  
    }  
}  
```  
  
 <span data-ttu-id="22e5a-132">Aşağıdaki örnekte bir `Zoo` hayvanlar koleksiyonunu içeren sınıf.</span><span class="sxs-lookup"><span data-stu-id="22e5a-132">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="22e5a-133">`foreach` Sınıf örneğine başvuruda bulunan deyimi (`theZoo`) örtük olarak çağırır `GetEnumerator` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-133">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="22e5a-134">`foreach` Başvurmak deyimleri `Birds` ve `Mammals` özelliklerini kullanmak `AnimalsForType` yineleyici yöntemi adı.</span><span class="sxs-lookup"><span data-stu-id="22e5a-134">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
```csharp  
static void Main()  
{  
    Zoo theZoo = new Zoo();  
  
    theZoo.AddMammal("Whale");  
    theZoo.AddMammal("Rhinoceros");  
    theZoo.AddBird("Penguin");  
    theZoo.AddBird("Warbler");  
  
    foreach (string name in theZoo)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Whale Rhinoceros Penguin Warbler  
  
    foreach (string name in theZoo.Birds)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Penguin Warbler  
  
    foreach (string name in theZoo.Mammals)  
    {  
        Console.Write(name + " ");  
    }  
    Console.WriteLine();  
    // Output: Whale Rhinoceros  
  
    Console.ReadKey();  
}  
  
public class Zoo : IEnumerable  
{  
    // Private members.  
    private List<Animal> animals = new List<Animal>();  
  
    // Public methods.  
    public void AddMammal(string name)  
    {  
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });  
    }  
  
    public void AddBird(string name)  
    {  
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });  
    }  
  
    public IEnumerator GetEnumerator()  
    {  
        foreach (Animal theAnimal in animals)  
        {  
            yield return theAnimal.Name;  
        }  
    }  
  
    // Public members.  
    public IEnumerable Mammals  
    {  
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }  
    }  
  
    public IEnumerable Birds  
    {  
        get { return AnimalsForType(Animal.TypeEnum.Bird); }  
    }  
  
    // Private methods.  
    private IEnumerable AnimalsForType(Animal.TypeEnum type)  
    {  
        foreach (Animal theAnimal in animals)  
        {  
            if (theAnimal.Type == type)  
            {  
                yield return theAnimal.Name;  
            }  
        }  
    }  
  
    // Private class.  
    private class Animal  
    {  
        public enum TypeEnum { Bird, Mammal }  
  
        public string Name { get; set; }  
        public TypeEnum Type { get; set; }  
    }  
}  
```  
  
##  <span data-ttu-id="22e5a-135"><a name="BKMK_GenericList"></a>Yineleyiciler genel bir listesi ile kullanma</span><span class="sxs-lookup"><span data-stu-id="22e5a-135"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="22e5a-136">Aşağıdaki örnekte, `Stack(Of T)` genel bir sınıf uygular <xref:System.Collections.Generic.IEnumerable%601> genel arabirim.</span><span class="sxs-lookup"><span data-stu-id="22e5a-136">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="22e5a-137">`Push` Yöntemi atar değerleri türünde bir dizi `T`.</span><span class="sxs-lookup"><span data-stu-id="22e5a-137">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="22e5a-138"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Yöntemi kullanarak dizi değerleri döndürür `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-138">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>  
  
 <span data-ttu-id="22e5a-139">Genel yanı sıra <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> yöntemi, genel olmayan <xref:System.Collections.IEnumerable.GetEnumerator%2A> gerekir ayrıca uygulanan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-139">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="22e5a-140">Bunun nedeni, <xref:System.Collections.Generic.IEnumerable%601> devraldığı <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="22e5a-140">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="22e5a-141">Genel olmayan uygulama genel uygulamasını erteler.</span><span class="sxs-lookup"><span data-stu-id="22e5a-141">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="22e5a-142">Örnek veri aynı koleksiyonu yineleme yapma çeşitli yollarını desteklemek için adlandırılmış yineleyiciler kullanır.</span><span class="sxs-lookup"><span data-stu-id="22e5a-142">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="22e5a-143">Bunlar yineleyiciler adlı `TopToBottom` ve `BottomToTop` özelliklerini ve `TopN` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-143">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="22e5a-144">`BottomToTop` Özelliği kullanan bir yineleyici bir `get` erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-144">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>  
  
```csharp  
static void Main()  
{  
    Stack<int> theStack = new Stack<int>();  
  
    //  Add items to the stack.  
    for (int number = 0; number <= 9; number++)  
    {  
        theStack.Push(number);  
    }  
  
    // Retrieve items from the stack.  
    // foreach is allowed because theStack implements  
    // IEnumerable<int>.  
    foreach (int number in theStack)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3 2 1 0  
  
    // foreach is allowed, because theStack.TopToBottom  
    // returns IEnumerable(Of Integer).  
    foreach (int number in theStack.TopToBottom)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3 2 1 0  
  
    foreach (int number in theStack.BottomToTop)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 0 1 2 3 4 5 6 7 8 9  
  
    foreach (int number in theStack.TopN(7))  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey();  
}  
  
public class Stack<T> : IEnumerable<T>  
{  
    private T[] values = new T[100];  
    private int top = 0;  
  
    public void Push(T t)  
    {  
        values[top] = t;  
        top++;  
    }  
    public T Pop()  
    {  
        top--;  
        return values[top];  
    }  
  
    // This method implements the GetEnumerator method. It allows  
    // an instance of the class to be used in a foreach statement.  
    public IEnumerator<T> GetEnumerator()  
    {  
        for (int index = top - 1; index >= 0; index--)  
        {  
            yield return values[index];  
        }  
    }  
  
    IEnumerator IEnumerable.GetEnumerator()  
    {  
        return GetEnumerator();  
    }  
  
    public IEnumerable<T> TopToBottom  
    {  
        get { return this; }  
    }  
  
    public IEnumerable<T> BottomToTop  
    {  
        get  
        {  
            for (int index = 0; index <= top - 1; index++)  
            {  
                yield return values[index];  
            }  
        }  
    }  
  
    public IEnumerable<T> TopN(int itemsFromTop)  
    {  
        // Return less than itemsFromTop if necessary.  
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;  
  
        for (int index = top - 1; index >= startIndex; index--)  
        {  
            yield return values[index];  
        }  
    }  
  
}  
```  
  
##  <span data-ttu-id="22e5a-145"><a name="BKMK_SyntaxInformation"></a>Sözdizimi bilgileri</span><span class="sxs-lookup"><span data-stu-id="22e5a-145"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="22e5a-146">Yineleyici bir yöntem olarak oluşabilir veya `get` erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-146">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="22e5a-147">Yineleyici bir olay, örnek oluşturucusu, statik Oluşturucusu veya statik sonlandırıcıyı gerçekleşemez.</span><span class="sxs-lookup"><span data-stu-id="22e5a-147">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>  
  
 <span data-ttu-id="22e5a-148">Örtük bir dönüştürme ifadesi türden bulunmalıdır `yield return` yineleyici dönüş türü bildirimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-148">An implicit conversion must exist from the expression type in the `yield return` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="22e5a-149">C# ' ta yineleyici yöntemi içeremez `ref` veya `out` parametreleri.</span><span class="sxs-lookup"><span data-stu-id="22e5a-149">In C#, an iterator method cannot have any `ref` or `out` parameters.</span></span>  
  
 <span data-ttu-id="22e5a-150">C# ' ta, "Verim" ayrılmış bir sözcük değildir ve yalnızca önce kullanıldığında, özel bir anlamı olan bir `return` veya `break` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="22e5a-150">In C#, "yield" is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>  
  
##  <span data-ttu-id="22e5a-151"><a name="BKMK_Technical"></a>Teknik uygulama</span><span class="sxs-lookup"><span data-stu-id="22e5a-151"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="22e5a-152">Yineleyici bir yöntem olarak yazma rağmen derleyici, iç içe geçmiş sınıf diğer bir deyişle, etkin, Durum makinesi çevirir.</span><span class="sxs-lookup"><span data-stu-id="22e5a-152">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="22e5a-153">Bu sınıf olarak uzun yineleyici konumunu izler `foreach` istemci kodu döngüde devam eder.</span><span class="sxs-lookup"><span data-stu-id="22e5a-153">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="22e5a-154">Derleyici yaptıklarını görmek için bir yineleyici yöntemi için oluşturulan Microsoft Ara dil kodu görüntülemek için Ildasm.exe Aracı'nı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="22e5a-154">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="22e5a-155">Yineleyici için oluşturduğunuzda bir [sınıfı](../../../csharp/language-reference/keywords/class.md) veya [yapısı](../../../csharp/language-reference/keywords/struct.md), tüm uygulama gerekmez <xref:System.Collections.IEnumerator> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-155">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="22e5a-156">Derleyici yineleyici algılarsa, otomatik olarak oluşturur `Current`, `MoveNext`, ve `Dispose` yöntemlerinin <xref:System.Collections.IEnumerator> veya <xref:System.Collections.Generic.IEnumerator%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-156">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="22e5a-157">Art arda gelen her yinelemesinden üzerinde `foreach` döngü (veya doğrudan çağrısı `IEnumerator.MoveNext`), sonraki yineleyici kod gövdesi önceki sonra sürdürür `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-157">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="22e5a-158">Sonraki devam edip `yield return` yineleyici gövde sonuna ulaşılana kadar deyimi veya kadar bir `yield break` deyimi karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="22e5a-158">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>  
  
 <span data-ttu-id="22e5a-159">Yineleyiciler desteklemez <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-159">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="22e5a-160">Baştan yeniden yinelemek için yeni bir yineleyici edinmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="22e5a-160">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="22e5a-161">Ek bilgi için bkz: [C# dil belirtimi](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="22e5a-161">For additional information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
##  <span data-ttu-id="22e5a-162"><a name="BKMK_UseOfIterators"></a>Yineleyiciler kullanımı</span><span class="sxs-lookup"><span data-stu-id="22e5a-162"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="22e5a-163">Yineleyiciler basitliği korumanıza olanak tanır bir `foreach` döngü listesi sırası doldurmak için karmaşık kodlar kullanmanız gerektiğinde.</span><span class="sxs-lookup"><span data-stu-id="22e5a-163">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="22e5a-164">Aşağıdakileri yapmak istediğinizde bu yararlı olabilir:</span><span class="sxs-lookup"><span data-stu-id="22e5a-164">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="22e5a-165">Sonra ilk listesi değişiklik `foreach` döngü yineleme.</span><span class="sxs-lookup"><span data-stu-id="22e5a-165">Modify the list sequence after the first `foreach` loop iteration.</span></span>  
  
-   <span data-ttu-id="22e5a-166">Büyük bir liste ilk yinelemesi önce tam olarak yüklenmesini önlemek bir `foreach` döngü.</span><span class="sxs-lookup"><span data-stu-id="22e5a-166">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="22e5a-167">Bir grup tablo satır yüklemek için disk belleğine alınan fetch örneğidir.</span><span class="sxs-lookup"><span data-stu-id="22e5a-167">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="22e5a-168">Başka bir örnek <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> .NET Framework içinde yineleyiciler uygulayan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22e5a-168">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="22e5a-169">Yineleyici listesini derlerken kapsüller.</span><span class="sxs-lookup"><span data-stu-id="22e5a-169">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="22e5a-170">Yineleyici yönteminde listesi oluşturun ve her bir döngü sonucu verecek.</span><span class="sxs-lookup"><span data-stu-id="22e5a-170">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e5a-171">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="22e5a-171">See Also</span></span>  
 <xref:System.Collections.Generic>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="22e5a-172">foreach,</span><span class="sxs-lookup"><span data-stu-id="22e5a-172">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="22e5a-173">uyarı simgesi</span><span class="sxs-lookup"><span data-stu-id="22e5a-173">yield</span></span>](../../../csharp/language-reference/keywords/yield.md)  
 [<span data-ttu-id="22e5a-174">Dizilerle foreach kullanma</span><span class="sxs-lookup"><span data-stu-id="22e5a-174">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
 [<span data-ttu-id="22e5a-175">Genel türler</span><span class="sxs-lookup"><span data-stu-id="22e5a-175">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)