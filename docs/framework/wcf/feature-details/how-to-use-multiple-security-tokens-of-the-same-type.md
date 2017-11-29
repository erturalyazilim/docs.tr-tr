---
title: "Nasıl yapılır: Aynı Türde Birden Fazla Belirteç Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9827d43ba4b0693d16380d93b066948d464bb978
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="5e67d-102">Nasıl yapılır: Aynı Türde Birden Fazla Belirteç Kullanma</span><span class="sxs-lookup"><span data-stu-id="5e67d-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="5e67d-103">İçinde [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, bir istemci iletisi yalnızca kapsanan bir belirteç herhangi bir türde.</span><span class="sxs-lookup"><span data-stu-id="5e67d-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="5e67d-104">Şimdi istemci iletileri bir türde birden çok belirteç içerebilir.</span><span class="sxs-lookup"><span data-stu-id="5e67d-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="5e67d-105">Bu konuda, bir istemci iletiye aynı türde birden çok belirteç gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="5e67d-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="5e67d-106">Bu şekilde bir hizmet yapılandıramazsınız Not: bir hizmetin yalnızca bir destekleme belirteci içerebilir.</span><span class="sxs-lookup"><span data-stu-id="5e67d-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="5e67d-107">Aynı türde birden çok güvenlik belirteçleri kullanmak için</span><span class="sxs-lookup"><span data-stu-id="5e67d-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="5e67d-108">Doldurulması için boş bağlama öğesi koleksiyon oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5e67d-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="5e67d-109">Oluşturma bir <xref:System.ServiceModel.Channels.SecurityBindingElement> çağırarak <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e67d-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="5e67d-110">Oluşturma bir <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="5e67d-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="5e67d-111">SAML belirteçleri koleksiyona ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5e67d-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="5e67d-112">Koleksiyona eklemek <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="5e67d-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="5e67d-113">Bağlama öğeleri bağlama öğesi koleksiyonuna ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5e67d-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="5e67d-114">Bağlama öğesi koleksiyonundan oluşturulan yeni bir özel bağlama döndür.</span><span class="sxs-lookup"><span data-stu-id="5e67d-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="5e67d-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="5e67d-115">Example</span></span>  
 <span data-ttu-id="5e67d-116">Yukarıdaki yordam tarafından açıklanan tüm yöntemi verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5e67d-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="5e67d-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5e67d-117">See Also</span></span>  
 [<span data-ttu-id="5e67d-118">Güvenlik mimarisi</span><span class="sxs-lookup"><span data-stu-id="5e67d-118">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)