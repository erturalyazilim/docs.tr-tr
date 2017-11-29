---
title: ISymUnmanagedDocument Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument
helpviewer_keywords: ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8654f28cc4d82a5ed1419215807ec3360522fd55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="12f68-102">ISymUnmanagedDocument Arabirimi</span><span class="sxs-lookup"><span data-stu-id="12f68-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="12f68-103">Sembol deposu tarafından başvurulan bir belgeyi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="12f68-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="12f68-104">Bir belgeyi bir Tekdüzen Kaynak Konum Belirleyicisi (URL) ve bir belge türü GUID tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="12f68-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="12f68-105">URL'yi kullanarak nasıl depolanacağını bağımsız olarak belgeyi bulun ve belge türü GUID.</span><span class="sxs-lookup"><span data-stu-id="12f68-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="12f68-106">Belge kaynağı simgesi deposunda depola ve bu arabirimi aracılığıyla alın.</span><span class="sxs-lookup"><span data-stu-id="12f68-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12f68-107">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="12f68-107">Methods</span></span>  
  
|<span data-ttu-id="12f68-108">Yöntem</span><span class="sxs-lookup"><span data-stu-id="12f68-108">Method</span></span>|<span data-ttu-id="12f68-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="12f68-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12f68-110">FindClosestLine yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="12f68-111">Bir satır olabilir veya bir dizi noktası olmayabilir bu belgede verilen bir dizi noktası en yakın satır döndürür.</span><span class="sxs-lookup"><span data-stu-id="12f68-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="12f68-112">GetCheckSum yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="12f68-113">Sağlama toplamı alır.</span><span class="sxs-lookup"><span data-stu-id="12f68-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="12f68-114">Getchecksumalgorithmıd yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="12f68-115">Sağlama toplamı algoritması tanımlayıcısını alır veya hiçbir sağlama toplamı ise sıfırlardan GUİD'si döndürür.</span><span class="sxs-lookup"><span data-stu-id="12f68-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="12f68-116">GetDocumentType yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="12f68-117">Bu belgenin belge türünü alır.</span><span class="sxs-lookup"><span data-stu-id="12f68-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="12f68-118">GetLanguage yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="12f68-119">Bu belge dil tanımlayıcısını alır.</span><span class="sxs-lookup"><span data-stu-id="12f68-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="12f68-120">GetLanguageVendor yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="12f68-121">Bu belgenin dil satıcı alır.</span><span class="sxs-lookup"><span data-stu-id="12f68-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="12f68-122">GetSourceLength yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="12f68-123">Katıştırılmış kaynak bayt cinsinden uzunluğu alır.</span><span class="sxs-lookup"><span data-stu-id="12f68-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="12f68-124">GetSourceRange yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="12f68-125">Katıştırılmış kaynak belirtilen aralığını verilen arabelleğe döndürür.</span><span class="sxs-lookup"><span data-stu-id="12f68-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="12f68-126">GetURL yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="12f68-127">Bu belge için URL'yi döndürür.</span><span class="sxs-lookup"><span data-stu-id="12f68-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="12f68-128">HasEmbeddedSource yöntemi</span><span class="sxs-lookup"><span data-stu-id="12f68-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="12f68-129">Döndürür `true` hata ayıklama simgeleri; katıştırılmış kaynak belge varsa, aksi takdirde, döndürür `false`.</span><span class="sxs-lookup"><span data-stu-id="12f68-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12f68-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="12f68-130">See Also</span></span>  
 [<span data-ttu-id="12f68-131">Tanılama sembol deposu arabirimleri</span><span class="sxs-lookup"><span data-stu-id="12f68-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)