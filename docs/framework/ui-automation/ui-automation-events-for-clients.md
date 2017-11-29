---
title: "İstemciler İçin UI Otomasyon Olayları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
caps.latest.revision: "32"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 1dfb4c1acd12b58d5c4f032ebe0ad8c56fc0db87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-events-for-clients"></a><span data-ttu-id="5040a-102">İstemciler İçin UI Otomasyon Olayları</span><span class="sxs-lookup"><span data-stu-id="5040a-102">UI Automation Events for Clients</span></span>
> [!NOTE]
>  <span data-ttu-id="5040a-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="5040a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5040a-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5040a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5040a-105">Bu konuda açıklanmaktadır nasıl [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] olayları UI Otomasyon istemcileri tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5040a-105">This topic describes how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] events are used by UI Automation clients.</span></span>  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="5040a-106">istemcilerin ilgi olaylarına abone olma olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="5040a-106"> allows clients to subscribe to events of interest.</span></span> <span data-ttu-id="5040a-107">Bu özellik, sürekli olarak tüm yoklamak için gereksinimini ortadan kaldırarak performansı artırır [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] tüm bilgileri, yapı veya durumu değişip değişmediğini görmek için sistemdeki öğeleri.</span><span class="sxs-lookup"><span data-stu-id="5040a-107">This capability improves performance by eliminating the need to continually poll all the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements in the system to see if any information, structure, or state has changed.</span></span>  
  
 <span data-ttu-id="5040a-108">Verimliliği de yalnızca tanımlı bir kapsamdaki olayları dinler özelliği tarafından geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5040a-108">Efficiency is also improved by the ability to listen for events only within a defined scope.</span></span> <span data-ttu-id="5040a-109">Örneğin, tüm odak değişikliği olaylarını istemci dinlediği [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] öğeleri ağacında ya da tek bir öğe ve alt öğeleri.</span><span class="sxs-lookup"><span data-stu-id="5040a-109">For example, a client can listen for focus change events on all [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements in the tree, or on just one element and its descendants.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5040a-110">Tüm olası olaylar tarafından oluşturulur varsayın olmayan bir [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sağlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="5040a-110">Do not assume that all possible events are raised by a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] provider.</span></span> <span data-ttu-id="5040a-111">Örneğin, tüm özellik değişikliği olayları için standart proxy sağlayıcıları tarafından gerçekleştirilen neden [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] ve [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="5040a-111">For example, not all property changes cause events to be raised by the standard proxy providers for [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls.</span></span>  
  
 <span data-ttu-id="5040a-112">Daha geniş bir görünümü için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] olayları görmek [UI Otomasyonu olaylarına genel bakış](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5040a-112">For a broader view of [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a><span data-ttu-id="5040a-113">Olaylara abone olma</span><span class="sxs-lookup"><span data-stu-id="5040a-113">Subscribing to Events</span></span>  
 <span data-ttu-id="5040a-114">İstemci uygulamaları, aşağıdaki yöntemlerden birini kullanarak bir olay işleyicisi kaydederek belirli bir türde olaylarına abone olma.</span><span class="sxs-lookup"><span data-stu-id="5040a-114">Client applications subscribe to events of a particular kind by registering an event handler, using one of the following methods.</span></span>  
  
|<span data-ttu-id="5040a-115">Yöntem</span><span class="sxs-lookup"><span data-stu-id="5040a-115">Method</span></span>|<span data-ttu-id="5040a-116">Olay türü</span><span class="sxs-lookup"><span data-stu-id="5040a-116">Event Type</span></span>|<span data-ttu-id="5040a-117">Olay bağımsız değişken türü</span><span class="sxs-lookup"><span data-stu-id="5040a-117">Event Arguments Type</span></span>|<span data-ttu-id="5040a-118">Temsilci türü</span><span class="sxs-lookup"><span data-stu-id="5040a-118">Delegate Type</span></span>|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|<span data-ttu-id="5040a-119">Odağı Değiştir</span><span class="sxs-lookup"><span data-stu-id="5040a-119">Focus change</span></span>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|<span data-ttu-id="5040a-120">Özellik değişikliği</span><span class="sxs-lookup"><span data-stu-id="5040a-120">Property change</span></span>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|<span data-ttu-id="5040a-121">Yapı değişikliğine</span><span class="sxs-lookup"><span data-stu-id="5040a-121">Structure change</span></span>|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|<span data-ttu-id="5040a-122">Tarafından tanımlanan tüm diğer olaylar, bir<xref:System.Windows.Automation.AutomationEvent></span><span class="sxs-lookup"><span data-stu-id="5040a-122">All other events, identified by an <xref:System.Windows.Automation.AutomationEvent></span></span>|<span data-ttu-id="5040a-123"><xref:System.Windows.Automation.AutomationEventArgs>veya<xref:System.Windows.Automation.WindowClosedEventArgs></span><span class="sxs-lookup"><span data-stu-id="5040a-123"><xref:System.Windows.Automation.AutomationEventArgs> or <xref:System.Windows.Automation.WindowClosedEventArgs></span></span>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 <span data-ttu-id="5040a-124">Bir yöntemini çağırmadan önce olayını işlemek için temsilci yöntemi oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5040a-124">Before calling the method, you must create a delegate method to handle the event.</span></span> <span data-ttu-id="5040a-125">İsterseniz, farklı türde tek bir yöntem olayları işlemek ve bu yöntem tablosundaki yöntemlerini birine birden fazla çağrı geçirin.</span><span class="sxs-lookup"><span data-stu-id="5040a-125">If you prefer, you can handle different kinds of events in a single method, and pass this method in multiple calls to one of the methods in the table.</span></span> <span data-ttu-id="5040a-126">Örneğin, bir tek <xref:System.Windows.Automation.AutomationEventHandler> farklı aşağıdakilere göre çeşitli olayları işlemek için ayarlanabilir <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.</span><span class="sxs-lookup"><span data-stu-id="5040a-126">For example, a single <xref:System.Windows.Automation.AutomationEventHandler> can be set up to handle various events differently according to the <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5040a-127">Pencere kapatıldığında olayları işlemek için olay işleyici olarak geçirilen bağımsız değişken türü cast <xref:System.Windows.Automation.WindowClosedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="5040a-127">To process window-closed events, cast the argument type that is passed to the event handler as <xref:System.Windows.Automation.WindowClosedEventArgs>.</span></span> <span data-ttu-id="5040a-128">Çünkü [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] pencere öğesi artık geçerli değil, kullanamazsınız `sender` bilgiler; almak için parametre kullanmak <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> yerine.</span><span class="sxs-lookup"><span data-stu-id="5040a-128">Because the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] element for the window is no longer valid, you cannot use the `sender` parameter to retrieve information; use <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> instead.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5040a-129">Uygulamanızı olayları kendi alabilirse [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], uygulamanızın kullanmayın [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] iş parçacığı olaylarına abone olma ya da bunlara ilişkin aboneliği.</span><span class="sxs-lookup"><span data-stu-id="5040a-129">If your application might receive events from its own [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], do not use your application's [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] thread to subscribe to events, or to unsubscribe.</span></span> <span data-ttu-id="5040a-130">Bunun yapılması için beklenmeyen davranışlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="5040a-130">Doing so might lead to unpredictable behavior.</span></span> <span data-ttu-id="5040a-131">Daha fazla bilgi için bkz: [UI Otomasyon iş parçacığı oluşturma sorunları](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5040a-131">For more information, see [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).</span></span>  
  
 <span data-ttu-id="5040a-132">Kapatma sırasında veya ne zaman [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] olayları artık uygulamaya ilgi, UI Otomasyon istemcileri aşağıdaki yöntemlerden birini çağrı.</span><span class="sxs-lookup"><span data-stu-id="5040a-132">On shutdown, or when [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events are no longer of interest to the application, UI Automation clients should call one of the following methods.</span></span>  
  
|<span data-ttu-id="5040a-133">Yöntem</span><span class="sxs-lookup"><span data-stu-id="5040a-133">Method</span></span>|<span data-ttu-id="5040a-134">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5040a-134">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|<span data-ttu-id="5040a-135">Kullanarak kayıtlı bir olay işleyicisi kaydını siler <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="5040a-135">Unregisters an event handler that was registered by using <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|<span data-ttu-id="5040a-136">Kullanarak kayıtlı bir olay işleyicisi kaydını siler <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="5040a-136">Unregisters an event handler that was registered by using <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.</span></span>|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|<span data-ttu-id="5040a-137">Kullanarak kayıtlı bir olay işleyicisi kaydını siler <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="5040a-137">Unregisters an event handler that was registered by using <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.</span></span>|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|<span data-ttu-id="5040a-138">Tüm kayıtlı olay işleyicileri kaydını siler.</span><span class="sxs-lookup"><span data-stu-id="5040a-138">Unregisters all registered event handlers.</span></span>|  
  
 <span data-ttu-id="5040a-139">Örnek kod, bkz: [UI Otomasyon olaylarına abone](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).</span><span class="sxs-lookup"><span data-stu-id="5040a-139">For example code, see [Subscribe to UI Automation Events](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5040a-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5040a-140">See Also</span></span>  
 [<span data-ttu-id="5040a-141">UI Otomasyon olaylarına abone olma</span><span class="sxs-lookup"><span data-stu-id="5040a-141">Subscribe to UI Automation Events</span></span>](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [<span data-ttu-id="5040a-142">UI Otomasyonu olaylarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="5040a-142">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [<span data-ttu-id="5040a-143">UI Otomasyon özelliklerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="5040a-143">UI Automation Properties Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [<span data-ttu-id="5040a-144">TrackFocus örnek</span><span class="sxs-lookup"><span data-stu-id="5040a-144">TrackFocus Sample</span></span>](http://msdn.microsoft.com/en-us/4a91c0af-6bb5-4d38-a743-cf136f268fc9)