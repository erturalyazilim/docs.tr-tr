---
title: "UI Otomasyonu Dönüştürme Denetim Düzenini Uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: df871c7f7214a6135db2493972dd76f41ce31aaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="164ec-102">UI Otomasyonu Dönüştürme Denetim Düzenini Uygulama</span><span class="sxs-lookup"><span data-stu-id="164ec-102">Implementing the UI Automation Transform Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="164ec-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="164ec-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="164ec-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="164ec-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="164ec-105">Bu konu kılavuzları ve uygulamak için kuralları tanıtır <xref:System.Windows.Automation.Provider.ITransformProvider>, özellikleri, yöntemleri ve etkinlikleri hakkında bilgiler dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="164ec-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="164ec-106">Ek başvurular bağlantılar konunun sonunda listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="164ec-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="164ec-107"><xref:System.Windows.Automation.TransformPattern> Denetim düzeni taşınmış, yeniden boyutlandırılmış veya iki boyutlu bir boşluğuna Döndürülmüş denetimleri desteklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="164ec-107">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="164ec-108">Bu denetim düzeni uygulama denetimleri örnekleri için bkz: [denetim düzeni eşleştirmesi UI Otomasyon istemcileri için](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="164ec-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="164ec-109">Uygulama rehberi ve kuralları</span><span class="sxs-lookup"><span data-stu-id="164ec-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="164ec-110">Dönüştürme denetim düzenini uygulama, aşağıdaki yönergeleri ve kuralları dikkat edin:</span><span class="sxs-lookup"><span data-stu-id="164ec-110">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="164ec-111">Bu denetim düzeni için destek masaüstündeki nesneler için sınırlı değildir.</span><span class="sxs-lookup"><span data-stu-id="164ec-111">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="164ec-112">Alt taşınmış, yeniden boyutlandırılmış veya serbestçe kapsayıcı sınırlar içinde Döndürülmüş bu denetim düzeni ayrıca bir kapsayıcı nesne gruplar tarafından desteklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="164ec-112">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
-   <span data-ttu-id="164ec-113">Bir nesne taşınamaz, yeniden boyutlandırılabilir ya da sonuçta elde edilen ekran konumuna veya tamamen kapsayıcısının ve bu nedenle klavye için erişilemez koordinatları dışında olabilir (örneğin, üst düzey bir pencere off-screen taşındığında veya bir fare şekilde Döndürülmüş alt nesne kapsayıcının görünüm penceresinin sınırları dışında taşınır).</span><span class="sxs-lookup"><span data-stu-id="164ec-113">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="164ec-114">Bu durumlarda, nesne, istenen ekran koordinatları olarak mümkün olduğunca kapsayıcı sınırlar içinde geçersiz üst veya sol koordinatları ile yakın yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="164ec-114">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
-   <span data-ttu-id="164ec-115">Bir nesne taşınırsa, birden çok monitör sistemler için yeniden boyutlandırılmış veya birleştirilmiş masaüstü ekran koordinatları tamamen dışında döndürülen nesne birincil monitörde istenen koordinatları olarak mümkün olduğunca yakın yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="164ec-115">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
-   <span data-ttu-id="164ec-116">Tüm parametreleri ve özellik değerlerini mutlak ve yerel ayar bağımsızdır.</span><span class="sxs-lookup"><span data-stu-id="164ec-116">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="164ec-117">Gerekli üyeleri ITransformProvider için</span><span class="sxs-lookup"><span data-stu-id="164ec-117">Required Members for ITransformProvider</span></span>  
 <span data-ttu-id="164ec-118">Aşağıdaki özellikleri ve yöntemleri uygulamak için gerekli olan <xref:System.Windows.Automation.Provider.ITransformProvider>.</span><span class="sxs-lookup"><span data-stu-id="164ec-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="164ec-119">Gerekli üyeleri</span><span class="sxs-lookup"><span data-stu-id="164ec-119">Required members</span></span>|<span data-ttu-id="164ec-120">Üye türü</span><span class="sxs-lookup"><span data-stu-id="164ec-120">Member type</span></span>|<span data-ttu-id="164ec-121">Notlar</span><span class="sxs-lookup"><span data-stu-id="164ec-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="164ec-122">Özellik</span><span class="sxs-lookup"><span data-stu-id="164ec-122">Property</span></span>|<span data-ttu-id="164ec-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="164ec-124">Özellik</span><span class="sxs-lookup"><span data-stu-id="164ec-124">Property</span></span>|<span data-ttu-id="164ec-125">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="164ec-126">Özellik</span><span class="sxs-lookup"><span data-stu-id="164ec-126">Property</span></span>|<span data-ttu-id="164ec-127">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="164ec-128">Yöntem</span><span class="sxs-lookup"><span data-stu-id="164ec-128">Method</span></span>|<span data-ttu-id="164ec-129">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="164ec-130">Yöntem</span><span class="sxs-lookup"><span data-stu-id="164ec-130">Method</span></span>|<span data-ttu-id="164ec-131">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="164ec-132">Yöntem</span><span class="sxs-lookup"><span data-stu-id="164ec-132">Method</span></span>|<span data-ttu-id="164ec-133">Yok.</span><span class="sxs-lookup"><span data-stu-id="164ec-133">None</span></span>|  
  
 <span data-ttu-id="164ec-134">Bu denetim düzeni ilişkili olay vardır.</span><span class="sxs-lookup"><span data-stu-id="164ec-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="164ec-135">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="164ec-135">Exceptions</span></span>  
 <span data-ttu-id="164ec-136">Sağlayıcıları aşağıdaki özel durumlar oluşturma gerekir.</span><span class="sxs-lookup"><span data-stu-id="164ec-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="164ec-137">Özel durum türü</span><span class="sxs-lookup"><span data-stu-id="164ec-137">Exception Type</span></span>|<span data-ttu-id="164ec-138">Koşul</span><span class="sxs-lookup"><span data-stu-id="164ec-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="164ec-139">-İf <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> false olur.</span><span class="sxs-lookup"><span data-stu-id="164ec-139">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="164ec-140">-İf <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> false olur.</span><span class="sxs-lookup"><span data-stu-id="164ec-140">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="164ec-141">-İf <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> false olur.</span><span class="sxs-lookup"><span data-stu-id="164ec-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="164ec-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="164ec-142">See Also</span></span>  
 [<span data-ttu-id="164ec-143">UI Otomasyon denetim düzenlerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="164ec-143">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="164ec-144">UI Otomasyon sağlayıcısında denetim düzenleri desteği</span><span class="sxs-lookup"><span data-stu-id="164ec-144">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="164ec-145">İstemciler için UI Otomasyon denetim düzenleri</span><span class="sxs-lookup"><span data-stu-id="164ec-145">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="164ec-146">UI Otomasyon ağacına genel bakış</span><span class="sxs-lookup"><span data-stu-id="164ec-146">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="164ec-147">UI otomasyonda önbelleğe almayı kullanma</span><span class="sxs-lookup"><span data-stu-id="164ec-147">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)