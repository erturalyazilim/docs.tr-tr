---
title: Hizmetleri Tasarlama ve Uygulama
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
caps.latest.revision: "37"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee2564b59ba0c0377c93c22787974ac0a980e64b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="designing-and-implementing-services"></a><span data-ttu-id="6914b-102">Hizmetleri Tasarlama ve Uygulama</span><span class="sxs-lookup"><span data-stu-id="6914b-102">Designing and Implementing Services</span></span>
<span data-ttu-id="6914b-103">Bu bölümde tanımlamak ve uygulamak gösterilmiştir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sözleşmeleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-103">This section shows you how to define and implement [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] contracts.</span></span> <span data-ttu-id="6914b-104">Bir hizmet sözleşmesini ne bir uç nokta için dış dünya iletişim kurar belirtir.</span><span class="sxs-lookup"><span data-stu-id="6914b-104">A service contract specifies what an endpoint communicates to the outside world.</span></span> <span data-ttu-id="6914b-105">Daha somut bir düzeyde, bu temel ileti exchange desenleri (MEPs) düzenlenmiştir belirli iletileri kümesi hakkında istek/yanıt gibi tek yönlü ve çift yönlü açıklamadır.</span><span class="sxs-lookup"><span data-stu-id="6914b-105">At a more concrete level, it is a statement about a set of specific messages organized into basic message exchange patterns (MEPs), such as request/reply, one-way, and duplex.</span></span> <span data-ttu-id="6914b-106">Bir hizmet sözleşmesini ileti alışverişlerinde mantıksal olarak ilişkili bir dizi, bir hizmet işlemi tek bir ileti exchange ise.</span><span class="sxs-lookup"><span data-stu-id="6914b-106">If a service contract is a logically related set of message exchanges, a service operation is a single message exchange.</span></span> <span data-ttu-id="6914b-107">Örneğin, bir `Hello` işlemi (arayan Tebrik Duyurusu şekilde) açıkça bir ileti kabul etmeniz gerekir ve olabilir veya (işlemi geçici kullanım bağlı olarak) bir ileti döndürmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="6914b-107">For example, a `Hello` operation must obviously accept one message (so the caller can announce the greeting) and may or may not return a message (depending upon the courtesy of the operation).</span></span>  
  
 <span data-ttu-id="6914b-108">Sözleşmeler ve diğer temel hakkında daha fazla bilgi için [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] bkz, [temel Windows Communication Foundation kavramları](../../../docs/framework/wcf/fundamental-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-108">For more information about contracts and other core [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] concepts, see [Fundamental Windows Communication Foundation Concepts](../../../docs/framework/wcf/fundamental-concepts.md).</span></span> <span data-ttu-id="6914b-109">Bu konu, hizmet sözleşmelerini anlamaya odaklanır.</span><span class="sxs-lookup"><span data-stu-id="6914b-109">This topic focuses on understanding service contracts.</span></span> <span data-ttu-id="6914b-110">Hizmet sözleşmeleri hizmetlerine bağlanmak için kullanan istemciler oluşturma hakkında daha fazla bilgi için bkz: [WCF istemcisi genel bakış](../../../docs/framework/wcf/wcf-client-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-110">For more information about how to build clients that use service contracts to connect to services, see [WCF Client Overview](../../../docs/framework/wcf/wcf-client-overview.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="6914b-111">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="6914b-111">Overview</span></span>  
 <span data-ttu-id="6914b-112">Bu konu, tasarlama ve uygulama için bir üst düzey kavramsal yönlendirmesini sağlar [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-112">This topic provides a high level conceptual orientation to designing and implementing [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="6914b-113">Konuları tasarım ve uygulama özellikleri hakkında daha ayrıntılı bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6914b-113">Subtopics provide more detailed information about the specifics of design and implementation.</span></span> <span data-ttu-id="6914b-114">Önce tasarlama ve uygulama, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] uygulama önerilir doğrulayın:</span><span class="sxs-lookup"><span data-stu-id="6914b-114">Before designing and implementing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application, it is recommended that you:</span></span>  
  
-   <span data-ttu-id="6914b-115">Anlamak hizmet sözleşmesini ne olduğu, nasıl çalıştığı ve nasıl oluşturulacağı.</span><span class="sxs-lookup"><span data-stu-id="6914b-115">Understand what a service contract is, how it works, and how to create one.</span></span>  
  
-   <span data-ttu-id="6914b-116">Sözleşmeleri en düşük gereksinimler durumunu anlamak, çalışma zamanı yapılandırma veya barındırma ortamı desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="6914b-116">Understand that contracts state minimum requirements that runtime configuration or the hosting environment may not support.</span></span>  
  
## <a name="service-contracts"></a><span data-ttu-id="6914b-117">Hizmet Sözleşmeleri</span><span class="sxs-lookup"><span data-stu-id="6914b-117">Service Contracts</span></span>  
 <span data-ttu-id="6914b-118">Bir hizmet sözleşmesini aşağıdaki belirtir:</span><span class="sxs-lookup"><span data-stu-id="6914b-118">A service contract specifies the following:</span></span>  
  
-   <span data-ttu-id="6914b-119">Bir sözleşme işlemleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="6914b-119">The operations a contract exposes.</span></span>  
  
-   <span data-ttu-id="6914b-120">Değiştirilen iletilerin açısından işlemleri imzası.</span><span class="sxs-lookup"><span data-stu-id="6914b-120">The signature of the operations in terms of messages exchanged.</span></span>  
  
-   <span data-ttu-id="6914b-121">Bu iletileri veri türleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-121">The data types of these messages.</span></span>  
  
-   <span data-ttu-id="6914b-122">Operations konumu.</span><span class="sxs-lookup"><span data-stu-id="6914b-122">The location of the operations.</span></span>  
  
-   <span data-ttu-id="6914b-123">Belirli protokolleri ve hizmeti ile başarılı iletişimi desteklemek için kullanılan serileştirme biçimleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-123">The specific protocols and serialization formats that are used to support successful communication with the service.</span></span>  
  
 <span data-ttu-id="6914b-124">Örneğin, bir satın alma siparişi sözleşme olabilir bir `CreateOrder` bir giriş sırası bilgilerinin kabul işlemi türleri ve bir sıra tanımlayıcısını dahil olmak üzere, başarı veya başarısızlık bilgileri döndürür.</span><span class="sxs-lookup"><span data-stu-id="6914b-124">For example, a purchase order contract might have a `CreateOrder` operation that accepts an input of order information types and returns success or failure information, including an order identifier.</span></span> <span data-ttu-id="6914b-125">Ayrıca olabilir bir `GetOrderStatus` sipariş tanımlayıcı kabul edip sipariş durum bilgilerini döndürür işlemi.</span><span class="sxs-lookup"><span data-stu-id="6914b-125">It might also have a `GetOrderStatus` operation that accepts an order identifier and returns order status information.</span></span> <span data-ttu-id="6914b-126">Bu tür bir hizmet sözleşmesini belirtmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="6914b-126">A service contract of this sort would specify:</span></span>  
  
1.  <span data-ttu-id="6914b-127">Satın alma siparişi sözleşme, oluşmuştur `CreateOrder` ve `GetOrderStatus` işlemleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-127">That the purchase order contract consisted of `CreateOrder` and `GetOrderStatus` operations.</span></span>  
  
2.  <span data-ttu-id="6914b-128">Operations belirttiğiniz iletileri giriş ve ileti çıkışı.</span><span class="sxs-lookup"><span data-stu-id="6914b-128">That the operations have specified input messages and output messages.</span></span>  
  
3.  <span data-ttu-id="6914b-129">Bu iletiler taşıyabilir veriler.</span><span class="sxs-lookup"><span data-stu-id="6914b-129">The data that these messages can carry.</span></span>  
  
4.  <span data-ttu-id="6914b-130">Kategorik deyimleri başarıyla iletileri işlemek için gerekli iletişimini altyapısıyla ilgili.</span><span class="sxs-lookup"><span data-stu-id="6914b-130">Categorical statements about the communication infrastructure necessary to successfully process the messages.</span></span> <span data-ttu-id="6914b-131">Örneğin, bu ayrıntıları dahil olup olmadığını ve hangi forms güvenlik başarıyla iletişim kurabilmek için sahip gereklidir.</span><span class="sxs-lookup"><span data-stu-id="6914b-131">For example, these details include whether and what forms of security are required to establish successful communication.</span></span>  
  
 <span data-ttu-id="6914b-132">Bu tür birçok platformda (dahil olmak üzere Microsoft dışı platformlar) diğer uygulamalara yönelik bilgileri iletmek için XML Hizmet sözleşmeleri genel olarak standart XML biçimlerde gibi belirtilmiştir [Web Hizmetleri Açıklama Dili](http://go.microsoft.com/fwlink/?LinkId=94952) () WSDL) ve [XML Şeması](http://go.microsoft.com/fwlink/?LinkId=94953) (XSD), diğerlerinin yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="6914b-132">To convey this kind of information to other applications on many platforms (including non-Microsoft platforms), XML service contracts are publicly expressed in standard XML formats, such as [Web Services Description Language](http://go.microsoft.com/fwlink/?LinkId=94952) (WSDL) and [XML Schema](http://go.microsoft.com/fwlink/?LinkId=94953) (XSD), among others.</span></span> <span data-ttu-id="6914b-133">Geliştiriciler için birçok platformda belirtimi dili anlamaları için hem dillere birlikte çalışabilirliği sağlamak için tasarlandığından hizmeti ile iletişim kurabilen uygulamaları oluşturmak için bu ortak sözleşme bilgilerini kullanabilirsiniz Genel form, biçimleri ve protokolleri hizmetini destekleyen açıklayarak.</span><span class="sxs-lookup"><span data-stu-id="6914b-133">Developers for many platforms can use this public contract information to create applications that can communicate with the service, both because they understand the language of the specification and because those languages are designed to enable interoperation by describing the public forms, formats, and protocols that the service supports.</span></span> <span data-ttu-id="6914b-134">Hakkında daha fazla bilgi için [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tanıtıcıları bilgi, bu tür bkz [meta verileri](../../../docs/framework/wcf/feature-details/metadata.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-134">For more information about how [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] handles this kind of information, see [Metadata](../../../docs/framework/wcf/feature-details/metadata.md).</span></span>  
  
 <span data-ttu-id="6914b-135">Sözleşmeleri birçok yolu ifade edilebilir ve WSDL ve XSD Hizmetleri erişilebilir bir biçimde tanımlamak için mükemmel dilleri olsa da, bunlar doğrudan kullanılacak zor diller ve yalnızca bir hizmet, hizmet sözleşmesi uygulamaları açıklamaları.</span><span class="sxs-lookup"><span data-stu-id="6914b-135">Contracts can be expressed many ways, and while WSDL and XSD are excellent languages to describe services in an accessible way, they are difficult languages to use directly and are merely descriptions of a service, not service contract implementations.</span></span> <span data-ttu-id="6914b-136">Bu nedenle, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] uygulamalar, yönetilen öznitelikleri, arabirimleri ve sınıfları hizmet yapısını tanımlamak ve uygulamak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="6914b-136">Therefore, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications use managed attributes, interfaces, and classes both to define the structure of a service and to implement it.</span></span>  
  
 <span data-ttu-id="6914b-137">Yönetilen türlerinde tanımlanan ortaya çıkan sözleşmeyi olabilir *dışarı* meta veri olarak — WSDL ve XSD — istemcileri veya diğer hizmet Implementers tarafından gerektiğinde.</span><span class="sxs-lookup"><span data-stu-id="6914b-137">The resulting contract defined in managed types can be *exported* as metadata—WSDL and XSD—when needed by clients or other service implementers.</span></span> <span data-ttu-id="6914b-138">Sonuç (ortak meta verileri kullanarak) açıklanan basit bir programlama modeli, için tüm istemci uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="6914b-138">The result is a straightforward programming model that can be described (using public metadata) to any client application.</span></span> <span data-ttu-id="6914b-139">İçin temel alınan SOAP iletilerine, taşıma ve güvenlikle ilgili bilgileri ve benzeri ayrıntılarını bırakılabilir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], gerekli dönüşümleri gerçekleştirir ve hizmet sözleşme türünü XML tür sistemi sistem otomatik olarak.</span><span class="sxs-lookup"><span data-stu-id="6914b-139">The details of the underlying SOAP messages, the transportation and security-related information, and so on, can be left to [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], which performs the necessary conversions to and from the service contract type system to the XML type system automatically.</span></span>  
  
 <span data-ttu-id="6914b-140">Sözleşmeleri tasarlama hakkında daha fazla bilgi için bkz: [Hizmet sözleşmeleri tasarlama](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-140">For more information about designing contracts, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="6914b-141">Sözleşmelerini uygulama hakkında daha fazla bilgi için bkz: [hizmet sözleşmelerini uygulama](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-141">For more information about implementing contracts, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
### <a name="messages-up-front-and-center"></a><span data-ttu-id="6914b-142">Ön ve merkezi iletileri</span><span class="sxs-lookup"><span data-stu-id="6914b-142">Messages Up Front and Center</span></span>  
 <span data-ttu-id="6914b-143">Yönetilen arabirimleri, sınıflar ve yöntemler modeli hizmet işlemlerine kullanarak basit uzaktan yordam çağrısı (RPC) kullanıldığında-stil yöntemi imzalar, hangi bir yönteme parametreleri geçirme dönüş değerleri alma olup normal biçiminde bir nesne veya başka bir kod türünden işlevselliği isteniyor.</span><span class="sxs-lookup"><span data-stu-id="6914b-143">Using managed interfaces, classes, and methods to model service operations is straightforward when you are used to remote procedure call (RPC)-style method signatures, in which passing parameters into a method and receiving return values is the normal form of requesting functionality from an object or other type of code.</span></span> <span data-ttu-id="6914b-144">Örneğin, kullanarak programcıları diller gibi yönetilen [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ve C++ COM uygulayabileceğiniz bilgilerini RPC-style yaklaşımın (nesneleri veya arabirimleri kullanarak olup olmadığını) oluşturulmasına [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Hizmet sözleşmeleri sorunlarınız olmadan RPC stilde devralınan dağıtılmış nesne sistemleri.</span><span class="sxs-lookup"><span data-stu-id="6914b-144">For example, programmers using managed languages such as [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and C++ COM can apply their knowledge of the RPC-style approach (whether using objects or interfaces) to the creation of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service contracts without experiencing the problems inherent in RPC-style distributed object systems.</span></span> <span data-ttu-id="6914b-145">Hizmet yönlendirmesi programlama deneyimine kolaylığı ve RPC aşina olduğunuz korurken geniş eşleşmiş, ileti kaynaklı programlama yararları sağlar.</span><span class="sxs-lookup"><span data-stu-id="6914b-145">Service orientation provides the benefits of loosely coupled, message-oriented programming while retaining the ease and familiarity of the RPC programming experience.</span></span>  
  
 <span data-ttu-id="6914b-146">İleti kaynaklı uygulama programlama arabirimleri, Microsoft MSMQ gibi ileti kuyrukları gibi birçok Programcı daha rahat <xref:System.Messaging> .NET Framework veya HTTP istekleri gönderen yapılandırılmamış XML ad alanları.</span><span class="sxs-lookup"><span data-stu-id="6914b-146">Many programmers are more comfortable with message-oriented application programming interfaces, such as message queues like Microsoft MSMQ, the <xref:System.Messaging> namespaces in the .NET Framework, or sending unstructured XML in HTTP requests, to name a few.</span></span> <span data-ttu-id="6914b-147">İleti düzeyinde programlama hakkında daha fazla bilgi için bkz: [kullanarak ileti sözleşmeleri](../../../docs/framework/wcf/feature-details/using-message-contracts.md), [hizmet kanal düzeyi programlama](../../../docs/framework/wcf/extending/service-channel-level-programming.md), ve [POXuygulamalarıilebirlikteçalışabilirlik](../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-147">For more information about programming at the message level, see [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md), [Service Channel-Level Programming](../../../docs/framework/wcf/extending/service-channel-level-programming.md), and [Interoperability with POX Applications](../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).</span></span>  
  
### <a name="understanding-the-hierarchy-of-requirements"></a><span data-ttu-id="6914b-148">Gereksinimleri hiyerarşisini anlama</span><span class="sxs-lookup"><span data-stu-id="6914b-148">Understanding the Hierarchy of Requirements</span></span>  
 <span data-ttu-id="6914b-149">Bir hizmet sözleşmesini operations grupları; ileti değişim deseni, ileti türleri ve veri türleri bu iletileri taşıyan belirtir; çalışma zamanı davranışını sözleşme desteklemek için bir uygulama olmalıdır kategorilerini belirtir (örneğin, iletileri imzalanmış ve şifrelenecek olduğunu gerektiren).</span><span class="sxs-lookup"><span data-stu-id="6914b-149">A service contract groups the operations; specifies the message exchange pattern, message types, and data types those messages carry; and indicates categories of run-time behavior an implementation must have to support the contract (for example, it may require that messages be encrypted and signed).</span></span> <span data-ttu-id="6914b-150">Hizmet sözleşmesi tam olarak nasıl bu gereksinimleri, yalnızca, olması gereken karşılandığından belirtmiyor.</span><span class="sxs-lookup"><span data-stu-id="6914b-150">The service contract itself does not specify precisely how these requirements are met, only that they must be.</span></span> <span data-ttu-id="6914b-151">Şifreleme veya bir ileti imzalanmış şekilde en fazla uygulama ve uyumlu bir hizmet yapılandırmasını türüdür.</span><span class="sxs-lookup"><span data-stu-id="6914b-151">The type of encryption or the manner in which a message is signed is up to the implementation and configuration of a compliant service.</span></span>  
  
 <span data-ttu-id="6914b-152">Sözleşme davranışı eklemek için belirli konular hizmet sözleşmesini uygulama ve çalışma zamanı yapılandırma gerektirir şekilde dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="6914b-152">Notice the way that the contract requires certain things of the service contract implementation and the run-time configuration to add behavior.</span></span> <span data-ttu-id="6914b-153">Bir hizmeti kullanmak için kullanıma sunmak için karşılanması gereken gereksinimleri kümesi gereksinimleri önceki kümesinde oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6914b-153">The set of requirements that must be met to expose a service for use builds on the preceding set of requirements.</span></span> <span data-ttu-id="6914b-154">Bir sözleşme uygulama gereksinimlerini yaparsa, bir uygulama henüz gerektirebilir için yapılandırma ve çalıştırmak hizmeti etkinleştirmek bağlamaları daha fazla.</span><span class="sxs-lookup"><span data-stu-id="6914b-154">If a contract makes requirements of the implementation, an implementation can require yet more of the configuration and bindings that enable the service to run.</span></span> <span data-ttu-id="6914b-155">Son olarak, konak uygulama hizmet yapılandırması bağlamaları Ekle ve herhangi bir gereksinimi desteklemelidir.</span><span class="sxs-lookup"><span data-stu-id="6914b-155">Finally, the host application must also support any requirements that the service configuration and bindings add.</span></span>  
  
 <span data-ttu-id="6914b-156">Bu ek gereksinim işlem tasarlama, uygulama, yapılandırma ve barındırma çalışırken göz önünde bulundurmanız önemlidir bir [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] hizmet uygulaması.</span><span class="sxs-lookup"><span data-stu-id="6914b-156">This additive requirement process is important to keep in mind while designing, implementing, configuring, and hosting a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service application.</span></span> <span data-ttu-id="6914b-157">Örneğin, sözleşmenin bir oturum desteklemek gerektiğini belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6914b-157">For example, the contract can specify that it needs to support a session.</span></span> <span data-ttu-id="6914b-158">Bu durumda, bağlama sözleşme bu gereksinimi desteklemek için yapılandırmanız gerekir ya da hizmet uygulaması çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="6914b-158">If so, then you must configure the binding to support that contractual requirement, or the service implementation will not work.</span></span> <span data-ttu-id="6914b-159">Veya hizmet Windows tümleşik kimlik doğrulaması gerektiriyorsa ve Internet Information Services (IIS) barındırılan hizmetin bulunduğu Web uygulaması Windows tümleşik kimlik açık ve kapalı anonim destek olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6914b-159">Or if your service requires Windows Integrated Authentication and is hosted in Internet Information Services (IIS), the Web application in which the service resides must have Windows Integrated Authentication turned on and anonymous support turned off.</span></span> <span data-ttu-id="6914b-160">Farklı hizmet ana uygulama türleri etkisini ve özellikler hakkında daha fazla bilgi için bkz: [barındırma hizmetleri](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="6914b-160">For more information about the features and impact of the different service host application types, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6914b-161">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6914b-161">See Also</span></span>  
 [<span data-ttu-id="6914b-162">Hizmet sözleşmeleri tasarlama</span><span class="sxs-lookup"><span data-stu-id="6914b-162">Designing Service Contracts</span></span>](../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="6914b-163">Hizmet sözleşmelerini uygulama</span><span class="sxs-lookup"><span data-stu-id="6914b-163">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)