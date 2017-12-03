---
title: Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d04011622321638e1f3b0c5f4d270f840c7070e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="interface-design"></a><span data-ttu-id="be5de-102">Arabirimi</span><span class="sxs-lookup"><span data-stu-id="be5de-102">Interface Design</span></span>
<span data-ttu-id="be5de-103">Çoğu API'leri sınıfları ve yapıları kullanarak en iyi Modellenen rağmen arabirimler daha uygun olan veya tek seçenektir durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="be5de-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="be5de-104">CLR birden çok devralma desteklemez (yani, CLR sınıflarına birden çok taban sınıftan devralın olamaz), ancak bir taban sınıftan devralmayı yanı sıra bir veya daha fazla arabirimlerini türleri izin vermiyor.</span><span class="sxs-lookup"><span data-stu-id="be5de-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="be5de-105">Bu nedenle, arabirimler, genellikle birden çok devralma etkisini elde etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="be5de-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="be5de-106">Örneğin, <xref:System.IDisposable> disposability içinde istedikleri katılmak diğer tüm Devralma Hiyerarşisi bağımsız desteklemek için türleri sağlayan bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="be5de-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="be5de-107">Hangi tanımlama arabirim uygun olan diğer bazı değer türleri dahil olmak üzere çeşitli türleri tarafından desteklenen ortak bir arabirim oluşturmada durumdur.</span><span class="sxs-lookup"><span data-stu-id="be5de-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="be5de-108">Değer türleri olamaz devral türlerinden dışında <xref:System.ValueType>, ancak arabirimleri uygulayabilir, bunu bir arabirimi kullanarak ortak bir taban türü sunmak için tek seçenek.</span><span class="sxs-lookup"><span data-stu-id="be5de-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="be5de-109">**✓ YAPMAK** değer türleri içeren bir dizi türleri tarafından desteklenen bazı ortak API gerekiyorsa bir arabirim tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="be5de-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="be5de-110">**✓ DÜŞÜNÜN** önceden başka bazı türünden devralan türleri işlevselliği desteklemek gereksinim duyarsanız bir arabirim tanımlama.</span><span class="sxs-lookup"><span data-stu-id="be5de-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="be5de-111">**KAÇININ x** işaret arabirimleri (hiçbir üye arabirimleriyle) kullanarak.</span><span class="sxs-lookup"><span data-stu-id="be5de-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="be5de-112">Genel olarak, bir sınıfın belirli bir karakteristik (işaret) sahip olarak işaretlemek gerekiyorsa, bir arabirim yerine özel bir öznitelik kullanın.</span><span class="sxs-lookup"><span data-stu-id="be5de-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="be5de-113">**✓ YAPMAK** bir arabirim uygulaması en az bir türü sağlar.</span><span class="sxs-lookup"><span data-stu-id="be5de-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="be5de-114">Yaptıktan arabirimi tasarımını doğrulamak için bu yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="be5de-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="be5de-115">Örneğin, <xref:System.Collections.Generic.List%601> uygulamasıdır <xref:System.Collections.Generic.IList%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="be5de-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="be5de-116">**✓ YAPMAK** tanımladığınız her bir arabirime tüketir en az bir API sağlar (bir parametre veya bir özellik arabirimi alma yöntemi yazılan arabirimi olarak).</span><span class="sxs-lookup"><span data-stu-id="be5de-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="be5de-117">Yaptıktan arabirimi tasarımı doğrulamak için bu yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="be5de-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="be5de-118">Örneğin, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> tüketir <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="be5de-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="be5de-119">**X yok** önceden sevk edilmiş bir arabirim üye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="be5de-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="be5de-120">Bunun yapılması arabirimin uygulamaları çalışmamasına neden.</span><span class="sxs-lookup"><span data-stu-id="be5de-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="be5de-121">Sürüm oluşturma sorunları önlemek için yeni bir arabirimi oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="be5de-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="be5de-122">Bu yönergeleri bölümünde açıklanan durumlar dışında genel olarak, arabirimleri yerine sınıfları yönetilen kodu yeniden kullanılabilir kitaplıkları tasarlarken seçtiğiniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="be5de-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="be5de-123">*Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="be5de-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="be5de-124">*Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="be5de-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be5de-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="be5de-125">See Also</span></span>  
 [<span data-ttu-id="be5de-126">Türü tasarım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="be5de-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="be5de-127">Framework tasarım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="be5de-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)