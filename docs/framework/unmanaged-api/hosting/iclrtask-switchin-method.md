---
title: "ICLRTask::SwitchIn Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchIn
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01e91c4febfebf8ec8ffd4c0ffbf8e33a4ff0edd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="70ab5-102">ICLRTask::SwitchIn Yöntemi</span><span class="sxs-lookup"><span data-stu-id="70ab5-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="70ab5-103">Ortak dil çalışma zamanı (CLR) bildirir, görev, geçerli [Iclrtask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) örneği temsil olduğu şimdi çalıştırılabilir bir durumda.</span><span class="sxs-lookup"><span data-stu-id="70ab5-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ab5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="70ab5-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70ab5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="70ab5-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="70ab5-106">[in] Görev geçerli temsil fiziksel iş parçacığı için bir tanıtıcı `ICLRTask` örneği yürütülüyor.</span><span class="sxs-lookup"><span data-stu-id="70ab5-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70ab5-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="70ab5-107">Return Value</span></span>  
  
|<span data-ttu-id="70ab5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70ab5-108">HRESULT</span></span>|<span data-ttu-id="70ab5-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70ab5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70ab5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="70ab5-110">S_OK</span></span>|<span data-ttu-id="70ab5-111">`SwitchIn`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="70ab5-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="70ab5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70ab5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70ab5-113">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="70ab5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70ab5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70ab5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70ab5-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="70ab5-115">The call timed out.</span></span>|  
|<span data-ttu-id="70ab5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70ab5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70ab5-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="70ab5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70ab5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70ab5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70ab5-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="70ab5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70ab5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70ab5-120">E_FAIL</span></span>|<span data-ttu-id="70ab5-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="70ab5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70ab5-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="70ab5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70ab5-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="70ab5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="70ab5-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="70ab5-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="70ab5-125">`SwitchIn`önceki bir çağrı olmadan çağrıldı [SwitchOut yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="70ab5-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70ab5-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="70ab5-126">Remarks</span></span>  
 <span data-ttu-id="70ab5-127">`threadHandle` Parametresi temsil eden bir tanıtıcı görev üzerinde geçerli tarafından gösterilen işletim sistemi iş parçacığına `ICLRTask` örneği zamanlandı.</span><span class="sxs-lookup"><span data-stu-id="70ab5-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="70ab5-128">Bu iş parçacığında kimliğe bürünme oluştuysa, çağırmalısınız [Ihostsecuritymanager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) görevde geçmeden önce.</span><span class="sxs-lookup"><span data-stu-id="70ab5-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70ab5-129">Çağrı `SwitchIn` önceki bir çağrı olmadan `SwitchOut` HOST_E_INVALIDOPERATION HRESULT değerle başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="70ab5-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70ab5-130">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="70ab5-130">Requirements</span></span>  
 <span data-ttu-id="70ab5-131">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70ab5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70ab5-132">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70ab5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70ab5-133">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="70ab5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70ab5-134">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70ab5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ab5-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70ab5-135">See Also</span></span>  
 [<span data-ttu-id="70ab5-136">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="70ab5-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="70ab5-137">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="70ab5-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="70ab5-138">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="70ab5-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="70ab5-139">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="70ab5-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)