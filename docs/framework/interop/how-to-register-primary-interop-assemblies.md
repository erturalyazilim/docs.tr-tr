---
title: "Nasıl yapılır: Birincil Birlikte Çalışma Derlemelerini Kaydetme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b72a24f349237aa35ccae295e9e552facc21ddd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-register-primary-interop-assemblies"></a><span data-ttu-id="3822c-102">Nasıl yapılır: Birincil Birlikte Çalışma Derlemelerini Kaydetme</span><span class="sxs-lookup"><span data-stu-id="3822c-102">How to: Register Primary Interop Assemblies</span></span>
<span data-ttu-id="3822c-103">Sınıflar yalnızca COM birlikte çalışma tarafından sıralanabilir ve arabirimleri olarak her zaman hazırlanırlar.</span><span class="sxs-lookup"><span data-stu-id="3822c-103">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="3822c-104">Bazı durumlarda sınıfı sıralama için kullanılan arabirim sınıf arabirimi olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="3822c-104">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="3822c-105">Tercih ettiğiniz bir arabirim ile sınıf arabirimi geçersiz kılma hakkında daha fazla bilgi için bkz: [COM aranabilir sarmalayıcısı](../../../docs/framework/interop/com-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="3822c-105">For information about overriding the class interface with an interface of your choice, see [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md).</span></span>  
  
 <span data-ttu-id="3822c-106">Bir .NET Framework uygulamasından COM türlerini kullanmak isteyen herhangi bir geliştirici birlikte çalışabilirlik bütünleştirilmiş oluşturabilirsiniz ancak bunu yaparsanız böylece bir sorun oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3822c-106">Although any developer who wants to use COM types from a .NET Framework application can generate an interop assembly, doing so creates a problem.</span></span> <span data-ttu-id="3822c-107">Her bir geliştirici alır ve geliştirici olanlar aktarılır ve başka bir geliştirici tarafından imzalandığı ile uyumsuz benzersiz türleri kümesi oluşturan bir COM tür kitaplığı imzalar.</span><span class="sxs-lookup"><span data-stu-id="3822c-107">Each time a developer imports and signs a COM type library, that developer creates a set of unique types that are incompatible with those imported and signed by another developer.</span></span> <span data-ttu-id="3822c-108">Her geliştirici satıcı tarafından sağlanan ve imzalanmış birincil birlikte çalışma derlemesi edinmek bu tür uyumsuzluğu sorunun çözümüdür.</span><span class="sxs-lookup"><span data-stu-id="3822c-108">The solution to this type incompatibility problem is for each developer to obtain the vendor-supplied and signed primary interop assembly.</span></span>  
  
 <span data-ttu-id="3822c-109">Diğer uygulamalar için üçüncü taraf COM türlerini kullanıma planlıyorsanız, her zaman tanımladığı tür kitaplığı olarak aynı yayımcı tarafından sağlanan birincil birlikte çalışma derlemesi kullanın.</span><span class="sxs-lookup"><span data-stu-id="3822c-109">If you plan to expose third-party COM types to other applications, always use the primary interop assembly provided by the same publisher as the type library it defines.</span></span> <span data-ttu-id="3822c-110">Garantili türü uyumluluğunu sağlamanın yanı sıra, birincil birlikte çalışma derlemeleri genellikle birlikte çalışabilirlik geliştirmek için satıcı tarafından özelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3822c-110">In addition to providing guaranteed type compatibility, primary interop assemblies are often customized by the vendor to enhance interoperability.</span></span>  
  
 <span data-ttu-id="3822c-111">Üçüncü taraf COM türlerini kullanıma planlıyor musunuz olsa bile, birincil birlikte çalışma derlemesi kullanarak COM bileşenleriyle birlikte görevini kolaylaştırabilir.</span><span class="sxs-lookup"><span data-stu-id="3822c-111">Even if you do not plan to expose third-party COM types, using the primary interop assembly can ease the task of interoperating with COM components.</span></span> <span data-ttu-id="3822c-112">Ancak, bu strateji bir satıcı birincil birlikte çalışma derlemesinde tanımlanan türler için yapabileceğiniz değişiklikleri hiçbir yalıtımı sağlar.</span><span class="sxs-lookup"><span data-stu-id="3822c-112">However, this strategy provides no insulation from changes a vendor might make to types defined in a primary interop assembly.</span></span> <span data-ttu-id="3822c-113">Uygulamanız bu tür yalıtımı gerektirdiğinde, birincil birlikte çalışma derlemesi kullanmak yerine kendi birlikte çalışma derlemesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="3822c-113">When your application requires such insulation, generate your own interop assembly instead of using the primary interop assembly.</span></span>  
  
 <span data-ttu-id="3822c-114">Bunlarla başvuru önce tüm alınan birincil birlikte çalışma derlemeleri geliştirme bilgisayarınızda kaydetmeniz gerekir [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3822c-114">You must register all acquired primary interop assemblies on your development computer before you can reference them with [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span></span> <span data-ttu-id="3822c-115">Visual Studio arar ve birincil birlikte çalışma derlemesi COM tür kitaplığından bir türe başvuruda ilk kez kullanır.</span><span class="sxs-lookup"><span data-stu-id="3822c-115">Visual Studio looks for and uses a primary interop assembly the first time that you reference a type from a COM type library.</span></span> <span data-ttu-id="3822c-116">Visual Studio türü Kitaplıkla ilişkilendirilmiş birincil birlikte çalışma derlemesi bulamazsanız, onu almanızı komut istemleri veya bir birlikte çalışma derlemesi yerine oluşturmak sunar.</span><span class="sxs-lookup"><span data-stu-id="3822c-116">If Visual Studio cannot locate the primary interop assembly associated with the type library, it prompts you to acquire it or offers to create an interop assembly instead.</span></span> <span data-ttu-id="3822c-117">Benzer şekilde, [tür kitaplığı içeri Aktarıcı (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) kayıt defteri birincil birlikte çalışma derlemeleri bulmak için de kullanır.</span><span class="sxs-lookup"><span data-stu-id="3822c-117">Likewise, the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) also uses the registry to locate primary interop assemblies.</span></span>  
  
 <span data-ttu-id="3822c-118">Visual Studio kullanmayı düşünmüyorsanız birincil birlikte çalışma derlemeleri kaydetmek gerekli olmamasına karşın, kayıt iki avantajları sağlar:</span><span class="sxs-lookup"><span data-stu-id="3822c-118">Although it is not necessary to register primary interop assemblies unless you plan to use Visual Studio, registration provides two advantages:</span></span>  
  
-   <span data-ttu-id="3822c-119">Kayıtlı bir birincil birlikte çalışma derlemesi özgün tür kitaplığı kayıt defteri anahtarında açıkça işaretlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="3822c-119">A registered primary interop assembly is clearly marked under the registry key of the original type library.</span></span> <span data-ttu-id="3822c-120">Kayıt, birincil birlikte çalışma derlemesi bilgisayarınızda bulmak en iyi yoludur.</span><span class="sxs-lookup"><span data-stu-id="3822c-120">Registration is the best way for you to locate a primary interop assembly on your computer.</span></span>  
  
-   <span data-ttu-id="3822c-121">Yanlışlıkla oluşturma ve bazı zaman gelecekte bir kaydı birincil birlikte çalışma derlemesi sahip bir tür başvurmak için Visual Studio kullanıyorsanız, yeni bir birlikte çalışma derleme kullanarak önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3822c-121">You can avoid accidentally generating and using a new interop assembly if, at some time in the future, you do use Visual Studio to reference a type for which you have an unregistered primary interop assembly.</span></span>  
  
 <span data-ttu-id="3822c-122">Kullanım [derleme Kayıt Aracı (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) birincil birlikte çalışma derlemesi kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="3822c-122">Use the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register a primary interop assembly.</span></span>  
  
### <a name="to-register-a-primary-interop-assembly"></a><span data-ttu-id="3822c-123">Birincil birlikte çalışma derlemesi kaydetmek için</span><span class="sxs-lookup"><span data-stu-id="3822c-123">To register a primary interop assembly</span></span>  
  
1.  <span data-ttu-id="3822c-124">Komut isteminde, şunları yazın:</span><span class="sxs-lookup"><span data-stu-id="3822c-124">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="3822c-125">**RegAsm** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="3822c-125">**regasm** *assemblyname*</span></span>  
  
     <span data-ttu-id="3822c-126">Bu komutta *assemblyname* kayıtlı derlemenin dosya adı.</span><span class="sxs-lookup"><span data-stu-id="3822c-126">In this command, *assemblyname* is the file name of the assembly that is registered.</span></span> <span data-ttu-id="3822c-127">RegAsm.exe özgün tür kitaplığı olarak aynı kayıt defteri anahtarı altında birincil birlikte çalışma derlemesi için bir giriş ekler.</span><span class="sxs-lookup"><span data-stu-id="3822c-127">Regasm.exe adds an entry for the primary interop assembly under the same registry key as the original type library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3822c-128">Örnek</span><span class="sxs-lookup"><span data-stu-id="3822c-128">Example</span></span>  
 <span data-ttu-id="3822c-129">Aşağıdaki örnek kaydeder `CompanyA.UtilLib.dll` birincil birlikte çalışma derlemesi.</span><span class="sxs-lookup"><span data-stu-id="3822c-129">The following example registers the `CompanyA.UtilLib.dll` primary interop assembly.</span></span>  
  
```  
regasm CompanyA.UtilLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3822c-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3822c-130">See Also</span></span>  
 [<span data-ttu-id="3822c-131">Birincil birlikte çalışma derlemeleri ile programlama</span><span class="sxs-lookup"><span data-stu-id="3822c-131">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)  
 [<span data-ttu-id="3822c-132">Birincil birlikte çalışma derlemeleri bulma</span><span class="sxs-lookup"><span data-stu-id="3822c-132">Locating Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/d6768e4b-cd80-414d-a4f8-05d979eb393b)  
 [<span data-ttu-id="3822c-133">Birincil birlikte çalışma derlemeleri yeniden dağıtma</span><span class="sxs-lookup"><span data-stu-id="3822c-133">Redistributing Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/e76384f0-d631-474c-bdbd-13884cba0265)