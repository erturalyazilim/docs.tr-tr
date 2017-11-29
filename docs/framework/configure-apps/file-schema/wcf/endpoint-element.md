---
title: "&lt;uç noktası&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 937819fabc50d4a0a43c6a3168e6d8a77bf4ceca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltendpointgt-element"></a><span data-ttu-id="ccfc4-102">&lt;uç noktası&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="ccfc4-102">&lt;endpoint&gt; element</span></span>
<span data-ttu-id="ccfc4-103">Bağlama, sözleşme ve Hizmetleri kullanıma sunmak için kullanılan bir hizmet uç noktası adresi özelliklerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="ccfc4-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ccfc4-105">\<Hizmet ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-105">\<service></span></span>  
<span data-ttu-id="ccfc4-106">\<uç noktası ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfc4-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ccfc4-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration="String"   isSystemEndpoint="Boolean"   kind="String"   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccfc4-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ccfc4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ccfc4-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccfc4-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ccfc4-110">Attributes</span></span>  
  
|<span data-ttu-id="ccfc4-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="ccfc4-111">Attribute</span></span>|<span data-ttu-id="ccfc4-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ccfc4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccfc4-113">adres</span><span class="sxs-lookup"><span data-stu-id="ccfc4-113">address</span></span>|<span data-ttu-id="ccfc4-114">Uç nokta adresi içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="ccfc4-115">Adres mutlak veya göreli adresi olarak belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="ccfc4-116">Göreli bir adresi sağlanırsa, konak bağlama kullanılan aktarma düzeni için uygun bir taban adresi sağlaması beklenir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="ccfc4-117">Bir adresi yapılandırılmamışsa, taban adresi Bu uç nokta adresi olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="ccfc4-118">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="ccfc4-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ccfc4-119">behaviorConfiguration</span></span>|<span data-ttu-id="ccfc4-120">Uç kullanılacak davranış adını içeren dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="ccfc4-121">bağlama</span><span class="sxs-lookup"><span data-stu-id="ccfc4-121">binding</span></span>|<span data-ttu-id="ccfc4-122">Kullanılacak bağlama türünü belirten dize özniteliği gerekli.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="ccfc4-123">Tür başvuru için kayıtlı yapılandırma bölümü içermelidir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="ccfc4-124">Kayıtlı bölüm adı yerine bağlama türü adını türüdür.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="ccfc4-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ccfc4-125">bindingConfiguration</span></span>|<span data-ttu-id="ccfc4-126">Uç nokta örneği oluşturulduğunda kullanılacak bağlama bağlama adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="ccfc4-127">Bağlama adı uç noktaları kapsamında olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="ccfc4-128">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ccfc4-129">Bu öznitelik ile birlikte kullanılan `binding` yapılandırma dosyasındaki özel bağlama yapılandırma başvurmak için.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="ccfc4-130">Özel bağlama kullanmaya çalıştığınız gerekiyorsa, bu öznitelik ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="ccfc4-131">Aksi halde, bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="ccfc4-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="ccfc4-132">bindingName</span></span>|<span data-ttu-id="ccfc4-133">WSDL aracılığıyla tanımı dışa aktarma için bağlama benzersiz tam adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="ccfc4-134">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="ccfc4-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="ccfc4-135">bindingNamespace</span></span>|<span data-ttu-id="ccfc4-136">Ad alanı tanımı için bağlama tam adını belirten dize WSDL dışa aktarın.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="ccfc4-137">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="ccfc4-138">Sözleşme</span><span class="sxs-lookup"><span data-stu-id="ccfc4-138">contract</span></span>|<span data-ttu-id="ccfc4-139">Bu uç noktaya sunduğu sözleşmeyi belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="ccfc4-140">Derleme sözleşme türü uygulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="ccfc4-141">Bir hizmet uygulaması tek anlaşma türü uygularsa, bu özellik atlanabilir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="ccfc4-142">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="ccfc4-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="ccfc4-143">endpointConfiguration</span></span>|<span data-ttu-id="ccfc4-144">Tarafından belirlenen standart uç noktanın adını belirten dize `kind` standart Bu uç noktanın ek yapılandırma bilgilerini başvuran özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="ccfc4-145">Aynı adı tanımlanmalıdır `<standardEndpoints>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="ccfc4-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="ccfc4-146">isSystemEndpoint</span></span>|<span data-ttu-id="ccfc4-147">Bir uç nokta bir altyapı uç noktası olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="ccfc4-148">türü</span><span class="sxs-lookup"><span data-stu-id="ccfc4-148">kind</span></span>|<span data-ttu-id="ccfc4-149">Standart uç nokta uygulanan türünü belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="ccfc4-150">Türü kaydedilmelidir `<extensions>` bölüm veya machine.config dosyasındaki. Hiçbir şey belirtilirse, ortak bir hizmet uç noktası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="ccfc4-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="ccfc4-151">listenUriMode</span></span>|<span data-ttu-id="ccfc4-152">Taşıma nasıl işler belirtir `ListenUri` hizmetinin üzerinde dinleme sağlanan.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="ccfc4-153">Geçerli değerler:</span><span class="sxs-lookup"><span data-stu-id="ccfc4-153">Valid values are</span></span><br /><br /> <span data-ttu-id="ccfc4-154">-Açık</span><span class="sxs-lookup"><span data-stu-id="ccfc4-154">-   Explicit</span></span><br /><span data-ttu-id="ccfc4-155">-Benzersiz</span><span class="sxs-lookup"><span data-stu-id="ccfc4-155">-   Unique</span></span><br /><br /> <span data-ttu-id="ccfc4-156">Explicit varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="ccfc4-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="ccfc4-157">listenUri</span></span>|<span data-ttu-id="ccfc4-158">Hizmet uç noktası dinleyen URI belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="ccfc4-159">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="ccfc4-160">name</span><span class="sxs-lookup"><span data-stu-id="ccfc4-160">name</span></span>|<span data-ttu-id="ccfc4-161">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-161">Optional attribute.</span></span> <span data-ttu-id="ccfc4-162">Hizmet uç noktası adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="ccfc4-163">Bağlama ve sözleşme açıklama adı birleşimini varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="ccfc4-164">Hizmetleri olabilir birden çok uç nokta, bu nedenle uç noktanın `name` özniteliktir hizmet adından farklı.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccfc4-165">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ccfc4-165">Child Elements</span></span>  
  
|<span data-ttu-id="ccfc4-166">Öğe</span><span class="sxs-lookup"><span data-stu-id="ccfc4-166">Element</span></span>|<span data-ttu-id="ccfc4-167">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ccfc4-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccfc4-168">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="ccfc4-169">Adres üstbilgileri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ccfc4-170">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ccfc4-171">Bir uç nokta onunla ileti değiş tokuşu diğer uç noktaları tarafından kimlik doğrulamasına olanak tanıyan bir kimlik.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccfc4-172">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ccfc4-172">Parent Elements</span></span>  
  
|<span data-ttu-id="ccfc4-173">Öğe</span><span class="sxs-lookup"><span data-stu-id="ccfc4-173">Element</span></span>|<span data-ttu-id="ccfc4-174">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ccfc4-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccfc4-175">\<Hizmet ></span><span class="sxs-lookup"><span data-stu-id="ccfc4-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="ccfc4-176">Bir istemcinin bağlanabileceği bitiş noktaları listesini tanımlar yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ccfc4-177">Örnek</span><span class="sxs-lookup"><span data-stu-id="ccfc4-177">Example</span></span>  
 <span data-ttu-id="ccfc4-178">Bu, bir hizmet uç noktası yapılandırması örneğidir.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccfc4-179">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ccfc4-179">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [<span data-ttu-id="ccfc4-180">Uç noktalar: Adresler, bağlamalar ve sözleşmeler</span><span class="sxs-lookup"><span data-stu-id="ccfc4-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="ccfc4-181">Nasıl yapılır: yapılandırmada hizmet uç noktası oluşturma</span><span class="sxs-lookup"><span data-stu-id="ccfc4-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)