---
title: '&#39; teki Windows Identity Foundation 4.5''deki yenilikler'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b381f04-593b-471f-bd33-0362be1aade5
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 19116aba3049dce6612ca1a7170030f7ced6705e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="what39s-new-in-windows-identity-foundation-45"></a><span data-ttu-id="2b83e-102">&#39; teki Windows Identity Foundation 4.5'deki yenilikler</span><span class="sxs-lookup"><span data-stu-id="2b83e-102">What&#39;s New in Windows Identity Foundation 4.5</span></span>
<span data-ttu-id="2b83e-103">Windows Identity Foundation'ın (WIF) ilk sürümü tek başına bir indirme olarak gönderildi ve .NET 3.5 SP1 zaman çerçevesinde kullanıma sunulduğundan WIF 3.5 olarak bilinmekteydi.</span><span class="sxs-lookup"><span data-stu-id="2b83e-103">The first version of Windows Identity Foundation (WIF) shipped as a standalone download and is known as WIF 3.5 because it was introduced in the .NET 3.5 SP1 timeframe.</span></span> <span data-ttu-id="2b83e-104">.NET 4.5 sürümünden itibaren WIF, .NET çerçevesinin bir parçası olmuştur.</span><span class="sxs-lookup"><span data-stu-id="2b83e-104">Starting with .NET 4.5, WIF is part of the .NET framework.</span></span> <span data-ttu-id="2b83e-105">Framework'te doğrudan kullanılabilen WIF sınıfları sahip talep tabanlı kimlik talepleri kullanan kolaylaştırma .NET içinde çok derin tümleştirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="2b83e-105">Having the WIF classes directly available in the framework allows for a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="2b83e-106">WIF 3.5 için yazılmış uygulamalar için yeni model yararlanmak için değiştirilmesi gerekir; bilgi için bkz: [bir uygulama yerleşik kullanarak WIF 3.5 WIF 4.5 sürümüne geçirmek için yönergeler](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-106">Applications written for WIF 3.5 will need to be modified in order to take advantage of the new model; for information, see [Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).</span></span>  
  
 <span data-ttu-id="2b83e-107">Aşağıda, bazı önemli ana değişiklikleri bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2b83e-107">Below you can find some highlights of the main changes.</span></span>  
  
## <a name="wif-is-now-part-of-the-net-framework"></a><span data-ttu-id="2b83e-108">WIF Artık .NET Framework'ün Bir Parçasıdır</span><span class="sxs-lookup"><span data-stu-id="2b83e-108">WIF Is Now Part of the .NET Framework</span></span>  
 <span data-ttu-id="2b83e-109">WIF sınıf artık birkaç derlemeler arasında ana olanları yayılan olan `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services`, ve `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="2b83e-109">WIF classes are now spread across several assemblies, the main ones being `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services`, and `System.ServiceModel`.</span></span> <span data-ttu-id="2b83e-110">Benzer şekilde, WIF sınıfları birkaç ad alanları arasında yayılır: <xref:System.Security.Claims?displayProperty=nameWithType>, birkaç [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) ad alanları, ve <xref:System.ServiceModel.Security?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b83e-110">Likewise, the WIF classes are spread across several namespaces: <xref:System.Security.Claims?displayProperty=nameWithType>, several [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) namespaces, and <xref:System.ServiceModel.Security?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2b83e-111"><xref:System.Security.Claims?displayProperty=nameWithType> Ad alanı içeren yeni <xref:System.Security.Claims.ClaimsPrincipal> ve <xref:System.Security.Claims.ClaimsIdentity> sınıfları (aşağıya bakın).</span><span class="sxs-lookup"><span data-stu-id="2b83e-111">The <xref:System.Security.Claims?displayProperty=nameWithType> namespace contains the new <xref:System.Security.Claims.ClaimsPrincipal> and <xref:System.Security.Claims.ClaimsIdentity> classes (see below).</span></span> <span data-ttu-id="2b83e-112">.NET içinde tüm Sorumlular şimdi öğesinden türetilen <xref:System.Security.Claims.ClaimsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="2b83e-112">All principals in .NET now derive from <xref:System.Security.Claims.ClaimsPrincipal>.</span></span> <span data-ttu-id="2b83e-113">WIF ad alanları ve içerdikleri sınıfları türleri hakkında daha ayrıntılı bilgi için bkz: [WIF API Başvurusu](../../../docs/framework/security/wif-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-113">For more detailed information about the WIF namespaces and the kinds of classes that they contain, see [WIF API Reference](../../../docs/framework/security/wif-api-reference.md).</span></span> <span data-ttu-id="2b83e-114">Ad alanları WIF 3.5 ve WIF 4.5 arasında nasıl eşleme hakkında daha fazla bilgi için bkz: [Namespace eşleme WIF 3.5 ve WIF 4.5 arasında](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-114">For information about how namespaces map between WIF 3.5 and WIF 4.5, see [Namespace Mapping between WIF 3.5 and WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).</span></span>  
  
## <a name="new-claims-model-and-principal-object"></a><span data-ttu-id="2b83e-115">Yeni Beyan Modeli ve Asıl Nesne</span><span class="sxs-lookup"><span data-stu-id="2b83e-115">New Claims Model and Principal Object</span></span>  
 <span data-ttu-id="2b83e-116">Beyanlar .NET Framework 4.5'in özündedir.</span><span class="sxs-lookup"><span data-stu-id="2b83e-116">Claims are at the very core of the .NET Framework 4.5.</span></span> <span data-ttu-id="2b83e-117">Temel sınıflar talep (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes>, ve <xref:System.Security.Claims.ClaimValueTypes>) tüm Canlı doğrudan `mscorlib` içinde <xref:System.Security.Claims?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="2b83e-117">The base claim classes (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes>, and <xref:System.Security.Claims.ClaimValueTypes>) all live directly in `mscorlib` in the <xref:System.Security.Claims?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2b83e-118">Artık .NET kimlik sisteme talep bağlama için arabirimleri kullanmak gerekli değildir: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal>, ve <xref:System.Web.Security.RolePrincipal> şimdi devralınmalıdır <xref:System.Security.Claims.ClaimsPrincipal>; ve <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity>, ve <xref:System.Web.Security.FormsIdentity> şimdi devral gelen <xref:System.Security.Claims.ClaimsIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2b83e-118">It is no longer necessary to use interfaces in order to plug claims into the .NET identity system: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal>, and <xref:System.Web.Security.RolePrincipal> now inherit from <xref:System.Security.Claims.ClaimsPrincipal>; and <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity>, and <xref:System.Web.Security.FormsIdentity> now inherit from <xref:System.Security.Claims.ClaimsIdentity>.</span></span> <span data-ttu-id="2b83e-119">Kısacası, her asıl sınıf bundan böyle beyanlar sunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="2b83e-119">In short, every principal class will now serve claims.</span></span> <span data-ttu-id="2b83e-120">WIF 3.5 tümleştirme sınıflar ve arabirimler (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) böylece kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="2b83e-120">The WIF 3.5 integration classes and interfaces (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) have thus been removed.</span></span> <span data-ttu-id="2b83e-121">Ayrıca, <xref:System.Security.Claims.ClaimsIdentity> kolaylaştırmak çıkarır yöntemleri kimliğin sorgu artık sınıfı talep koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="2b83e-121">In addition, the <xref:System.Security.Claims.ClaimsIdentity> class now exposes methods which make it easier to query the identity’s claims collection.</span></span>  
  
## <a name="changes-to-the-wif-45-visual-studio-experience"></a><span data-ttu-id="2b83e-122">WIF 4.5 Visual Studio Deneyimine Yönelik Değişiklikler</span><span class="sxs-lookup"><span data-stu-id="2b83e-122">Changes to the WIF 4.5 Visual Studio Experience</span></span>  
  
-   <span data-ttu-id="2b83e-123">**STS Başvurusu Ekle...**</span><span class="sxs-lookup"><span data-stu-id="2b83e-123">The **Add STS Reference …**</span></span> <span data-ttu-id="2b83e-124">Visual Studio işlevselliği (komut satırı yardımcı programı FedUtil) artık yoktur; Bunun yerine, yeni Visual Studio uzantısı kullanabileceğiniz **kimlik ve erişim aracı Visual Studio 2012 için**.</span><span class="sxs-lookup"><span data-stu-id="2b83e-124">Visual Studio functionality (cmdline utility FedUtil) no longer exists; instead you can use the new Visual Studio extension **Identity and Access Tool for Visual Studio 2012**.</span></span> <span data-ttu-id="2b83e-125">Bu size, varolan bir STS ile federasyon oluşturma veya çözümlerinizi test etmek için LocalSTS kullanma olanağı sağlar.</span><span class="sxs-lookup"><span data-stu-id="2b83e-125">This allows you to federate with an existing STS or use LocalSTS to test your solutions.</span></span> <span data-ttu-id="2b83e-126">Uzantıyı yükledikten sonra projeye sağ tıklayın ve Ara **kimlik ve erişim** bağlam menüsünde.</span><span class="sxs-lookup"><span data-stu-id="2b83e-126">After installing the extension you can right-click on your project and look for **Identity and Access** in the context menu.</span></span>  
  
-   <span data-ttu-id="2b83e-127">Beyanlar varolan ASP.Net, web siteleri ve WCF proje şablonlarında doğrudan kullanılabileceğinden, ASP.NET ve STS şablonları artık sağlanmamaktadır.</span><span class="sxs-lookup"><span data-stu-id="2b83e-127">The ASP.NET and STS templates are no longer provided as claims can be used directly in existing project templates for ASP.Net, web sites, and WCF.</span></span>  
  
-   <span data-ttu-id="2b83e-128">Denetimleri `Microsoft.IdentityModel.Web.Controls` ad alanı (`SignInControl`, `FederatedPassiveSignInControl`, ve `FederatedPassiveSignInStatus`) WIF 4.5 taşınır değil.</span><span class="sxs-lookup"><span data-stu-id="2b83e-128">The controls in the `Microsoft.IdentityModel.Web.Controls` namespace (`SignInControl`, `FederatedPassiveSignInControl`, and `FederatedPassiveSignInStatus`) are not carried over into WIF 4.5.</span></span>  
  
## <a name="changes-to-the-wif-45-api"></a><span data-ttu-id="2b83e-129">WIF 4.5 API'sine Yönelik Değişiklikler</span><span class="sxs-lookup"><span data-stu-id="2b83e-129">Changes to the WIF 4.5 API</span></span>  
  
-   <span data-ttu-id="2b83e-130">Genel olarak, talep ilgili olarak sınıflardır <xref:System.Security.Claims?displayProperty=nameWithType> ad alanı; WCF ilgili sınıflar – - hizmet sözleşmeler, Kanallar, kanal fabrikaları ve WS-Trust senaryoları için--kullanılan hizmet konakları olan <xref:System.ServiceModel.Security?displayProperty=nameWithType>; ve diğer tüm WIF sınıfları çeşitli arasında yayılır [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) ad alanları – bunlar, örneğin, WS - temsil eden sınıfları * SAML yapıları belirteci işleyicileri ve ilgili sınıfları ve WS-Federasyon senaryolarında kullanılan sınıfları ve.</span><span class="sxs-lookup"><span data-stu-id="2b83e-130">In general, claims related classes are in the <xref:System.Security.Claims?displayProperty=nameWithType> namespace; WCF related classes –- service contracts, channels, channel factories, and service hosts that are used for WS-Trust scenarios -- are in <xref:System.ServiceModel.Security?displayProperty=nameWithType>; and all other WIF classes are spread across various [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) namespaces – these include, for example, classes that represent WS-* and SAML artifacts, token handlers and related classes, and classes used in WS-Federation scenarios.</span></span> <span data-ttu-id="2b83e-131">Daha fazla bilgi için bkz: [Namespace eşleme WIF 3.5 ve WIF 4.5 arasında](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) ve [WIF API Başvurusu](../../../docs/framework/security/wif-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-131">For more information, see [Namespace Mapping between WIF 3.5 and WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) and [WIF API Reference](../../../docs/framework/security/wif-api-reference.md).</span></span>  
  
-   <span data-ttu-id="2b83e-132">Makine anahtarının, Web grubu senaryoları için oturum tanımlama bilgilerinde kullanımı sağlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="2b83e-132">Machine key has been enabled for use in session cookies for web farm scenarios.</span></span> <span data-ttu-id="2b83e-133">Daha fazla bilgi için bkz: [WIF ve Web grupları](../../../docs/framework/security/wif-and-web-farms.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-133">For more information, see [WIF and Web Farms](../../../docs/framework/security/wif-and-web-farms.md).</span></span>  
  
-   <span data-ttu-id="2b83e-134">Şimdi bildirimli olarak WIF altında yapılandırdığınız [ \<System.IdentityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) ve [ \<system.identityModel.services >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) öğeleri.</span><span class="sxs-lookup"><span data-stu-id="2b83e-134">You now declaratively configure WIF under the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) elements.</span></span> <span data-ttu-id="2b83e-135">WIF yapılandırma hakkında daha fazla bilgi için bkz: [WIF yapılandırma başvurusu](../../../docs/framework/security/wif-configuration-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2b83e-135">For more information about WIF configuration, see [WIF Configuration Reference](../../../docs/framework/security/wif-configuration-reference.md).</span></span>  
  
## <a name="other-notable-net-changes-or-features-that-are-caused-by-the-integration-of-wif-into-net"></a><span data-ttu-id="2b83e-136">WFI'nin .NET tümleştirmesinin sağladığı diğer önemli .NET değişiklikleri veya özellikleri</span><span class="sxs-lookup"><span data-stu-id="2b83e-136">Other notable .NET changes or features that are caused by the integration of WIF into .NET</span></span>  
  
-   <span data-ttu-id="2b83e-137">Beyan tabanlı kimlik doğrulaması (CBAC) yapma potansiyeli artık .NET çerçevesinde tümleşiktir.</span><span class="sxs-lookup"><span data-stu-id="2b83e-137">The potential for performing claims-based authorization (CBAC) is now integral to the .NET framework.</span></span> <span data-ttu-id="2b83e-138">Yapılandırabileceğiniz bir <xref:System.Security.Claims.ClaimsAuthorizationManager> nesnesi ve ardından <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> ve <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> kodunuzda kesinlik temelli ve bildirim temelli erişim denetimleri gerçekleştirmek için sınıflar.</span><span class="sxs-lookup"><span data-stu-id="2b83e-138">You can configure a <xref:System.Security.Claims.ClaimsAuthorizationManager> object and then use the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> and <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classes to perform imperative and declarative access checks in your code.</span></span> <span data-ttu-id="2b83e-139">CBAC, geleneksel rol tabanlı erişim denetimlerine (RBAC) göre daha fazla esneklik ve ayrıntı düzeyi sağlar.</span><span class="sxs-lookup"><span data-stu-id="2b83e-139">CBAC provides more flexibility and greater granularity than traditional role-based access checks (RBAC).</span></span> <span data-ttu-id="2b83e-140">Ayrıca yetkilendirme ilkesi büyük ayrılması iş mantığı gelen iş mantığı belirli bir talep üzerinde erişim denetimi temel alabilir veya grup talepleri ve bu talepleri yetkilendirme ilkesi yapılandırılabilir bildirimli olarak altındaolduğundantanır[ \<claimsAuthorizationManager >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="2b83e-140">It also allows greater separation of authorization policy from business logic because the business logic can base the access check on a specific claim or set of claims and the authorization policy for those claims can be configured declaratively under the [\<claimsAuthorizationManager>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element.</span></span>  
  
## <a name="wcf-changes-as-a-result-of-wif-integration"></a><span data-ttu-id="2b83e-141">WIF tümleştirmesinin doğurduğu WCF değişiklikleri:</span><span class="sxs-lookup"><span data-stu-id="2b83e-141">WCF changes as a result of WIF integration:</span></span>  
  
-   <span data-ttu-id="2b83e-142">WCF beyana dayalı kimlik modelinin yerini WIF almıştır.</span><span class="sxs-lookup"><span data-stu-id="2b83e-142">The WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="2b83e-143">Sınıflar Bunun anlamı <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, ve <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> ad alanları bırakılan WIF sınıflarını kullanarak lehinde.</span><span class="sxs-lookup"><span data-stu-id="2b83e-143">This means that classes in the <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> namespaces should be dropped in favor of using WIF classes.</span></span>  
  
-   <span data-ttu-id="2b83e-144">WIF şu anda etkin bir WCF Hizmeti belirterek `useIdentityConfiguration` özniteliği `<system.serviceModel>` / `<behaviors>` / `<serviceBehaviors>` / `<serviceCredentials>` olduğu gibi aşağıdaki XML öğesi:</span><span class="sxs-lookup"><span data-stu-id="2b83e-144">WIF is now enabled on a WCF service by specifying the `useIdentityConfiguration` attribute on the `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>` element as in the following XML:</span></span>  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
     <span data-ttu-id="2b83e-145">Kullandığınızda **kimlik ve erişim aracı Visual Studio 2012 için** (bkz **değiştirir Visual Studio deneyimine** yukarıda), aracı ekler bir `<serviceCredentials>` öğeyle `useIdentityConfiguration` özniteliği ayarlamak sizin için yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="2b83e-145">When you use the **Identity and Access Tool for Visual Studio 2012** (see **Changes to the Visual Studio Experience** above), the tool adds a `<serviceCredentials>` element with the `useIdentityConfiguration` attribute set to the configuration file for you.</span></span> <span data-ttu-id="2b83e-146">Ayrıca bir karşılık gelen ekler [ \<System.IdentityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) WIF yapılandırma ayarlarını içeren ve bağlama ve kimlik doğrulama, seçilen STS için dış kaynak sağlamak gerekli diğer ayarları ekler öğesi.</span><span class="sxs-lookup"><span data-stu-id="2b83e-146">It also adds a corresponding [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) element that contains the WIF configuration settings and adds a binding and other settings necessary to outsource authentication to your chosen STS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b83e-147">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2b83e-147">See Also</span></span>  
 [<span data-ttu-id="2b83e-148">WIF 4.5 WIF 3.5 kullanılarak oluşturulan bir uygulamayı geçirmek için yönergeler</span><span class="sxs-lookup"><span data-stu-id="2b83e-148">Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5</span></span>](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)  
 [<span data-ttu-id="2b83e-149">WIF 3.5 ve WIF 4.5 arasında Namespace eşleme</span><span class="sxs-lookup"><span data-stu-id="2b83e-149">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [<span data-ttu-id="2b83e-150">WIF API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="2b83e-150">WIF API Reference</span></span>](../../../docs/framework/security/wif-api-reference.md)  
 [<span data-ttu-id="2b83e-151">WIF yapılandırma başvurusu</span><span class="sxs-lookup"><span data-stu-id="2b83e-151">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)