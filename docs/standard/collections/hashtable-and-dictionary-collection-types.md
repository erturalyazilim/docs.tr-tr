---
title: "Karma Tablo ve Sözlük Koleksiyon Türleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aa2392775f0bd2d68c0aeb28aa0654b690b11808
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="hashtable-and-dictionary-collection-types"></a><span data-ttu-id="240fc-102">Karma Tablo ve Sözlük Koleksiyon Türleri</span><span class="sxs-lookup"><span data-stu-id="240fc-102">Hashtable and Dictionary Collection Types</span></span>
<span data-ttu-id="240fc-103"><xref:System.Collections.Hashtable?displayProperty=nameWithType> Sınıfı ve <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> ve <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> Genel sınıflar uygulamak <xref:System.Collections.IDictionary?displayProperty=nameWithType> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="240fc-103">The <xref:System.Collections.Hashtable?displayProperty=nameWithType> class, and the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> generic classes, implement the <xref:System.Collections.IDictionary?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="240fc-104"><xref:System.Collections.Generic.Dictionary%602> Genel sınıfı ayrıca uygulayan <xref:System.Collections.Generic.IDictionary%602> genel arabirim.</span><span class="sxs-lookup"><span data-stu-id="240fc-104">The <xref:System.Collections.Generic.Dictionary%602> generic class also implements the <xref:System.Collections.Generic.IDictionary%602> generic interface.</span></span> <span data-ttu-id="240fc-105">Bu nedenle, bu koleksiyonları her bir öğesinde bir anahtar ve değer çifti ' dir.</span><span class="sxs-lookup"><span data-stu-id="240fc-105">Therefore, each element in these collections is a key-and-value pair.</span></span>  
  
 <span data-ttu-id="240fc-106">A <xref:System.Collections.Hashtable> nesnesi koleksiyon öğelerini içeren demet oluşur.</span><span class="sxs-lookup"><span data-stu-id="240fc-106">A <xref:System.Collections.Hashtable> object consists of buckets that contain the elements of the collection.</span></span> <span data-ttu-id="240fc-107">Bir sanal alt öğeleri içinde kova grubudur <xref:System.Collections.Hashtable>, arama ve alma yapar daha kolay ve daha hızlıdır çoğu koleksiyonlarda.</span><span class="sxs-lookup"><span data-stu-id="240fc-107">A bucket is a virtual subgroup of elements within the <xref:System.Collections.Hashtable>, which makes searching and retrieving easier and faster than in most collections.</span></span> <span data-ttu-id="240fc-108">Her demet karma işlevi kullanılarak oluşturulur ve öğenin anahtarı temel bir karma kod ile ilişkilidir.</span><span class="sxs-lookup"><span data-stu-id="240fc-108">Each bucket is associated with a hash code, which is generated using a hash function and is based on the key of the element.</span></span>  
  
 <span data-ttu-id="240fc-109">Genel <xref:System.Collections.Generic.HashSet%601> sınıfı, sırasız bir benzersiz öğeleri içeren koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="240fc-109">The generic <xref:System.Collections.Generic.HashSet%601> class is an unordered collection for containing unique elements.</span></span>  
  
 <span data-ttu-id="240fc-110">Hash işlevi bir anahtarı temel sayısal karma kodu döndürür bir algoritmadır.</span><span class="sxs-lookup"><span data-stu-id="240fc-110">A hash function is an algorithm that returns a numeric hash code based on a key.</span></span> <span data-ttu-id="240fc-111">Anahtar depolanmakta nesnenin bazı özelliğinin değeri.</span><span class="sxs-lookup"><span data-stu-id="240fc-111">The key is the value of some property of the object being stored.</span></span> <span data-ttu-id="240fc-112">Hash işlevi her zaman aynı anahtar için aynı karma koda döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="240fc-112">A hash function must always return the same hash code for the same key.</span></span> <span data-ttu-id="240fc-113">İki farklı anahtarlar aynı karma kodunu oluşturmak için bir karma işlevi, ancak öğeleri karma tablosundan alınırken daha iyi performans her benzersiz anahtar sonuçlar için bir benzersiz karma kodu oluşturan karma işlevi mümkündür.</span><span class="sxs-lookup"><span data-stu-id="240fc-113">It is possible for a hash function to generate the same hash code for two different keys, but a hash function that generates a unique hash code for each unique key results in better performance when retrieving elements from the hash table.</span></span>  
  
 <span data-ttu-id="240fc-114">Bir öğe olarak kullanılan her nesne bir <xref:System.Collections.Hashtable> bir karma kod kendisi için uygulaması kullanarak oluşturabilir olmalıdır <xref:System.Object.GetHashCode%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="240fc-114">Each object that is used as an element in a <xref:System.Collections.Hashtable> must be able to generate a hash code for itself by using an implementation of the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="240fc-115">Ancak, tüm öğeler için karma işlevi de belirleyebileceğiniz bir <xref:System.Collections.Hashtable> kullanarak bir <xref:System.Collections.Hashtable> kabul Oluşturucusu bir <xref:System.Collections.IHashCodeProvider> parametrelerinden biri olarak uygulama.</span><span class="sxs-lookup"><span data-stu-id="240fc-115">However, you can also specify a hash function for all elements in a <xref:System.Collections.Hashtable> by using a <xref:System.Collections.Hashtable> constructor that accepts an <xref:System.Collections.IHashCodeProvider> implementation as one of its parameters.</span></span>  
  
 <span data-ttu-id="240fc-116">İçin bir nesne eklendiğinde bir <xref:System.Collections.Hashtable>, nesnenin karma kodu ile eşleşen karma kodu ile ilişkili demet depolanır.</span><span class="sxs-lookup"><span data-stu-id="240fc-116">When an object is added to a <xref:System.Collections.Hashtable>, it is stored in the bucket that is associated with the hash code that matches the object's hash code.</span></span> <span data-ttu-id="240fc-117">Ne zaman bir değer aranır için de <xref:System.Collections.Hashtable>karma kod için bu değer oluşturulur ve bu karma kodu ile ilişkili demet aranır.</span><span class="sxs-lookup"><span data-stu-id="240fc-117">When a value is being searched for in the <xref:System.Collections.Hashtable>, the hash code is generated for that value, and the bucket associated with that hash code is searched.</span></span>  
  
 <span data-ttu-id="240fc-118">Örneğin, bir dize için bir karma işlevi bir dizede her karakter ASCII kodlarından alın ve bunları birlikte bir karma kodu oluşturmak için ekleyin.</span><span class="sxs-lookup"><span data-stu-id="240fc-118">For example, a hash function for a string might take the ASCII codes of each character in the string and add them together to generate a hash code.</span></span> <span data-ttu-id="240fc-119">"Piknik" dize "sepet"; dize ilişkin karma kodu farklı bir karma kod gerekir Bu nedenle, dizeleri "Piknik" ve "sepet" içinde farklı demet olacaktır.</span><span class="sxs-lookup"><span data-stu-id="240fc-119">The string "picnic" would have a hash code that is different from the hash code for the string "basket"; therefore, the strings "picnic" and "basket" would be in different buckets.</span></span> <span data-ttu-id="240fc-120">Buna karşılık, "kullanımı yoğun" ve "desserts" aynı karma koda sahip ve aynı aralığındaki olacaktır.</span><span class="sxs-lookup"><span data-stu-id="240fc-120">In contrast, "stressed" and "desserts" would have the same hash code and would be in the same bucket.</span></span>  
  
 <span data-ttu-id="240fc-121"><xref:System.Collections.Generic.Dictionary%602> Ve <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sınıfları aynı işlevselliğe sahip <xref:System.Collections.Hashtable> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="240fc-121">The <xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602> classes have the same functionality as the <xref:System.Collections.Hashtable> class.</span></span> <span data-ttu-id="240fc-122">A <xref:System.Collections.Generic.Dictionary%602> belirli bir türdeki (dışında <xref:System.Object>) daha iyi performans sağlayan bir <xref:System.Collections.Hashtable> değer türleri için.</span><span class="sxs-lookup"><span data-stu-id="240fc-122">A <xref:System.Collections.Generic.Dictionary%602> of a specific type (other than <xref:System.Object>) provides better performance than a <xref:System.Collections.Hashtable> for value types.</span></span> <span data-ttu-id="240fc-123">Bunun nedeni, öğelerini <xref:System.Collections.Hashtable> türü <xref:System.Object>; bu nedenle, kutulama ve kutudan çıkarma genellikle ortaya depolamak ya da bir değer türü alır.</span><span class="sxs-lookup"><span data-stu-id="240fc-123">This is because the elements of <xref:System.Collections.Hashtable> are of type <xref:System.Object>; therefore, boxing and unboxing typically occur when you store or retrieve a value type.</span></span> <span data-ttu-id="240fc-124"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> Birden çok iş parçacığı koleksiyonunun aynı anda erişirken sınıfı'nin kullanılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="240fc-124">The <xref:System.Collections.Concurrent.ConcurrentDictionary%602> class should be used when multiple threads might be accessing the collection simultaneously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240fc-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="240fc-125">See Also</span></span>  
 <xref:System.Collections.Hashtable>  
 <xref:System.Collections.IDictionary>  
 <xref:System.Collections.IHashCodeProvider>  
 <xref:System.Collections.Generic.Dictionary%602>  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>  
 [<span data-ttu-id="240fc-126">Çok kullanılan koleksiyon türleri</span><span class="sxs-lookup"><span data-stu-id="240fc-126">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)