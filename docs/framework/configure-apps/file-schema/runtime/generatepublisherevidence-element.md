---
title: "&lt;generatePublisherEvidence&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 78293c396687f9c0c99ffdfbe94cf1f3c548289d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="879c4-102">&lt;generatePublisherEvidence&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="879c4-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="879c4-103">Çalışma zamanı oluşturup oluşturmayacağını belirtir <xref:System.Security.Policy.Publisher> kod erişim güvenliği (CAS) için kanıt.</span><span class="sxs-lookup"><span data-stu-id="879c4-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="879c4-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="879c4-104">\<configuration></span></span>  
<span data-ttu-id="879c4-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="879c4-105">\<runtime></span></span>  
<span data-ttu-id="879c4-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="879c4-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="879c4-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="879c4-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="879c4-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="879c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="879c4-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="879c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="879c4-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="879c4-110">Attributes</span></span>  
  
|<span data-ttu-id="879c4-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="879c4-111">Attribute</span></span>|<span data-ttu-id="879c4-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="879c4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="879c4-113">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="879c4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="879c4-114">Çalışma zamanı oluşturup oluşturmayacağını belirtir <xref:System.Security.Policy.Publisher> kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="879c4-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="879c4-115">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="879c4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="879c4-116">Değer</span><span class="sxs-lookup"><span data-stu-id="879c4-116">Value</span></span>|<span data-ttu-id="879c4-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="879c4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="879c4-118">Oluşturmaz <xref:System.Security.Policy.Publisher> kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="879c4-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="879c4-119">Oluşturur <xref:System.Security.Policy.Publisher> kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="879c4-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="879c4-120">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="879c4-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="879c4-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="879c4-121">Child Elements</span></span>  
 <span data-ttu-id="879c4-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="879c4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="879c4-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="879c4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="879c4-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="879c4-124">Element</span></span>|<span data-ttu-id="879c4-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="879c4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="879c4-126">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="879c4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="879c4-127">Çalışma zamanı başlatma seçenekleri hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="879c4-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="879c4-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="879c4-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="879c4-129">İçinde [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] ve daha sonra bu öğe derleme yükleme süreleri üzerinde hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="879c4-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="879c4-130">Daha fazla bilgi için "Güvenlik ilkesi basitleştirme" bölümüne bakın [güvenlik değişiklikleri](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="879c4-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="879c4-131">Ortak dil çalışma zamanı (CLR) oluşturmak için yükleme zamanında Authenticode imzasını doğrulama girişiminde <xref:System.Security.Policy.Publisher> derleme için kanıt.</span><span class="sxs-lookup"><span data-stu-id="879c4-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="879c4-132">Ancak, varsayılan olarak, çoğu uygulamayı gerekmeyen <xref:System.Security.Policy.Publisher> kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="879c4-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="879c4-133">Standart CAS ilkesini değil Bel <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="879c4-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="879c4-134">Uygulamanızı özel CA ilkesi olan bir bilgisayarda yürütür veya için taleplerini karşılamak üzere planladığı sürece yayımcı imzasını doğrulama ile ilişkili gereksiz başlangıç maliyeti kaçınmalısınız <xref:System.Security.Permissions.PublisherIdentityPermission> kısmi güven ortamında.</span><span class="sxs-lookup"><span data-stu-id="879c4-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="879c4-135">(Her zaman talepleri kimlik izinleri için tam güven ortamında başarılı.)</span><span class="sxs-lookup"><span data-stu-id="879c4-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="879c4-136">Kullanım Hizmetleri öneririz `<generatePublisherEvidence>` başlangıç performansını artırmak için öğesi.</span><span class="sxs-lookup"><span data-stu-id="879c4-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="879c4-137">Bu öğe kullanarak da bir zaman aşımı ve hizmetin başlatılması iptaline neden olabileceği gecikmeler önlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="879c4-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="879c4-138">Yapılandırma Dosyası</span><span class="sxs-lookup"><span data-stu-id="879c4-138">Configuration File</span></span>  
 <span data-ttu-id="879c4-139">Bu öğe yalnızca uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="879c4-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="879c4-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="879c4-140">Example</span></span>  
 <span data-ttu-id="879c4-141">Aşağıdaki örnekte nasıl kullanılacağını gösterir `<generatePublisherEvidence>` CA'lar Yayımcı ilkesi için bir uygulama denetimi devre dışı bırakmak için öğesi.</span><span class="sxs-lookup"><span data-stu-id="879c4-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="879c4-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="879c4-142">See Also</span></span>  
 [<span data-ttu-id="879c4-143">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="879c4-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="879c4-144">Yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="879c4-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)