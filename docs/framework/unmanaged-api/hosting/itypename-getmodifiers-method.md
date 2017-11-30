---
title: ITypeName::GetModifiers Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeName.GetModifiers
api_location: mscoree.dll
api_type: COM
f1_keywords: GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a7a6bfb8a8520d390844442665e4ba5feb4dcffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="bad0c-102">ITypeName::GetModifiers Metodu</span><span class="sxs-lookup"><span data-stu-id="bad0c-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="bad0c-103">Bu yöntem .NET Framework altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.</span><span class="sxs-lookup"><span data-stu-id="bad0c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad0c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bad0c-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bad0c-105">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="bad0c-105">Requirements</span></span>  
 <span data-ttu-id="bad0c-106">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad0c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad0c-107">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bad0c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bad0c-108">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="bad0c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bad0c-109">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad0c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad0c-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bad0c-110">See Also</span></span>  
 [<span data-ttu-id="bad0c-111">Barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="bad0c-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)