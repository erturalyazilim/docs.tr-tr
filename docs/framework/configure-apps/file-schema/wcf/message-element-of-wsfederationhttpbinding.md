---
title: "&lt;wsFederationHttpBinding&gt; &lt;iletisi&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b17a6325b84382d9d22b4da3ccf7e1598dc42df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="6c003-102">&lt;wsFederationHttpBinding&gt; &lt;iletisi&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="6c003-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="6c003-103">İleti düzeyi güvenlik ayarlarını tanımlar [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6c003-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="6c003-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6c003-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6c003-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="6c003-105">\<bindings></span></span>  
<span data-ttu-id="6c003-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="6c003-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="6c003-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="6c003-107">\<binding></span></span>  
<span data-ttu-id="6c003-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="6c003-108">\<security></span></span>  
<span data-ttu-id="6c003-109">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="6c003-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c003-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6c003-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c003-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c003-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6c003-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6c003-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c003-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="6c003-113">Attributes</span></span>  
  
|<span data-ttu-id="6c003-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="6c003-114">Attribute</span></span>|<span data-ttu-id="6c003-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c003-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c003-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="6c003-116">algorithmSuite</span></span>|<span data-ttu-id="6c003-117">İleti şifreleme ve anahtar-wrap algoritmaları ayarlar.</span><span class="sxs-lookup"><span data-stu-id="6c003-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="6c003-118">Bu özniteliğin geçerli değerler "algorithmSuite özniteliği" tablosuna bakın.</span><span class="sxs-lookup"><span data-stu-id="6c003-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="6c003-119">Varsayılan değer `Basic256` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="6c003-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="6c003-120">Bu öznitelik türünde <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="6c003-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="6c003-121">Bu algoritmalar, güvenlik ilkesi dili (WS-SecurityPolicy) belirtiminde belirtilen eşlenir.</span><span class="sxs-lookup"><span data-stu-id="6c003-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="6c003-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="6c003-122">issuedKeyType</span></span>|<span data-ttu-id="6c003-123">Kesilecek anahtar türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c003-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="6c003-124">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c003-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c003-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="6c003-125">-   SymmetricKey</span></span><br /><span data-ttu-id="6c003-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="6c003-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="6c003-127">Varsayılan, `SymmetricKey` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c003-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="6c003-128">Bu öznitelik türünde <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="6c003-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="6c003-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="6c003-129">issuedTokenType</span></span>|<span data-ttu-id="6c003-130">Verilmesine Belirtecin türü belirten bir URI'yı içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="6c003-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="6c003-131">Varsayılan, `null` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c003-131">The default is `null`.</span></span>|  
|<span data-ttu-id="6c003-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="6c003-132">negotiateServiceCredential</span></span>|<span data-ttu-id="6c003-133">Hizmet kimlik bilgilerini anlaşmasının bir parçası değiştirilen veya bant dışı kullanılabilir olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c003-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="6c003-134">Varsayılan değer `true`, hizmet kimlik bilgilerini anlaşılmadan anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="6c003-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="6c003-135">algorithmSuite özniteliği</span><span class="sxs-lookup"><span data-stu-id="6c003-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="6c003-136">Değer</span><span class="sxs-lookup"><span data-stu-id="6c003-136">Value</span></span>|<span data-ttu-id="6c003-137">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c003-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c003-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="6c003-138">Basic128</span></span>|<span data-ttu-id="6c003-139">İleti özeti için Sha1 ve Rsa oaep mgf1p Basic128 şifreleme anahtarı kaydırma için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="6c003-140">Basic192</span></span>|<span data-ttu-id="6c003-141">Basic192 şifreleme, Sha1 oaep Rsa mgf1p anahtar kaydırma için ileti özeti için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="6c003-142">Basic256</span></span>|<span data-ttu-id="6c003-143">Basic256 şifreleme, Sha1 oaep Rsa mgf1p anahtar kaydırma için ileti özeti için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-144">Basic256Rsa15</span></span>|<span data-ttu-id="6c003-145">İleti şifreleme, ileti özeti için Sha1 ve anahtar sarma Rsa15 için Basic256 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-146">Basic192Rsa15</span></span>|<span data-ttu-id="6c003-147">İleti şifreleme, ileti özeti için Sha1 ve anahtar sarma Rsa15 için Basic192 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="6c003-148">TripleDes</span></span>|<span data-ttu-id="6c003-149">TripleDes şifreleme, Sha1 oaep Rsa mgf1p anahtar kaydırma için ileti özeti için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-150">Basic128Rsa15</span></span>|<span data-ttu-id="6c003-151">İleti şifreleme, ileti özeti için Sha1 ve anahtar sarma Rsa15 için Basic128 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-152">TripleDesRsa15</span></span>|<span data-ttu-id="6c003-153">TripleDes şifreleme, ileti özeti için Sha1 ve Rsa15 anahtar kaydırma için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="6c003-154">Basic128Sha256</span></span>|<span data-ttu-id="6c003-155">İleti şifreleme, ileti özeti için Sha256 ve anahtar kaydırma için Rsa-oaep mgf1p için Basic128 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="6c003-156">Basic192Sha256</span></span>|<span data-ttu-id="6c003-157">İleti şifreleme, ileti özeti için Sha256 ve anahtar kaydırma için Rsa-oaep mgf1p için Basic192 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="6c003-158">Basic256Sha256</span></span>|<span data-ttu-id="6c003-159">İleti şifreleme, ileti özeti için Sha256 ve anahtar kaydırma için Rsa-oaep mgf1p için Basic256 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="6c003-160">TripleDesSha256</span></span>|<span data-ttu-id="6c003-161">TripleDes ileti şifreleme, ileti özeti için Sha256 ve oaep Rsa mgf1p anahtar kaydırma için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6c003-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="6c003-163">İleti şifreleme, ileti özeti için Sha256 ve anahtar sarma Rsa15 için Basic128 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="6c003-165">İleti şifreleme, ileti özeti için Sha256 ve anahtar sarma Rsa15 için Aes192 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="6c003-167">İleti şifreleme, ileti özeti için Sha256 ve anahtar sarma Rsa15 için Basic256 kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6c003-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6c003-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="6c003-169">TripleDes ileti şifreleme, ileti özeti için Sha256 ve Rsa15 anahtar kaydırma için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c003-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c003-170">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c003-170">Child Elements</span></span>  
  
|<span data-ttu-id="6c003-171">Öğe</span><span class="sxs-lookup"><span data-stu-id="6c003-171">Element</span></span>|<span data-ttu-id="6c003-172">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c003-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c003-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="6c003-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="6c003-174">Bu bağlama için talep türleri koleksiyonunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c003-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="6c003-175">Her öğe türünde <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="6c003-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="6c003-176">yayınlayan</span><span class="sxs-lookup"><span data-stu-id="6c003-176">issuer</span></span>|<span data-ttu-id="6c003-177">Bir güvenlik belirteci verir bir uç nokta belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c003-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="6c003-178">Bu öğe türünde <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="6c003-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="6c003-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="6c003-179">issuerMetadata</span></span>|<span data-ttu-id="6c003-180">Uç nokta adresi verenin belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c003-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="6c003-181">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="6c003-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="6c003-182">Belirteç isteği parametreleri topluluğu.</span><span class="sxs-lookup"><span data-stu-id="6c003-182">A collection of token request parameters.</span></span> <span data-ttu-id="6c003-183">Her bir XML öğesi parametresidir.</span><span class="sxs-lookup"><span data-stu-id="6c003-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c003-184">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c003-184">Parent Elements</span></span>  
  
|<span data-ttu-id="6c003-185">Öğe</span><span class="sxs-lookup"><span data-stu-id="6c003-185">Element</span></span>|<span data-ttu-id="6c003-186">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c003-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c003-187">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="6c003-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="6c003-188">Bağlama için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="6c003-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c003-189">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6c003-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="6c003-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[Hizmetler ve istemcileri güvenli hale getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="6c003-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="6c003-191">Bağlamaları</span><span class="sxs-lookup"><span data-stu-id="6c003-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6c003-192">Sistem tarafından sağlanan bağlamaları yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6c003-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="6c003-193">Windows Communication Foundation Hizmetleri ve istemcileri yapılandırmak için bağlamaları kullanma</span><span class="sxs-lookup"><span data-stu-id="6c003-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="6c003-194">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="6c003-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)