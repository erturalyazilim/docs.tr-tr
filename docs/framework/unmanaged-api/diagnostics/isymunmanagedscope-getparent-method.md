---
title: ISymUnmanagedScope::GetParent Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetParent
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68215224467170962e897964483a4ce13d7b6366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="d5fdb-102">ISymUnmanagedScope::GetParent Metodu</span><span class="sxs-lookup"><span data-stu-id="d5fdb-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="d5fdb-103">Bu kapsam üst kapsamı alır.</span><span class="sxs-lookup"><span data-stu-id="d5fdb-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5fdb-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d5fdb-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5fdb-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="d5fdb-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d5fdb-106">[out] Bir işaretçi döndürülen [Isymunmanagedscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="d5fdb-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5fdb-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="d5fdb-107">Return Value</span></span>  
 <span data-ttu-id="d5fdb-108">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="d5fdb-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5fdb-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d5fdb-109">Requirements</span></span>  
 <span data-ttu-id="d5fdb-110">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5fdb-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5fdb-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d5fdb-111">See Also</span></span>  
 [<span data-ttu-id="d5fdb-112">Isymunmanagedscope arabirimi</span><span class="sxs-lookup"><span data-stu-id="d5fdb-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="d5fdb-113">GetChildren yöntemi</span><span class="sxs-lookup"><span data-stu-id="d5fdb-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)