---
title: "&lt;Clear&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 34e6e7c505dab135452664fdb815ee3e905a2ad0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="7e04b-102">&lt;Clear&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;</span><span class="sxs-lookup"><span data-stu-id="7e04b-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="7e04b-103">Temizler `Listeners` izleme için koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="7e04b-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="7e04b-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="7e04b-104">\<configuration></span></span>  
<span data-ttu-id="7e04b-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7e04b-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7e04b-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="7e04b-106">\<trace></span></span>  
<span data-ttu-id="7e04b-107">\<dinleyicileri ></span><span class="sxs-lookup"><span data-stu-id="7e04b-107">\<listeners></span></span>  
<span data-ttu-id="7e04b-108">\<Clear ></span><span class="sxs-lookup"><span data-stu-id="7e04b-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e04b-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7e04b-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e04b-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7e04b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e04b-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7e04b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e04b-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7e04b-112">Attributes</span></span>  
 <span data-ttu-id="7e04b-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="7e04b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e04b-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7e04b-114">Child Elements</span></span>  
 <span data-ttu-id="7e04b-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="7e04b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e04b-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7e04b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7e04b-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="7e04b-117">Element</span></span>|<span data-ttu-id="7e04b-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7e04b-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7e04b-119">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="7e04b-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7e04b-120">Toplamak, depolamak ve iletileri ve izleme anahtarı ayarlandığı düzeyi rota izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="7e04b-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="7e04b-121">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="7e04b-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="7e04b-122">Toplamak, depolamak ve iletileri yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="7e04b-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="7e04b-123">Dinleyicileri uygun hedef İzleme çıkışı yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="7e04b-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e04b-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7e04b-124">Remarks</span></span>  
 <span data-ttu-id="7e04b-125">`<clear>` Öğeyi kaldırır gelen tüm dinleyicileri `Listeners` izleme için koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="7e04b-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="7e04b-126">Kullanabileceğiniz `<clear>` kullanmadan önce öğesi `<add>` öğe koleksiyonda diğer etkin dinleyicileri olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="7e04b-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="7e04b-127">Temizleyebilir `Listeners` çağırarak programlı olarak koleksiyonu <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> yöntemi <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> özelliği (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="7e04b-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="7e04b-128">Bu öğe makine yapılandırma dosyası (Machine.config) ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7e04b-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e04b-129">`<clear>` Öğeyi kaldırır <xref:System.Diagnostics.DefaultTraceListener> gelen `Listeners` davranışını değiştiren koleksiyonu <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, ve <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="7e04b-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="7e04b-130">Çağıran bir `Assert` veya `Fail` yöntem normalde bir ileti kutusu görüntüleme içinde sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="7e04b-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="7e04b-131">Ancak, ileti kutusu varsa görüntülenmez <xref:System.Diagnostics.DefaultTraceListener> bulunmayan `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="7e04b-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e04b-132">Örnek</span><span class="sxs-lookup"><span data-stu-id="7e04b-132">Example</span></span>  
 <span data-ttu-id="7e04b-133">Aşağıdaki örnekte nasıl kullanılacağını gösterir `<clear>` kullanmadan önce öğesi `<add>` dinleyicisi eklemek için öğesi `console` için `Listeners` izleme için koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="7e04b-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="7e04b-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7e04b-134">See Also</span></span>  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="7e04b-135">İzleme ve hata ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="7e04b-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="7e04b-136">\<kaldırma ></span><span class="sxs-lookup"><span data-stu-id="7e04b-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [<span data-ttu-id="7e04b-137">İzleme dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="7e04b-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)