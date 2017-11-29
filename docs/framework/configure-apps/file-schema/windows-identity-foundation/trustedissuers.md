---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="36d2e-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="36d2e-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="36d2e-103">Güvenilen yayıncı sertifikaları yapılandırma temelli verenin adı kayıt defteri tarafından kullanılan listesini yapılandırır (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="36d2e-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="36d2e-104">\<System.IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="36d2e-104">\<system.identityModel></span></span>  
<span data-ttu-id="36d2e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="36d2e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="36d2e-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="36d2e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="36d2e-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="36d2e-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="36d2e-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="36d2e-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="36d2e-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="36d2e-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d2e-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="36d2e-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d2e-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="36d2e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="36d2e-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="36d2e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d2e-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="36d2e-113">Attributes</span></span>  
 <span data-ttu-id="36d2e-114">Yok.</span><span class="sxs-lookup"><span data-stu-id="36d2e-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36d2e-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="36d2e-115">Child Elements</span></span>  
  
|<span data-ttu-id="36d2e-116">Öğe</span><span class="sxs-lookup"><span data-stu-id="36d2e-116">Element</span></span>|<span data-ttu-id="36d2e-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="36d2e-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="36d2e-118">Bir sertifika, güvenilen verenler koleksiyonuna ekler.</span><span class="sxs-lookup"><span data-stu-id="36d2e-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="36d2e-119">Sertifika ile belirtilen `thumbprint` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="36d2e-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="36d2e-120">Bu özniteliği gereklidir ve sertifika parmak izi ASN.1 kodlanmış form içermelidir.</span><span class="sxs-lookup"><span data-stu-id="36d2e-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="36d2e-121">`name` Özniteliği isteğe bağlıdır ve sertifika için kolay bir ad belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="36d2e-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="36d2e-122">Tüm sertifikaları Güvenilen verenler koleksiyonundan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="36d2e-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="36d2e-123">Bir sertifika, güvenilen verenler koleksiyondan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="36d2e-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="36d2e-124">Sertifika ile belirtilen `thumbprint` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="36d2e-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="36d2e-125">Bu öznitelik gereklidir.</span><span class="sxs-lookup"><span data-stu-id="36d2e-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36d2e-126">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="36d2e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="36d2e-127">Öğe</span><span class="sxs-lookup"><span data-stu-id="36d2e-127">Element</span></span>|<span data-ttu-id="36d2e-128">Açıklama</span><span class="sxs-lookup"><span data-stu-id="36d2e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d2e-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="36d2e-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="36d2e-130">Yayınlayıcı adı kaydını yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="36d2e-130">Configures the issuer name registry.</span></span> <span data-ttu-id="36d2e-131">**Önemli:** `type` özniteliği `<issuerNameRegistry>` öğesi başvurmalıdır <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> için sınıf `<trustedIssuers>` geçerli olması için öğesi.</span><span class="sxs-lookup"><span data-stu-id="36d2e-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d2e-132">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="36d2e-132">Remarks</span></span>  
 <span data-ttu-id="36d2e-133">Windows Identity Foundation (WIF) sağlar, tek bir uygulama <xref:System.IdentityModel.Tokens.IssuerNameRegistry> kutusunu dışında sınıfı <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="36d2e-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="36d2e-134">Yapılandırma yayınlayıcı adı kaydını yapılandırmasından yüklenen güvenilen verenlerin bir listesini tutar.</span><span class="sxs-lookup"><span data-stu-id="36d2e-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="36d2e-135">Listenin her verenin adı veren tarafından üretilen belirteçleri imzasını doğrulamak için gereken X.509 sertifikası ile ilişkilendirir.</span><span class="sxs-lookup"><span data-stu-id="36d2e-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="36d2e-136">Güvenilen yayıncı sertifikaları listesi altında belirtilen `<trustedIssuers>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="36d2e-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="36d2e-137">Her bir öğe listesi anımsatıcı verenin adı, veren tarafından üretilen belirteçleri imzasını doğrulamak için gereken X.509 sertifikası ile ilişkilendirir.</span><span class="sxs-lookup"><span data-stu-id="36d2e-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="36d2e-138">Güvenilir sertifikalar ASN.1 kullanılarak kodlanmış form sertifika parmak izi belirtilir ve koleksiyon kullanılarak eklenen `<add>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="36d2e-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="36d2e-139">İşaretini kaldırın veya verenler (sertifika) kullanarak listeden kaldırmak `<clear>` ve `<remove>` öğeleri.</span><span class="sxs-lookup"><span data-stu-id="36d2e-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="36d2e-140">`type` Özniteliği `<issuerNameRegistry>` öğesi başvurmalıdır <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> için sınıf `<trustedIssuers>` geçerli olması için öğesi.</span><span class="sxs-lookup"><span data-stu-id="36d2e-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36d2e-141">Örnek</span><span class="sxs-lookup"><span data-stu-id="36d2e-141">Example</span></span>  
 <span data-ttu-id="36d2e-142">Aşağıdaki XML tabanlı yapılandırma veren belirtmek adı kayıt defteri gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="36d2e-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36d2e-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="36d2e-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>