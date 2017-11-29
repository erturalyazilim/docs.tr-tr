---
title: "Nasıl yapılır: Özel WSDL İçe Aktarma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00a845fe5c8321d521fb7baa3b16bd009fc3e660
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="e7dc7-102">Nasıl yapılır: Özel WSDL İçe Aktarma</span><span class="sxs-lookup"><span data-stu-id="e7dc7-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="e7dc7-103">Bu konu, özel WSDL içe aktarmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="e7dc7-104">Özel WSDL işlemek için uygulamanız gereken <xref:System.ServiceModel.Description.IWsdlImportExtension> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="e7dc7-105">Özel WSDL içe aktarmak için</span><span class="sxs-lookup"><span data-stu-id="e7dc7-105">To import custom WSDL</span></span>  
  
1.  <span data-ttu-id="e7dc7-106">Uygulama <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="e7dc7-107">Uygulama <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> içeri aktarılmadan önce meta verileri değiştirmeye yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="e7dc7-108">Uygulama <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> ve <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> sözleşmeleri ve meta verileri içe uç noktalarını değiştirmek için yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="e7dc7-109">İçeri aktarılan sözleşme veya uç nokta erişmek için karşılık gelen bağlam nesnesi kullanın (<xref:System.ServiceModel.Description.WsdlContractConversionContext> veya <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="e7dc7-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
          public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
    {  
            // Contract documentation  
         if (context.WsdlPortType.Documentation != null)  
         {  
               context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
    if (operation.Documentation != null)  
    {  
    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
    if (operationDescription != null)  
    {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
    }  
    }  
    }  
    }  
  
    public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
    public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
       }  
    ```  
  
2.  <span data-ttu-id="e7dc7-110">Özel WSDL alma aracını kullanmak için istemci uygulaması yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="e7dc7-111">Svcutil.exe kullanıyorsanız, bu yapılandırma yapılandırma dosyasına Svcutil.exe (Svcutil.exe.config) eklemeniz gerektiğini unutmayın:</span><span class="sxs-lookup"><span data-stu-id="e7dc7-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="e7dc7-112">Yeni bir <xref:System.ServiceModel.Description.WsdlImporter> örneği (tümleştirilmesidir <xref:System.ServiceModel.Description.MetadataSet> içeri aktarmak istediğiniz WSDL belgeleri içeren örneği) ve arama <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span><span class="sxs-lookup"><span data-stu-id="e7dc7-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e7dc7-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-113">See Also</span></span>  
 [<span data-ttu-id="e7dc7-114">Meta veriler</span><span class="sxs-lookup"><span data-stu-id="e7dc7-114">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="e7dc7-115">Meta veri alma ve verme</span><span class="sxs-lookup"><span data-stu-id="e7dc7-115">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [<span data-ttu-id="e7dc7-116">Özel WSDL yayımı</span><span class="sxs-lookup"><span data-stu-id="e7dc7-116">Custom WSDL Publication</span></span>](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)