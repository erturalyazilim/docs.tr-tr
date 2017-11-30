---
title: ISymUnmanagedReader::GetDocument Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7fcc18b1441093a3e3a1a0e813ccfb4ba3ad507b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="474b9-102">ISymUnmanagedReader::GetDocument Metodu</span><span class="sxs-lookup"><span data-stu-id="474b9-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="474b9-103">Bir belge bulur.</span><span class="sxs-lookup"><span data-stu-id="474b9-103">Finds a document.</span></span> <span data-ttu-id="474b9-104">Belge dili, satıcı ve türü isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="474b9-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474b9-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="474b9-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="474b9-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="474b9-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="474b9-107">[in] Belge tanımlayan URL.</span><span class="sxs-lookup"><span data-stu-id="474b9-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="474b9-108">[in] Belge dili.</span><span class="sxs-lookup"><span data-stu-id="474b9-108">[in] The document language.</span></span> <span data-ttu-id="474b9-109">Bu parametre isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="474b9-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="474b9-110">[in] Belge dili için satıcı kimliği.</span><span class="sxs-lookup"><span data-stu-id="474b9-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="474b9-111">Bu parametre isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="474b9-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="474b9-112">[in] Belge türü.</span><span class="sxs-lookup"><span data-stu-id="474b9-112">[in] The type of the document.</span></span> <span data-ttu-id="474b9-113">Bu parametre isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="474b9-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="474b9-114">[out] Döndürülen arabirimi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="474b9-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="474b9-115">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="474b9-115">Return Value</span></span>  
 <span data-ttu-id="474b9-116">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="474b9-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="474b9-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="474b9-117">Requirements</span></span>  
 <span data-ttu-id="474b9-118">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="474b9-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474b9-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="474b9-119">See Also</span></span>  
 [<span data-ttu-id="474b9-120">Isymunmanagedreader arabirimi</span><span class="sxs-lookup"><span data-stu-id="474b9-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)