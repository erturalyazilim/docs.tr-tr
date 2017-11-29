---
title: "Birleştirilmiş Kaynak Sözlükleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ce02b772bacf2115a1bb74039fdff30a46fea8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="merged-resource-dictionaries"></a><span data-ttu-id="1dfa9-102">Birleştirilmiş Kaynak Sözlükleri</span><span class="sxs-lookup"><span data-stu-id="1dfa9-102">Merged Resource Dictionaries</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1dfa9-103">kaynakları birleştirilmiş kaynak sözlüğü özelliğini desteklemez.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-103"> resources support a merged resource dictionary feature.</span></span> <span data-ttu-id="1dfa9-104">Bu özellik, kaynaklar bölümünü tanımlamak için bir yol sağlar. bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derlenmiş dışında uygulama [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] uygulama.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-104">This feature provides a way to define the resources portion of a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application outside of the compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] application.</span></span> <span data-ttu-id="1dfa9-105">Kaynaklar sonra uygulamalar arasında paylaşılabilir ve ayrıca daha rahat yerelleştirme için yalıtılır.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-105">Resources can then be shared across applications and are also more conveniently isolated for localization.</span></span>  
  
## <a name="introducing-a-merged-resource-dictionary"></a><span data-ttu-id="1dfa9-106">Birleştirilmiş kaynak sözlüğünü Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="1dfa9-106">Introducing a Merged Resource Dictionary</span></span>  
 <span data-ttu-id="1dfa9-107">Biçimlendirme içinde bir sayfaya birleştirilmiş kaynak sözlüğünü tanıtmak için aşağıdaki sözdizimini kullanın:</span><span class="sxs-lookup"><span data-stu-id="1dfa9-107">In markup, you use the following syntax to introduce a merged resource dictionary into a page:</span></span>  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 <span data-ttu-id="1dfa9-108">Unutmayın <xref:System.Windows.ResourceDictionary> öğesi yok bir [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md), bir kaynak koleksiyondaki tüm öğeleri için genellikle gerekli olduğu.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-108">Note that the <xref:System.Windows.ResourceDictionary> element does not have an [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), which is generally required for all items in a resource collection.</span></span> <span data-ttu-id="1dfa9-109">Ancak başka bir <xref:System.Windows.ResourceDictionary> içinde başvuru <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> koleksiyonudur bu birleştirilmiş kaynak sözlüğü senaryosu için ayrılmış özel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-109">But another <xref:System.Windows.ResourceDictionary> reference within the <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> collection is a special case, reserved for this merged resource dictionary scenario.</span></span> <span data-ttu-id="1dfa9-110"><xref:System.Windows.ResourceDictionary> Birleştirilmiş tanıtır kaynak sözlüğü olamaz bir [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="1dfa9-110">The <xref:System.Windows.ResourceDictionary> that introduces a merged resource dictionary cannot have an [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span> <span data-ttu-id="1dfa9-111">Genellikle, her <xref:System.Windows.ResourceDictionary> içinde <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> koleksiyonunu belirtir bir <xref:System.Windows.ResourceDictionary.Source%2A> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-111">Typically, each <xref:System.Windows.ResourceDictionary> within the <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> collection specifies a <xref:System.Windows.ResourceDictionary.Source%2A> attribute.</span></span> <span data-ttu-id="1dfa9-112">Değeri <xref:System.Windows.ResourceDictionary.Source%2A> olması gereken bir [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] birleştirilecek kaynak dosyasının konumunu giderir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-112">The value of <xref:System.Windows.ResourceDictionary.Source%2A> should be a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] that resolves to the location of the resources file to be merged.</span></span> <span data-ttu-id="1dfa9-113">Bu hedef [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] başka olmalıdır [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosyası ile <xref:System.Windows.ResourceDictionary> , kök öğesi olarak.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-113">The destination of that [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] must be another [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, with <xref:System.Windows.ResourceDictionary> as its root element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dfa9-114">İçindeki kaynaklara tanımlamak için yasal bir <xref:System.Windows.ResourceDictionary> belirtilen birleştirilmiş bir sözlük belirtmek için bir alternatif olarak da <xref:System.Windows.ResourceDictionary.Source%2A>, veya hangi kaynak belirtilen kaynaktan içerilen yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-114">It is legal to define resources within a <xref:System.Windows.ResourceDictionary> that is specified as a merged dictionary, either as an alternative to specifying <xref:System.Windows.ResourceDictionary.Source%2A>, or in addition to whatever resources are included from the specified source.</span></span> <span data-ttu-id="1dfa9-115">Ancak, bu yaygın bir senaryo değildir; Birleştirilmiş sözlük için ana senaryo dış dosya konumlarından kaynakları birleştirmektir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-115">However, this is not a common scenario; the main scenario for merged dictionaries is to merge resources from external file locations.</span></span> <span data-ttu-id="1dfa9-116">Bir sayfa için biçimlendirme içindeki kaynaklara belirtmek istiyorsanız, genellikle bu ana tanımlamanız gerekir <xref:System.Windows.ResourceDictionary> ve birleştirilmiş sözlükler içinde değil.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-116">If you want to specify resources within the markup for a page, you should typically define these in the main <xref:System.Windows.ResourceDictionary> and not in the merged dictionaries.</span></span>  
  
## <a name="merged-dictionary-behavior"></a><span data-ttu-id="1dfa9-117">Birleştirilmiş sözlük davranışı</span><span class="sxs-lookup"><span data-stu-id="1dfa9-117">Merged Dictionary Behavior</span></span>  
 <span data-ttu-id="1dfa9-118">Birleştirilmiş sözlük kaynaklarında içine birleştirilmiş ana kaynak sözlüğü kapsamını hemen sonra kaynak arama kapsamı bir konumda kaplar.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-118">Resources in a merged dictionary occupy a location in the resource lookup scope that is just after the scope of the main resource dictionary they are merged into.</span></span> <span data-ttu-id="1dfa9-119">Kaynak anahtarı herhangi bir tek tek dictionary içinde benzersiz olması gerekse de, bir anahtar birleştirilmiş sözlükler kümesinde birden çok kez yer alabilir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-119">Although a resource key must be unique within any individual dictionary, a key can exist multiple times in a set of merged dictionaries.</span></span> <span data-ttu-id="1dfa9-120">Bu durumda, döndürülen kaynak sırayla bulunan son sözlükten gelecektir <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-120">In this case, the resource that is returned will come from the last dictionary found sequentially in the <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> collection.</span></span> <span data-ttu-id="1dfa9-121">Varsa <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> koleksiyonu içinde tanımlanmışsa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], birleştirilmiş sözlükler koleksiyondaki öğelerin sırasını biçimlendirmede sağlanan sırasıdır sonra.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-121">If the <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> collection was defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], then the order of the merged dictionaries in the collection is the order of the elements as provided in the markup.</span></span> <span data-ttu-id="1dfa9-122">Bir anahtar birincil sözlük hem de birleştirilmiş bir sözlük tanımlanmışsa, döndürülen kaynak birincil sözlükten gelecektir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-122">If a key is defined in the primary dictionary and also in a dictionary that was merged, then the resource that is returned will come from the primary dictionary.</span></span> <span data-ttu-id="1dfa9-123">Bu kapsama kuralları eşit olarak statik kaynak başvuruları hem dinamik kaynak başvuruları uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-123">These scoping rules apply equally for both static resource references and dynamic resource references.</span></span>  
  
### <a name="merged-dictionaries-and-code"></a><span data-ttu-id="1dfa9-124">Birleştirilmiş sözlükler ve kod</span><span class="sxs-lookup"><span data-stu-id="1dfa9-124">Merged Dictionaries and Code</span></span>  
 <span data-ttu-id="1dfa9-125">Birleştirilmiş sözlük eklenebilir bir `Resources` kod aracılığıyla sözlük.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-125">Merged dictionaries can be added to a `Resources` dictionary through code.</span></span> <span data-ttu-id="1dfa9-126">Varsayılan olarak, başlangıçta boş <xref:System.Windows.ResourceDictionary> için bulunduğunu `Resources` özelliği de varsayılan, başlangıçta boş olan <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> koleksiyon özelliği.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-126">The default, initially empty <xref:System.Windows.ResourceDictionary> that exists for any `Resources` property also has a default, initially empty <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> collection property.</span></span> <span data-ttu-id="1dfa9-127">Kod aracılığıyla birleştirilmiş sözlük eklemek için istenen birincil başvuru elde <xref:System.Windows.ResourceDictionary>, Al, <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> özellik değeri ve arama `Add` genel `Collection` içinde bulunan <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-127">To add a merged dictionary through code, you obtain a reference to the desired primary <xref:System.Windows.ResourceDictionary>, get its <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> property value, and call `Add` on the generic `Collection` that is contained in <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>.</span></span> <span data-ttu-id="1dfa9-128">Eklediğiniz nesne yeni bir olmalıdır <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-128">The object you add must be a new <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="1dfa9-129">Kod içinde ayarlamayın <xref:System.Windows.ResourceDictionary.Source%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-129">In code, you do not set the <xref:System.Windows.ResourceDictionary.Source%2A> property.</span></span> <span data-ttu-id="1dfa9-130">Bunun yerine, edinmelidir bir <xref:System.Windows.ResourceDictionary> tane oluşturarak veya bir yükleme nesne.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-130">Instead, you must obtain a <xref:System.Windows.ResourceDictionary> object by either creating one or loading one.</span></span> <span data-ttu-id="1dfa9-131">Var olan yüklemek için tek yönlü <xref:System.Windows.ResourceDictionary> çağırmak için <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> varolan üzerinde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sahip dosya akışı bir <xref:System.Windows.ResourceDictionary> köküne, ardından <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> dönüş değeri için <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-131">One way to load an existing <xref:System.Windows.ResourceDictionary> to call <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> on an existing [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file stream that has a <xref:System.Windows.ResourceDictionary> root, then casting the <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> return value to <xref:System.Windows.ResourceDictionary>.</span></span>  
  
### <a name="merged-resource-dictionary-uris"></a><span data-ttu-id="1dfa9-132">Birleştirilmiş kaynak sözlüğü URI'leri</span><span class="sxs-lookup"><span data-stu-id="1dfa9-132">Merged Resource Dictionary URIs</span></span>  
 <span data-ttu-id="1dfa9-133">Tarafından belirtilen birleştirilmiş kaynak sözlüğünü içeren ilişkin birçok tekniği vardır [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] kullanacağınız biçimi.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-133">There are several techniques for how to include a merged resource dictionary, which are indicated by the [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] format that you will use.</span></span> <span data-ttu-id="1dfa9-134">Genel anlamda, bu teknikler iki kategoriye ayrılabilir: projenin bir parçası olarak derlenmiş kaynaklar ve projenin bir parçası derlenmemiş kaynaklar.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-134">Broadly speaking, these techniques can be divided into two categories: resources that are compiled as part of the project, and resources that are not compiled as part of the project.</span></span>  
  
 <span data-ttu-id="1dfa9-135">Projenin bir parçası olarak derlenmiş kaynaklar için kaynak konuma başvuruyor göreli bir yol kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-135">For resources that are compiled as part of the project, you can use a relative path that refers to the resource location.</span></span> <span data-ttu-id="1dfa9-136">Göreli yol derlenirken değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-136">The relative path is evaluated during compilation.</span></span> <span data-ttu-id="1dfa9-137">Kaynağınız kaynak yapı eylemi projenin bir parçası olarak tanımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-137">Your resource must be defined as part of the project as a Resource build action.</span></span> <span data-ttu-id="1dfa9-138">Kaynak olarak proje içinde kaynak .xaml dosyasında eklerseniz, kaynak dosyanın çıkış dizinine Kopyala gerekmez, kaynak önceden derlenmiş uygulama içinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-138">If you include a resource .xaml file in the project as Resource, you do not need to copy the resource file to the output directory, the resource is already included within the compiled application.</span></span> <span data-ttu-id="1dfa9-139">İçerik yapı eylemini de kullanabilirsiniz, ancak sonra dosyaları çıkış dizinine kopyalayın ve da aynı yol ilişkisi kaynak dosyalarında yürütülebilir dosyaya dağıtmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-139">You can also use Content build action, but you must then copy the files to the output directory and also deploy the resource files in the same path relationship to the executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dfa9-140">Katıştırılmış kaynak yapı eylemi kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-140">Do not use the Embedded Resource build action.</span></span> <span data-ttu-id="1dfa9-141">Yapı eylemi için desteklenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulamalar ancak çözünürlüğünü <xref:System.Windows.ResourceDictionary.Source%2A> dahil değil <xref:System.Resources.ResourceManager>ve bu nedenle tek tek kaynak akış dışında ayıramazsınız.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-141">The build action itself is supported for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, but the resolution of <xref:System.Windows.ResourceDictionary.Source%2A> does not incorporate <xref:System.Resources.ResourceManager>, and thus cannot separate the individual resource out of the stream.</span></span> <span data-ttu-id="1dfa9-142">Ayrıca kullandığınız sürece diğer amaçlar için hala katıştırılmış kaynakları kullanabilirsiniz <xref:System.Resources.ResourceManager> kaynaklara erişmek için.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-142">You could still use Embedded Resource for other purposes so long as you also used <xref:System.Resources.ResourceManager> to access the resources.</span></span>  
  
 <span data-ttu-id="1dfa9-143">İlişkili bir teknik Pack URI kullanmaktır bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosya ve kaynak olarak başvurmaktır.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-143">A related technique is to use a Pack URI to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, and refer to it as Source.</span></span> <span data-ttu-id="1dfa9-144">Paketi URI bileşenleri başvurulan derlemeler ve diğer teknik başvuru sağlar.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-144">Pack URI enables references to components of referenced assemblies and other techniques.</span></span> <span data-ttu-id="1dfa9-145">Paketi URI'ler hakkında daha fazla bilgi için bkz: [WPF Uygulama kaynağı, içerik ve veri dosyalarını](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="1dfa9-145">For more information on Pack URIs, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="1dfa9-146">Projenin bir parçası derlenmemiş kaynaklar için URI çalışma zamanında değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-146">For resources that are not compiled as part of the project, the URI is evaluated at run time.</span></span> <span data-ttu-id="1dfa9-147">Sık kullanılan URI taşıma gibi dosya kullanabilirsiniz: veya http: kaynak dosyasına başvurmak için.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-147">You can use a common URI transport such as file: or http: to refer to the resource file.</span></span> <span data-ttu-id="1dfa9-148">Derlenmemiş kaynak yaklaşımı kullanmanın olumsuz yanı o dosyadır: erişim gerektiren ek dağıtım adımları ve http: erişim Internet güvenlik bölgesi anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-148">The disadvantage of using the noncompiled resource approach is that file: access requires additional deployment steps, and http: access implies the Internet security zone.</span></span>  
  
### <a name="reusing-merged-dictionaries"></a><span data-ttu-id="1dfa9-149">Birleştirilen sözlükleri yeniden kullanma</span><span class="sxs-lookup"><span data-stu-id="1dfa9-149">Reusing Merged Dictionaries</span></span>  
 <span data-ttu-id="1dfa9-150">Yeniden ya da birleştirmek için kaynak sözlüğü herhangi başvurulabilir olduğundan birleştirilmiş kaynak sözlüklerindeki uygulamalar arasında paylaşmak geçerli [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dfa9-150">You can reuse or share merged resource dictionaries between applications, because the resource dictionary to merge can be referenced through any valid [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span> <span data-ttu-id="1dfa9-151">Tam olarak bunu nasıl yapacağınız, uygulama dağıtım stratejinizi bağlıdır ve hangi uygulama modelini izleyin.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-151">Exactly how you do this will depend on your application deployment strategy and which application model you follow.</span></span> <span data-ttu-id="1dfa9-152">Yukarıda sözü edilen Pack URI stratejisi genellikle birleştirilmiş bir kaynak birden çok projede geliştirme sırasında bir derleme başvurusu paylaşarak kaynak için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-152">The aforementioned Pack URI strategy provides a way to commonly source a merged resource across multiple projects during development by sharing an assembly reference.</span></span> <span data-ttu-id="1dfa9-153">Bu senaryoda kaynaklar hala istemci tarafından dağıtılan ve uygulamalardan en az biri başvurulan derlemeyi dağıtmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-153">In this scenario the resources are still distributed by the client, and at least one of the applications must deploy the referenced assembly.</span></span> <span data-ttu-id="1dfa9-154">Http protokolünü kullanan dağıtılmış bir URI üzerinden birleştirilmiş kaynaklara başvurmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-154">It is also possible to reference merged resources through a distributed URI that uses the http protocol.</span></span>  
  
 <span data-ttu-id="1dfa9-155">Yerel uygulama dosyaları veya başka bir olası birleştirilmiş sözlük yerel paylaşılan depolama olarak birleştirilmiş sözlükleri yazma / uygulama dağıtım senaryosudur.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-155">Writing merged dictionaries as local application files or to local shared storage is another possible merged dictionary / application deployment scenario.</span></span>  
  
### <a name="localization"></a><span data-ttu-id="1dfa9-156">Yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dfa9-156">Localization</span></span>  
 <span data-ttu-id="1dfa9-157">Yerelleştirilmesi gereken kaynaklar birincil sözlükler birleştirilir ve olarak gevşek tutulan sözlükler yalıtılmış olması durumunda [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], bu dosyalar ayrı olarak yerelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-157">If resources that need to be localized are isolated to dictionaries that are merged into primary dictionaries, and kept as loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], these files can be localized separately.</span></span> <span data-ttu-id="1dfa9-158">Bu teknik, uydu kaynak derlemelerini yerelleştirme için basit bir alternatifidir.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-158">This technique is a lightweight alternative to localizing  the satellite resource assemblies.</span></span> <span data-ttu-id="1dfa9-159">Ayrıntılar için bkz [WPF Genelleştirme ve yerelleştirme genel bakış](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1dfa9-159">For details, see [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfa9-160">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1dfa9-160">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 [<span data-ttu-id="1dfa9-161">XAML kaynakları</span><span class="sxs-lookup"><span data-stu-id="1dfa9-161">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="1dfa9-162">Kaynaklar ve kod</span><span class="sxs-lookup"><span data-stu-id="1dfa9-162">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="1dfa9-163">WPF Uygulama kaynağı, içerik ve veri dosyaları</span><span class="sxs-lookup"><span data-stu-id="1dfa9-163">WPF Application Resource, Content, and Data Files</span></span>](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)