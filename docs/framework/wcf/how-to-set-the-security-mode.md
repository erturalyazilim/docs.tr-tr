---
title: "Nasıl yapılır: Güvenlik Modunu Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: "22"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 595999bfa7d3472fc31274a0c9652af5416d2da5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="38a38-102">Nasıl yapılır: Güvenlik Modunu Ayarlama</span><span class="sxs-lookup"><span data-stu-id="38a38-102">How to: Set the Security Mode</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="38a38-103">Güvenlik en önceden tanımlanmış bağlamaları üzerinde bulunan üç genel güvenlik modu vardır: Aktarım, iletisi ve "ileti kimlik bilgileri ile taşıma."</span><span class="sxs-lookup"><span data-stu-id="38a38-103"> security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="38a38-104">İki ek modları için iki bağlamaları belirli: "yalnızca Aktarım-credential" modu bulunan <xref:System.ServiceModel.BasicHttpBinding>ve bulunan "İki" modu <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="38a38-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="38a38-105">Ancak, bu konuda üç genel güvenlik modlarını yoğunlaşır: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, ve <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="38a38-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
 <span data-ttu-id="38a38-106">Önceden tanımlanmış her bağlama tüm bu modlarını desteklediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="38a38-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="38a38-107">Bu konuda moduyla ayarlar <xref:System.ServiceModel.WSHttpBinding> ve <xref:System.ServiceModel.NetTcpBinding> sınıfları ve modunu hem program aracılığıyla ve yapılandırma yoluyla nasıl ayarlanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="38a38-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../includes/crdefault-md.md)]<span data-ttu-id="38a38-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] güvenlik, bkz: [güvenliğine genel bakış](../../../docs/framework/wcf/feature-details/security-overview.md), [Hizmetleri güvenli hale getirme](../../../docs/framework/wcf/securing-services.md), ve [güvenli hale getirme hizmetler ve istemcileri](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="38a38-108"> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] security, see [Security Overview](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), and [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="38a38-109">Aktarım modu ve ileti bkz [taşıma güvenliği](../../../docs/framework/wcf/feature-details/transport-security.md) ve [ileti güvenliği](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="38a38-109"> transport mode and message, see [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) and [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
### <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="38a38-110">Kod içinde kullanılan güvenlik modunu ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="38a38-110">To set the security mode in code</span></span>  
  
1.  <span data-ttu-id="38a38-111">Kullanmakta olduğunuz bağlama sınıfının bir örneğini oluşturun.</span><span class="sxs-lookup"><span data-stu-id="38a38-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="38a38-112">Önceden tanımlanmış bağlamaları listesi için bkz: [System-Provided bağlamaları](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="38a38-112">For a list of predefined bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="38a38-113">Bu örnek bir örneğini oluşturur <xref:System.ServiceModel.WSHttpBinding> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="38a38-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
2.  <span data-ttu-id="38a38-114">Ayarlama `Mode` tarafından döndürülen nesne özelliğinin `Security` özelliği.</span><span class="sxs-lookup"><span data-stu-id="38a38-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     <span data-ttu-id="38a38-115">Alternatif olarak, modunu aşağıdaki kodda gösterildiği gibi iletiyi ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="38a38-115">Alternatively, set the mode to message, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     <span data-ttu-id="38a38-116">Veya aşağıdaki kodda gösterildiği gibi ileti kimlik bilgileriyle taşıma için modunu ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="38a38-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  <span data-ttu-id="38a38-117">Aşağıdaki kodda gösterildiği gibi bağlama oluşturucuda modu da ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="38a38-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="38a38-118">ClientCredentialType özelliği ayarlama</span><span class="sxs-lookup"><span data-stu-id="38a38-118">Setting the ClientCredentialType Property</span></span>  
 <span data-ttu-id="38a38-119">Üç değerden birini modunu ayarlama belirler nasıl ayarlanacağını `ClientCredentialType` özelliği.</span><span class="sxs-lookup"><span data-stu-id="38a38-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="38a38-120">Örneğin, kullanarak <xref:System.ServiceModel.WSHttpBinding> modu ayarını sınıfı `Transport` ayarlamalısınız anlamına gelir <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> özelliği <xref:System.ServiceModel.HttpTransportSecurity> uygun bir değere sınıfı.</span><span class="sxs-lookup"><span data-stu-id="38a38-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="38a38-121">Aktarım modu için ClientCredentialType özelliğini ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="38a38-121">To set the ClientCredentialType property for Transport mode</span></span>  
  
1.  <span data-ttu-id="38a38-122">Bağlama örneği oluşturun.</span><span class="sxs-lookup"><span data-stu-id="38a38-122">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="38a38-123">Ayarlama `Mode` özelliğine `Transport`.</span><span class="sxs-lookup"><span data-stu-id="38a38-123">Set the `Mode` property to `Transport`.</span></span>  
  
3.  <span data-ttu-id="38a38-124">Ayarlama `ClientCredential` uygun bir değere özelliği.</span><span class="sxs-lookup"><span data-stu-id="38a38-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="38a38-125">Aşağıdaki kod özelliği ayarlar `Windows`.</span><span class="sxs-lookup"><span data-stu-id="38a38-125">The following code sets the property to `Windows`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="38a38-126">İleti modu ClientCredentialType özelliğini ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="38a38-126">To set the ClientCredentialType property for Message mode</span></span>  
  
1.  <span data-ttu-id="38a38-127">Bağlama örneği oluşturun.</span><span class="sxs-lookup"><span data-stu-id="38a38-127">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="38a38-128">Ayarlama `Mode` özelliğine `Message`.</span><span class="sxs-lookup"><span data-stu-id="38a38-128">Set the `Mode` property to `Message`.</span></span>  
  
3.  <span data-ttu-id="38a38-129">Ayarlama `ClientCredential` uygun bir değere özelliği.</span><span class="sxs-lookup"><span data-stu-id="38a38-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="38a38-130">Aşağıdaki kod özelliği ayarlar `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="38a38-130">The following code sets the property to `Certificate`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="38a38-131">Yapılandırma modu ve ClientCredentialType özelliğini ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="38a38-131">To set the Mode and ClientCredentialType property in configuration</span></span>  
  
1.  <span data-ttu-id="38a38-132">Bir uygun bağlama öğesi ekleme [ \<bağlamaları >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) yapılandırma dosyası öğesi.</span><span class="sxs-lookup"><span data-stu-id="38a38-132">Add an appropriate binding element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="38a38-133">Aşağıdaki örnek, bir [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="38a38-133">The following example adds a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
2.  <span data-ttu-id="38a38-134">Ekleme bir `<binding>` öğesi ve kümesi kendi `name` öznitelik için uygun bir değer.</span><span class="sxs-lookup"><span data-stu-id="38a38-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="38a38-135">Ekleme bir `<security>` öğesi ve kümesi `mode` özniteliğini `Message`, `Transport`, veya `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="38a38-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="38a38-136">Mod ayarlanmışsa `Transport`, ekleme bir `<transport>` öğesi ve kümesi `clientCredential` öznitelik için uygun bir değer.</span><span class="sxs-lookup"><span data-stu-id="38a38-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>  
  
     <span data-ttu-id="38a38-137">Aşağıdaki örnek modunu ayarlar "`Transport"`ve ardından ayarlar `clientCredentialType` özniteliği `<transport>` öğesine"`Windows"`.</span><span class="sxs-lookup"><span data-stu-id="38a38-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="38a38-138">Alternatif olarak, kümesinin `security mode` için "`Message"`takip eden bir `<"message">` öğesi.</span><span class="sxs-lookup"><span data-stu-id="38a38-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="38a38-139">Bu örnek ayarlar `clientCredentialType` için "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="38a38-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="38a38-140">Kullanarak <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> değeri özel bir durumdur ve aşağıda açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="38a38-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>  
  
### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="38a38-141">TransportWithMessageCredential kullanma</span><span class="sxs-lookup"><span data-stu-id="38a38-141">Using TransportWithMessageCredential</span></span>  
 <span data-ttu-id="38a38-142">Güvenlik modu ayarlarken `TransportWithMessageCredential`, aktarım düzeyinde güvenlik sağlayan gerçek mekanizması taşıma belirler.</span><span class="sxs-lookup"><span data-stu-id="38a38-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="38a38-143">Örneğin, HTTP protokolünü HTTP (HTTPS) üzerinden Güvenli Yuva Katmanı (SSL) kullanır.</span><span class="sxs-lookup"><span data-stu-id="38a38-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="38a38-144">Bu nedenle, ayarı `ClientCredentialType` herhangi bir aktarım güvenlik nesnenin özelliği (gibi <xref:System.ServiceModel.HttpTransportSecurity>) göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="38a38-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="38a38-145">Diğer bir deyişle, yalnızca ayarlayabilirsiniz `ClientCredentialType` ileti güvenlik nesnesinin (için `WSHttpBinding` bağlama, <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> nesnesi).</span><span class="sxs-lookup"><span data-stu-id="38a38-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="38a38-146">[Nasıl yapılır: kullanım taşıma Güveniği ve ileti kimlik bilgilerini](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="38a38-146"> [How to: Use Transport Security and Message Credentials](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a38-147">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="38a38-147">See Also</span></span>  
 [<span data-ttu-id="38a38-148">Nasıl yapılır: bir SSL sertifikası ile bir bağlantı noktası yapılandırın</span><span class="sxs-lookup"><span data-stu-id="38a38-148">How to: Configure a Port with an SSL Certificate</span></span>](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="38a38-149">Nasıl yapılır: kullanım taşıma Güveniği ve ileti kimlik bilgileri</span><span class="sxs-lookup"><span data-stu-id="38a38-149">How to: Use Transport Security and Message Credentials</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [<span data-ttu-id="38a38-150">Taşıma güvenliği</span><span class="sxs-lookup"><span data-stu-id="38a38-150">Transport Security</span></span>](../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="38a38-151">İleti güvenliği</span><span class="sxs-lookup"><span data-stu-id="38a38-151">Message Security</span></span>](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="38a38-152">Güvenlik genel bakış</span><span class="sxs-lookup"><span data-stu-id="38a38-152">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="38a38-153">Sistem tarafından sağlanan bağlamalar</span><span class="sxs-lookup"><span data-stu-id="38a38-153">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="38a38-154">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="38a38-154">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)  
 [<span data-ttu-id="38a38-155">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="38a38-155">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)  
 [<span data-ttu-id="38a38-156">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="38a38-156">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)