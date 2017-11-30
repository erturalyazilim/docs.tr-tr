---
title: "&lt;useLegacyJit&gt; öğesi"
ms.custom: 
ms.date: 04/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 735733fc33a21c2f275c1ea9894c43558f01626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="479dd-102">&lt;useLegacyJit&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="479dd-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="479dd-103">Ortak dil çalışma zamanı için tam zamanında derleme eski 64-bit JIT Derleyici kullanıp kullanmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="479dd-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="479dd-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="479dd-104">\<configuration></span></span>  
<span data-ttu-id="479dd-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="479dd-105">\<runtime></span></span>  
<span data-ttu-id="479dd-106">\<useLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="479dd-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="479dd-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="479dd-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="479dd-108">Öğe adı `useLegacyJit` küçük harfe duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="479dd-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="479dd-109">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="479dd-109">Attributes and elements</span></span>

<span data-ttu-id="479dd-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="479dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="479dd-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="479dd-111">Attributes</span></span>  
  
| <span data-ttu-id="479dd-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="479dd-112">Attribute</span></span> | <span data-ttu-id="479dd-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="479dd-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="479dd-114">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="479dd-114">Required attribute.</span></span><br><br><span data-ttu-id="479dd-115">Çalışma zamanı eski 64-bit JIT Derleyici kullanıp kullanmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="479dd-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="479dd-116">Etkin özniteliği</span><span class="sxs-lookup"><span data-stu-id="479dd-116">enabled attribute</span></span>  
  
| <span data-ttu-id="479dd-117">Değer</span><span class="sxs-lookup"><span data-stu-id="479dd-117">Value</span></span> | <span data-ttu-id="479dd-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="479dd-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="479dd-119">0</span><span class="sxs-lookup"><span data-stu-id="479dd-119">0</span></span>     | <span data-ttu-id="479dd-120">Ortak dil çalışma zamanı .NET Framework 4.6 ve sonraki sürümlerinde bulunan yeni 64-bit JIT Derleyici kullanır.</span><span class="sxs-lookup"><span data-stu-id="479dd-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="479dd-121">1.</span><span class="sxs-lookup"><span data-stu-id="479dd-121">1</span></span>     | <span data-ttu-id="479dd-122">Ortak dil çalışma zamanı eski 64-bit JIT Derleyici kullanır.</span><span class="sxs-lookup"><span data-stu-id="479dd-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="479dd-123">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="479dd-123">Child elements</span></span>

<span data-ttu-id="479dd-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="479dd-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="479dd-125">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="479dd-125">Parent elements</span></span>  
  
| <span data-ttu-id="479dd-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="479dd-126">Element</span></span>         | <span data-ttu-id="479dd-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="479dd-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="479dd-128">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="479dd-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="479dd-129">Çalışma zamanı başlatma seçenekleri hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="479dd-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="479dd-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="479dd-130">Remarks</span></span>  

<span data-ttu-id="479dd-131">.NET Framework 4.6 ile başlayarak, ortak dil çalışma zamanı yeni bir 64 bit derleyici Just-In-Time (JIT) derleme için varsayılan olarak kullanır.</span><span class="sxs-lookup"><span data-stu-id="479dd-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="479dd-132">Bazı durumlarda, bu davranışı fark JIT derlenmiş önceki sürümü 64-bit JIT Derleyici tarafından uygulama kodu neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="479dd-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="479dd-133">Ayarlayarak `enabled` özniteliği `<useLegacyJit>` öğesine `1`, yeni 64-bit JIT Derleyici devre dışı bırakabilir ve bunun yerine eski 64-bit JIT Derleyici kullanarak uygulamanızı derleyin.</span><span class="sxs-lookup"><span data-stu-id="479dd-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="479dd-134">`<useLegacyJit>` Öğesi yalnızca 64-bit JIT derleme etkiler.</span><span class="sxs-lookup"><span data-stu-id="479dd-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="479dd-135">32-bit JIT derleyicisi ile derleme etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="479dd-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="479dd-136">Bir yapılandırma dosyası ayarı kullanmak yerine, diğer iki yolla eski 64-bit JIT Derleyici etkinleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="479dd-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="479dd-137">Bir ortam değişkeni ayarlama</span><span class="sxs-lookup"><span data-stu-id="479dd-137">Setting an environment variable</span></span>

  <span data-ttu-id="479dd-138">Ayarlama `COMPLUS_useLegacyJit` ya da ortam değişkeni `0` (yeni 64-bit JIT Derleyici kullanın) veya `1` (eski 64-bit JIT Derleyici kullanın):</span><span class="sxs-lookup"><span data-stu-id="479dd-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="479dd-139">Ortam değişkeni sahip *genel kapsam*, etkilediği anlamına tüm uygulamaları makinede çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="479dd-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="479dd-140">Ayarlama, bu uygulama yapılandırma dosyası ayarı tarafından geçersiz kılınabilir durumunda.</span><span class="sxs-lookup"><span data-stu-id="479dd-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="479dd-141">Ortam değişkeni adı büyük küçük harfe duyarlı değil.</span><span class="sxs-lookup"><span data-stu-id="479dd-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="479dd-142">Bir kayıt defteri anahtarı ekleme</span><span class="sxs-lookup"><span data-stu-id="479dd-142">Adding a registry key</span></span>

  <span data-ttu-id="479dd-143">Eski 64-bit JIT Derleyici ekleyerek etkinleştirebilirsiniz bir `REG_DWORD` değeri ya da `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` veya `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` kayıt defterinde anahtar.</span><span class="sxs-lookup"><span data-stu-id="479dd-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="479dd-144">Adlı değer `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="479dd-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="479dd-145">Değer 0 ise, yeni derleyici kullanılır.</span><span class="sxs-lookup"><span data-stu-id="479dd-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="479dd-146">Değer 1 ise, eski 64-bit JIT Derleyici etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="479dd-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="479dd-147">Kayıt defteri değerinin adını büyük küçük harfe duyarlı değil.</span><span class="sxs-lookup"><span data-stu-id="479dd-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="479dd-148">Değer ekleme `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` anahtar makine üzerinde çalışan tüm uygulamaları etkiler.</span><span class="sxs-lookup"><span data-stu-id="479dd-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="479dd-149">Değer ekleme `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` anahtar geçerli kullanıcı tarafından çalıştırılan tüm uygulamaları etkiler.</span><span class="sxs-lookup"><span data-stu-id="479dd-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="479dd-150">Bir makine birden çok kullanıcı hesabı ile yapılandırılmışsa, değer de diğer kullanıcılar için kayıt defteri anahtarları için eklenene kadar yalnızca geçerli kullanıcı tarafından çalıştırılan uygulamalar etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="479dd-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="479dd-151">Ekleme `<useLegacyJit>` öğesi bir yapılandırma dosyasına mevcut değilse kayıt defteri ayarları geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="479dd-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="479dd-152">Örnek</span><span class="sxs-lookup"><span data-stu-id="479dd-152">Example</span></span>  

<span data-ttu-id="479dd-153">Aşağıdaki yapılandırma dosyası derleme yeni 64-bit JIT derleyicisi ile devre dışı bırakır ve bunun yerine eski 64-bit JIT Derleyici kullanır.</span><span class="sxs-lookup"><span data-stu-id="479dd-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="479dd-154">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="479dd-154">See also</span></span>

<span data-ttu-id="479dd-155">[\<çalışma zamanı > öğesi](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="479dd-155">[\<runtime> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span></span>  
<span data-ttu-id="479dd-156">[\<Yapılandırma > öğesi](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="479dd-156">[\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
[<span data-ttu-id="479dd-157">Azaltma: Yeni 64-bit JIT derleme</span><span class="sxs-lookup"><span data-stu-id="479dd-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)