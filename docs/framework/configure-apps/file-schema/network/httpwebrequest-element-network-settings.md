---
title: "&lt;httpWebRequest&gt; öğesi (ağ ayarları)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0a4490870cb12ff221f75b043f01baad9b5c7c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="415a8-102">&lt;httpWebRequest&gt; öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="415a8-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="415a8-103">Web isteği parametreleri özelleştirir.</span><span class="sxs-lookup"><span data-stu-id="415a8-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="415a8-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="415a8-104">\<configuration></span></span>  
<span data-ttu-id="415a8-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="415a8-105">\<system.net></span></span>  
<span data-ttu-id="415a8-106">\<Ayarlar ></span><span class="sxs-lookup"><span data-stu-id="415a8-106">\<settings></span></span>  
<span data-ttu-id="415a8-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="415a8-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415a8-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="415a8-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="415a8-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="415a8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="415a8-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="415a8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="415a8-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="415a8-111">Attributes</span></span>  
  
|<span data-ttu-id="415a8-112">**Özniteliği**</span><span class="sxs-lookup"><span data-stu-id="415a8-112">**Attribute**</span></span>|<span data-ttu-id="415a8-113">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="415a8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="415a8-114">Bir yanıt üstbilgisi uzunluğu en fazla kilobayt cinsinden belirtir.</span><span class="sxs-lookup"><span data-stu-id="415a8-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="415a8-115">64 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="415a8-115">The default is 64.</span></span> <span data-ttu-id="415a8-116">Boyut sınırı yanıt üstbilgileri uygulanan -1 değeri gösterir.</span><span class="sxs-lookup"><span data-stu-id="415a8-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="415a8-117">Bir hata yanıtı uzunluğu en fazla kilobayt cinsinden belirtir.</span><span class="sxs-lookup"><span data-stu-id="415a8-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="415a8-118">64 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="415a8-118">The default is 64.</span></span> <span data-ttu-id="415a8-119">Boyut sınırı hata yanıtta uygulanan -1 değeri gösterir.</span><span class="sxs-lookup"><span data-stu-id="415a8-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="415a8-120">Karşıya yükleme uzunluğu en fazla bayt bir yetkisiz hata koduna karşılık belirtir.</span><span class="sxs-lookup"><span data-stu-id="415a8-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="415a8-121">Varsayılan değer -1 ' dir.</span><span class="sxs-lookup"><span data-stu-id="415a8-121">The default is -1.</span></span> <span data-ttu-id="415a8-122">Boyut sınırı karşıya yükleme sırasında uygulanan -1 değeri gösterir.</span><span class="sxs-lookup"><span data-stu-id="415a8-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="415a8-123">Güvenli olmayan üstbilgi ayrıştırma etkinleştirilip etkinleştirilmeyeceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="415a8-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="415a8-124">Varsayılan değer `false` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="415a8-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="415a8-125">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="415a8-125">Child Elements</span></span>  
 <span data-ttu-id="415a8-126">Yok.</span><span class="sxs-lookup"><span data-stu-id="415a8-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="415a8-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="415a8-127">Parent Elements</span></span>  
  
|<span data-ttu-id="415a8-128">**Öğesi**</span><span class="sxs-lookup"><span data-stu-id="415a8-128">**Element**</span></span>|<span data-ttu-id="415a8-129">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="415a8-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="415a8-130">Ayarlar</span><span class="sxs-lookup"><span data-stu-id="415a8-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="415a8-131">Temel ağ seçeneklerini yapılandırır <xref:System.Net> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="415a8-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="415a8-132">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="415a8-132">Remarks</span></span>  
 <span data-ttu-id="415a8-133">Varsayılan olarak, .NET Framework kesinlikle RFC 2616 URI ayrıştırmak için zorlar.</span><span class="sxs-lookup"><span data-stu-id="415a8-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="415a8-134">Bazı sunucu yanıtlarını neden olur, izin verilmeyen alanlarında denetim karakterleri içerebilir <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> throw yöntemi bir <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="415a8-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="415a8-135">Varsa **useUnsafeHeaderParsing** ayarlanır **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> oluşturmayacaksa bu durumda; ancak, uygulamanızın saldırıları ayrıştırma URI birkaç formlara savunmasız olacaktır.</span><span class="sxs-lookup"><span data-stu-id="415a8-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="415a8-136">Sunucu yanıtı denetim karakterleri içermeyen şekilde değiştirmek için en iyi çözüm olur.</span><span class="sxs-lookup"><span data-stu-id="415a8-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="415a8-137">Yapılandırma Dosyaları</span><span class="sxs-lookup"><span data-stu-id="415a8-137">Configuration Files</span></span>  
 <span data-ttu-id="415a8-138">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="415a8-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="415a8-139">Örnek</span><span class="sxs-lookup"><span data-stu-id="415a8-139">Example</span></span>  
 <span data-ttu-id="415a8-140">Aşağıdaki örnek, daha geniş bir belirtmek gösterilmiştir normal maksimum üstbilgi uzunluğundan.</span><span class="sxs-lookup"><span data-stu-id="415a8-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="415a8-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="415a8-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="415a8-142">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="415a8-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)