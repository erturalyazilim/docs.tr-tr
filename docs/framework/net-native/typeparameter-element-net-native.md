---
title: "&lt;TypeParameter&gt; Öğesi (.NET Yerel)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c7b2fe5cf586c0f8a58d1698cdf3870b5b5c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparametergt-element-net-native"></a><span data-ttu-id="399d7-102">&lt;TypeParameter&gt; Öğesi (.NET Yerel)</span><span class="sxs-lookup"><span data-stu-id="399d7-102">&lt;TypeParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="399d7-103">Bir yönteme geçirilen tür bağımsız değişkeni tarafından temsil edilen türü ilke uygulanır.</span><span class="sxs-lookup"><span data-stu-id="399d7-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="399d7-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="399d7-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="399d7-105">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="399d7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="399d7-106">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="399d7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="399d7-107">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="399d7-107">Attributes</span></span>  
  
|<span data-ttu-id="399d7-108">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="399d7-108">Attribute</span></span>|<span data-ttu-id="399d7-109">Öznitelik türü</span><span class="sxs-lookup"><span data-stu-id="399d7-109">Attribute type</span></span>|<span data-ttu-id="399d7-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="399d7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="399d7-111">Genel</span><span class="sxs-lookup"><span data-stu-id="399d7-111">General</span></span>|<span data-ttu-id="399d7-112">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-112">Required attribute.</span></span> <span data-ttu-id="399d7-113">Tür parametresinin adı <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="399d7-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="399d7-114">Örneğin, yöntem imzası `Type.GetInterfaceMap(Type interfaceType)`, değeri `Name` "InterfaceType" bir özniteliktir.</span><span class="sxs-lookup"><span data-stu-id="399d7-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="399d7-115">Yansıma</span><span class="sxs-lookup"><span data-stu-id="399d7-115">Reflection</span></span>|<span data-ttu-id="399d7-116">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-116">Optional attribute.</span></span> <span data-ttu-id="399d7-117">Oluşturucular örneklerinin etkinleştirmesi için çalışma zamanı erişimi kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="399d7-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="399d7-118">Yansıma</span><span class="sxs-lookup"><span data-stu-id="399d7-118">Reflection</span></span>|<span data-ttu-id="399d7-119">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-119">Optional attribute.</span></span> <span data-ttu-id="399d7-120">Program öğeleri hakkında bilgi için sorgulama kontrol eder, ancak herhangi bir çalışma zamanı erişim sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="399d7-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="399d7-121">Yansıma</span><span class="sxs-lookup"><span data-stu-id="399d7-121">Reflection</span></span>|<span data-ttu-id="399d7-122">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-122">Optional attribute.</span></span> <span data-ttu-id="399d7-123">Dinamik programlama etkinleştirmek için Oluşturucular, yöntemleri, alanları, özellikleri ve olayları dahil tüm tür üyeleri, çalışma zamanı erişimi kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="399d7-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="399d7-124">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="399d7-124">Serialization</span></span>|<span data-ttu-id="399d7-125">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-125">Optional attribute.</span></span> <span data-ttu-id="399d7-126">Oluşturucular, alanları ve seri hale getirilmiş ve kitaplıklar gibi Newtonsoft JSON seri hale getirici tarafından seri türü örnekleri etkinleştirmek için özellikleri, çalışma zamanı erişimi denetler.</span><span class="sxs-lookup"><span data-stu-id="399d7-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="399d7-127">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="399d7-127">Serialization</span></span>|<span data-ttu-id="399d7-128">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-128">Optional attribute.</span></span> <span data-ttu-id="399d7-129">Denetimleri kullanan serileştirme için ilke <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="399d7-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="399d7-130">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="399d7-130">Serialization</span></span>|<span data-ttu-id="399d7-131">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-131">Optional attribute.</span></span> <span data-ttu-id="399d7-132">Denetimleri kullanan JSON serileştirmesi için ilke <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="399d7-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="399d7-133">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="399d7-133">Serialization</span></span>|<span data-ttu-id="399d7-134">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-134">Optional attribute.</span></span> <span data-ttu-id="399d7-135">Denetimleri kullanan XML serileştirme için ilke <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="399d7-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="399d7-136">Birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="399d7-136">Interop</span></span>|<span data-ttu-id="399d7-137">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-137">Optional attribute.</span></span> <span data-ttu-id="399d7-138">Başvuru türleri Windows çalışma zamanı ve COM hazırlama denetimlerini İlkesi</span><span class="sxs-lookup"><span data-stu-id="399d7-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="399d7-139">Birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="399d7-139">Interop</span></span>|<span data-ttu-id="399d7-140">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-140">Optional attribute.</span></span> <span data-ttu-id="399d7-141">Yerel kod için işlev işaretçileri olarak temsilci türleri hazırlama için ilke denetler.</span><span class="sxs-lookup"><span data-stu-id="399d7-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="399d7-142">Birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="399d7-142">Interop</span></span>|<span data-ttu-id="399d7-143">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="399d7-143">Optional attribute.</span></span> <span data-ttu-id="399d7-144">Değer türleri yerel koda hazırlama için ilke denetler.</span><span class="sxs-lookup"><span data-stu-id="399d7-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="399d7-145">Ad özniteliği</span><span class="sxs-lookup"><span data-stu-id="399d7-145">Name attribute</span></span>  
  
|<span data-ttu-id="399d7-146">Değer</span><span class="sxs-lookup"><span data-stu-id="399d7-146">Value</span></span>|<span data-ttu-id="399d7-147">Açıklama</span><span class="sxs-lookup"><span data-stu-id="399d7-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="399d7-148">*parametre_adý*</span><span class="sxs-lookup"><span data-stu-id="399d7-148">*parameter_name*</span></span>|<span data-ttu-id="399d7-149">Tür parametresinin adı <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="399d7-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="399d7-150">Örneğin, yöntem imzası `Type.GetInterfaceMap(Type interfaceType)`, değeri `Name` "InterfaceType" bir özniteliktir.</span><span class="sxs-lookup"><span data-stu-id="399d7-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="399d7-151">Tüm diğer özniteliklerle</span><span class="sxs-lookup"><span data-stu-id="399d7-151">All other attributes</span></span>  
  
|<span data-ttu-id="399d7-152">Değer</span><span class="sxs-lookup"><span data-stu-id="399d7-152">Value</span></span>|<span data-ttu-id="399d7-153">Açıklama</span><span class="sxs-lookup"><span data-stu-id="399d7-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="399d7-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="399d7-154">*policy_setting*</span></span>|<span data-ttu-id="399d7-155">Bu ilke türü için geçerli ayar.</span><span class="sxs-lookup"><span data-stu-id="399d7-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="399d7-156">Olası değerler şunlardır: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, ve `Required All`.</span><span class="sxs-lookup"><span data-stu-id="399d7-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="399d7-157">Daha fazla bilgi için bkz: [çalışma zamanı yönerge İlkesi ayarları](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="399d7-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="399d7-158">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="399d7-158">Child Elements</span></span>  
 <span data-ttu-id="399d7-159">Yok.</span><span class="sxs-lookup"><span data-stu-id="399d7-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="399d7-160">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="399d7-160">Parent Elements</span></span>  
  
|<span data-ttu-id="399d7-161">Öğe</span><span class="sxs-lookup"><span data-stu-id="399d7-161">Element</span></span>|<span data-ttu-id="399d7-162">Açıklama</span><span class="sxs-lookup"><span data-stu-id="399d7-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="399d7-163">\<Yöntem ></span><span class="sxs-lookup"><span data-stu-id="399d7-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="399d7-164">Çalışma zamanı yansıma ilke oluşturucunun ya da yöntemi için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="399d7-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="399d7-165">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="399d7-165">Remarks</span></span>  
 <span data-ttu-id="399d7-166">`<TypeParameter>` Öğesi benzer [ \<parametresi >](../../../docs/framework/net-native/parameter-element-net-native.md) şekilde yalnızca türü parametreleri için uygulanabilir dışında öğesi <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="399d7-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="399d7-167">Hangi tür çalışma zamanında tarafından belirtilen tür bağımsız değişkeni tarafından temsil edilen için ilke uygulanır `Name` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="399d7-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="399d7-168">Örneğin, bir statik NewtonSoft JSON seri hale getirici içerir `JsonConvert.DeserializeObject(String value, Type type)` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="399d7-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="399d7-169">Aşağıdaki yansıma yönergeleri:</span><span class="sxs-lookup"><span data-stu-id="399d7-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="399d7-170">tarafından temsil edilen çalışma zamanı türü için meta verilerin belirtin `type` bağımsız değişkeni seri hale getirme için kullanılabilir hale.</span><span class="sxs-lookup"><span data-stu-id="399d7-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="399d7-171">Bu çalışma zamanı yönergeleri aşağıdaki kaynak kodu içeren bir projeye uygularsanız:</span><span class="sxs-lookup"><span data-stu-id="399d7-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="399d7-172">meta verilerini yansıma yönergeleri yapmak `StockQuote` türü çalışma zamanında NewtonSoft JSON serileştirici için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="399d7-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399d7-173">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="399d7-173">See Also</span></span>  
 [<span data-ttu-id="399d7-174">\<Yöntem > öğesi</span><span class="sxs-lookup"><span data-stu-id="399d7-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="399d7-175">Çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu</span><span class="sxs-lookup"><span data-stu-id="399d7-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="399d7-176">Çalışma zamanı yönerge İlkesi ayarları</span><span class="sxs-lookup"><span data-stu-id="399d7-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="399d7-177">Çalışma zamanı yönerge öğeleri</span><span class="sxs-lookup"><span data-stu-id="399d7-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)