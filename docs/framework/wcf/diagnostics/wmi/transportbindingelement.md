---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c130093b9600c324e7179febce6857341b8a7d3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="transportbindingelement"></a><span data-ttu-id="79844-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="79844-102">TransportBindingElement</span></span>
<span data-ttu-id="79844-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="79844-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79844-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="79844-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="79844-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="79844-105">Methods</span></span>  
 <span data-ttu-id="79844-106">TransportBindingElement sınıfı herhangi bir yöntem tanımlamıyor.</span><span class="sxs-lookup"><span data-stu-id="79844-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79844-107">Özellikler</span><span class="sxs-lookup"><span data-stu-id="79844-107">Properties</span></span>  
 <span data-ttu-id="79844-108">TransportBindingElement sınıfı aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="79844-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="79844-109">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="79844-109">ManualAddressing</span></span>  
 <span data-ttu-id="79844-110">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="79844-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="79844-111">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="79844-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79844-112">Kullanıcı ileti adresleme denetimini almak istediği olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="79844-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="79844-113">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="79844-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="79844-114">Veri türü: sint64</span><span class="sxs-lookup"><span data-stu-id="79844-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="79844-115">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="79844-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79844-116">Bağlama için en büyük arabellek havuzu boyutu.</span><span class="sxs-lookup"><span data-stu-id="79844-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="79844-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="79844-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="79844-118">Veri türü: sint64</span><span class="sxs-lookup"><span data-stu-id="79844-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="79844-119">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="79844-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79844-120">Bu bağlama tarafından işlenen bir ileti için en büyük boyutu.</span><span class="sxs-lookup"><span data-stu-id="79844-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="79844-121">Düzen</span><span class="sxs-lookup"><span data-stu-id="79844-121">Scheme</span></span>  
 <span data-ttu-id="79844-122">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="79844-122">Data type: string</span></span>  
  
 <span data-ttu-id="79844-123">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="79844-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79844-124">Taşıma için kullanılacak URI düzeni.</span><span class="sxs-lookup"><span data-stu-id="79844-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79844-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="79844-125">Requirements</span></span>  
  
|<span data-ttu-id="79844-126">MOF</span><span class="sxs-lookup"><span data-stu-id="79844-126">MOF</span></span>|<span data-ttu-id="79844-127">Bildirilen Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="79844-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="79844-128">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="79844-128">Namespace</span></span>|<span data-ttu-id="79844-129">İçinde tanımlanan root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="79844-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79844-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="79844-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>