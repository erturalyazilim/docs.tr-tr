---
title: "Özel Güvenli Meta Veri Uç Noktaları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
caps.latest.revision: "19"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 78fbde5f83d4a24594e06b787756c7ab3762d75a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="a8e0d-102">Özel Güvenli Meta Veri Uç Noktaları</span><span class="sxs-lookup"><span data-stu-id="a8e0d-102">Custom Secure Metadata Endpoint</span></span>
<span data-ttu-id="a8e0d-103">Bu örnek bir hizmeti meta veri olmayan exchange bağlamaları birini kullanan bir güvenli meta veri uç noktası ile uygulama ve nasıl yapılandırılacağı gösterilmektedir [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) veya fetch istemcileri Bu tür bir meta veri uç noktasından meta veriler.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="a8e0d-104">İki sistem tarafından sağlanan bağlamalar meta veri uç noktalarını gösterme için kullanılabilir: mexHttpBinding ve mexHttpsBinding.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="a8e0d-105">mexHttpBinding meta veri uç noktasına HTTP üzerinden güvenli olmayan bir biçimde göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="a8e0d-106">mexHttpsBinding meta veri uç noktasına HTTPS üzerinden güvenli bir şekilde kullanıma sunmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="a8e0d-107">Bu örnek, güvenli meta veri kullanan uç noktasını kullanıma sunmak verilmektedir <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="a8e0d-108">Bağlama üzerinde güvenlik ayarlarını değiştirmek istediğiniz ancak HTTPS kullanmak istemediğiniz durumlarda yapmak istiyor.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="a8e0d-109">MexHttpsBinding kullanırsanız, meta veri uç noktası güvenli olacaktır, ancak bağlama ayarlarını değiştirmek için bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8e0d-110">Kurulum yordamı ve yapı yönergeleri Bu örnek için bu konunun sonunda yer alır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="a8e0d-111">Hizmet</span><span class="sxs-lookup"><span data-stu-id="a8e0d-111">Service</span></span>  
 <span data-ttu-id="a8e0d-112">Bu örnek hizmetinde iki uç nokta vardır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="a8e0d-113">Uygulama uç noktasını hizmet `ICalculator` üzerinde sözleşme bir `WSHttpBinding` ile `ReliableSession` etkin ve `Message` sertifikaları kullanan güvenliği.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="a8e0d-114">Meta veri uç noktasının de kullanır `WSHttpBinding`, aynı güvenlik ayarlarına sahip ancak hiçbir `ReliableSession`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="a8e0d-115">İlgili yapılandırma şöyledir:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-115">Here is the relevant configuration:</span></span>  
  
```xml  
<services>   
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 <span data-ttu-id="a8e0d-116">Birçok diğer örnekleri varsayılan meta veri uç noktasının kullanır `mexHttpBinding`, güvenli değil.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="a8e0d-117">Meta verileri kullanarak burada güvenliği `WSHttpBinding` ile `Message` güvenlik.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="a8e0d-118">Meta veri istemcilerin bu meta verilerini almak sırayla bunlar eşleşen bir bağlama ile yapılandırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="a8e0d-119">Bu örnek iki tür istemcileri gösterir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="a8e0d-120">İlk istemci Svcutil.exe meta veri Getir ve istemci kodu ve tasarım zamanında yapılandırma oluşturmak üzere kullanır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="a8e0d-121">Hizmet için meta veriler varsayılan olmayan bağlama kullandığından, böylece bu bağlama işlemini kullanma hizmetinden meta verileri alabilir Svcutil.exe aracı özellikle yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="a8e0d-122">İkinci istemcinin kullandığı `MetadataResolver` dinamik olarak bilinen bir sözleşme meta verilerini getirmek ve dinamik olarak üretilen istemci işlemlerini çağırma.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="a8e0d-123">Svcutil istemci</span><span class="sxs-lookup"><span data-stu-id="a8e0d-123">Svcutil client</span></span>  
 <span data-ttu-id="a8e0d-124">Ana bilgisayar için varsayılan bağlama kullanırken, `IMetadataExchange` uç noktası, o uç noktası adresi ile Svcutil.exe çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="a8e0d-125">ve bu çalışır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-125">and it works.</span></span> <span data-ttu-id="a8e0d-126">Ancak bu örnekte, sunucu meta verileri barındırmak için varsayılan olmayan bir uç kullanır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="a8e0d-127">Bu nedenle Svcutil.exe doğru bağlama kullanmak için talimat gerekir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="a8e0d-128">Bu yapılabilir bir Svcutil.exe.config dosyası kullanarak.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="a8e0d-129">Svcutil.exe.config dosya normal istemci yapılandırma dosyası gibi görünüyor.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="a8e0d-130">Sözleşme ve istemci uç nokta adı yalnızca olağan dışı yönleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="a8e0d-131">Uç nokta adı burada meta verileri barındırılan ve uç nokta sözleşme olmalıdır adres düzeni adı olmalıdır `IMetadataExchange`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="a8e0d-132">Bu nedenle, Svcutil.exe aşağıdaki gibi komut satırı ile çalıştırıldığında:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="a8e0d-133">"http" ve sözleşme adlı uç noktası için görünüyor `IMetadataExchange` meta veri uç noktası ile bağlama ve iletişim exchange davranışını yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="a8e0d-134">Örnek Svcutil.exe.config dosyasında kalan bağlama yapılandırması ve meta veri uç noktasının sunucunun yapılandırma ile eşleşmesi için davranış kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="a8e0d-135">Sırayla Svcutil.exe Svcutil.exe.config yapılandırmasında alması için Svcutil.exe yapılandırma dosyası ile aynı dizinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="a8e0d-136">Sonuç olarak, yükleme konumundan Svcutil.exe Svcutil.exe.config dosyasını içeren dizine kopyalamalısınız.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="a8e0d-137">Ardından bu dizininden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-137">Then from that directory, run the following command:</span></span>  
  
```  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="a8e0d-138">Başında ". \\"Svcutil.exe kopyasını bu dizindeki (bir karşılık gelen Svcutil.exe.config olan) çalıştığını sağlar.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="a8e0d-139">MetadataResolver istemci</span><span class="sxs-lookup"><span data-stu-id="a8e0d-139">MetadataResolver client</span></span>  
 <span data-ttu-id="a8e0d-140">İstemci sözleşme ve tasarım zamanında meta verilere nasıl biliyorsa, istemci dinamik olarak bağlama ve uygulama uç noktalarını kullanarak adresini bulabilirsiniz `MetadataResolver`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="a8e0d-141">Bu örnek istemcisi bu, bağlama ve tarafından kullanılan kimlik bilgilerini nasıl yapılandırılacağını gösteren gösterir `MetadataResolver` oluşturma ve yapılandırma tarafından bir `MetadataExchangeClient`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="a8e0d-142">Svcutil.exe.config içinde görünen aynı bağlama ve sertifika bilgileri imperatively üzerinde belirtilebilir `MetadataExchangeClient`:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.    CertificateValidationMode =    X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="a8e0d-143">İle `mexClient` yapılandırılmış, biz biz ilgilendiğiniz ve kullanmak sözleşmeleri numaralandırabilir `MetadataResolver` bu sözleşmelerle bitiş noktaları listesini getirmek için:</span><span class="sxs-lookup"><span data-stu-id="a8e0d-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts =    new Collection<ContractDescription>();  
ContractDescription contract =    ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new    EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints =    MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="a8e0d-144">Biz bağlama ve adresini başlatmak için bu uç bilgilerinden son kullanabilirsiniz bir `ChannelFactory` uygulama uç noktaları ile iletişim kanalı oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```  
ChannelFactory<ICalculator> cf = new    ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="a8e0d-145">Kullanıyorsanız anahtar Bu örnek istemcisi, göstermek için noktasıdır `MetadataResolver`ve özel bağlamaları veya meta veri exchange iletişimi için davranışlar belirtmelisiniz, kullanabileceğiniz bir `MetadataExchangeClient` bu özel ayarları belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="a8e0d-146">Ayarlamak ve örneği oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a8e0d-146">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="a8e0d-147">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8e0d-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a8e0d-148">Çözümü derlemek için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8e0d-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="a8e0d-149">Aynı makinede örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="a8e0d-149">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="a8e0d-150">Setup.bat örnek yükleme klasöründen çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="a8e0d-151">Bu örneği çalıştırmak için gerekli tüm sertifikalar yükler.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="a8e0d-152">Setup.bat gelen setupCertTool.bat çalıştırarak yüklü FindPrivateKey.exe aracı kullandığına dikkat edin [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a8e0d-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a8e0d-153">İstemci uygulaması \MetadataResolverClient\bin veya \SvcutilClient\bin çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="a8e0d-154">İstemci etkinliği istemci konsol uygulaması görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-154">Client activity is displayed on the client console application.</span></span>  
  
3.  <span data-ttu-id="a8e0d-155">İstemci ve hizmet iletişim kurabildiğinden değilseniz bkz [sorun giderme ipuçları](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="a8e0d-155">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
4.  <span data-ttu-id="a8e0d-156">Sertifikaları örnekle tamamladığınızda Cleanup.bat çalıştırarak kaldırın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="a8e0d-157">Diğer güvenlik örnekleri aynı sertifikaları kullanır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="a8e0d-158">Makine genelinde örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="a8e0d-158">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="a8e0d-159">Sunucu üzerinde çalışan `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="a8e0d-160">Çalışan `setup.bat` ile `service` bağımsız değişkeni makinenin tam etki alanı adı ile bir hizmet sertifikası oluşturur ve hizmet sertifikası Service.cer adlı bir dosyaya aktarır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2.  <span data-ttu-id="a8e0d-161">Sunucu üzerinde Web.config dosyasını yeni sertifika yansıtacak şekilde düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="a8e0d-162">Diğer bir deyişle, değişiklik `findValue` özniteliğini [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) makinenin tam etki alanı adı öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3.  <span data-ttu-id="a8e0d-163">Service.cer dosya hizmeti dizininden istemci makinesinde istemci dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4.  <span data-ttu-id="a8e0d-164">İstemci üzerinde çalışan `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="a8e0d-165">Çalışan `setup.bat` ile `client` bağımsız değişkeni Client.com adlı bir istemci sertifikası oluşturur ve istemci sertifikasını Client.cer adlı bir dosyaya aktarır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5.  <span data-ttu-id="a8e0d-166">App.config dosyasında `MetadataResolverClient` istemci makinede hizmetinizin yeni adresi eşleşecek şekilde mex uç noktası adresi değerini değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="a8e0d-167">Bunun için localhost sunucunun tam etki alanı adı ile değiştirerek.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="a8e0d-168">Ayrıca metadataResolverClient.cs dosyasındaki "localhost" oluşumunun yeni hizmet sertifikası adı (sunucunun tam etki alanı adı) değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="a8e0d-169">Aynı şey SvcutilClient proje App.config için yapın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6.  <span data-ttu-id="a8e0d-170">Client.cer dosyasını istemci dizininden sunucusunda hizmet dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7.  <span data-ttu-id="a8e0d-171">İstemci üzerinde çalışan `ImportServiceCert.bat`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="a8e0d-172">Bu hizmet sertifikası Service.cer dosyadan Currentuser'a - TrustedPeople deposunu alır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8.  <span data-ttu-id="a8e0d-173">Sunucu üzerinde çalışan `ImportClientCert.bat`, bu istemci sertifikasını Client.cer dosyasından LocalMachine - TrustedPeople deposunu alır.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="a8e0d-174">Hizmeti makinede Visual Studio'da hizmet projeyi oluşturun ve çalıştığını doğrulamak için bir web tarayıcısında Yardım sayfasını seçin.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="a8e0d-175">İstemci makinesinde MetadataResolverClient veya SvcutilClient VS'den çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1.  <span data-ttu-id="a8e0d-176">İstemci ve hizmet iletişim kurabildiğinden değilseniz bkz [sorun giderme ipuçları](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="a8e0d-176">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="a8e0d-177">Örnek sonra temizlemek için</span><span class="sxs-lookup"><span data-stu-id="a8e0d-177">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="a8e0d-178">Örnek çalıştıran tamamladıktan sonra Cleanup.bat samples klasöründen çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8e0d-179">Bu komut dosyası, bu örnek makine genelinde çalıştırırken bir istemcide hizmet sertifikaları kaldırmaz.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="a8e0d-180">Çalıştırırsanız [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] makine genelinde sertifikaları kullanma örnekleri Currentuser'a - TrustedPeople deposu yüklü hizmet sertifikalarını temizlemek emin olun.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-180">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="a8e0d-181">Bunu yapmak için aşağıdaki komutu kullanın: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="a8e0d-182">Örneğin: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8e0d-183">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a8e0d-184">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-184">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a8e0d-185">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a8e0d-186">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-186">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
  
## <a name="see-also"></a><span data-ttu-id="a8e0d-187">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a8e0d-187">See Also</span></span>