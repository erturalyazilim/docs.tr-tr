---
title: IHostAssemblyManager::GetNonHostStoreAssemblies Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetNonHostStoreAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35e22e186b290cc4242275976f5109b73e2cf068
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="0be5a-102">IHostAssemblyManager::GetNonHostStoreAssemblies Metodu</span><span class="sxs-lookup"><span data-stu-id="0be5a-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="0be5a-103">Bir arabirim işaretçisi alır bir [Iclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ortak dil çalışma zamanı (CLR) yüklemek için konak bekliyor derleme listesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="0be5a-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be5a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0be5a-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be5a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0be5a-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="0be5a-106">[out] Adresine bir işaretçi bir `ICLRAssemblyReferenceList` yüklemek için CLR konak bekliyor derlemelerine başvurular listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="0be5a-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0be5a-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="0be5a-107">Return Value</span></span>  
  
|<span data-ttu-id="0be5a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0be5a-108">HRESULT</span></span>|<span data-ttu-id="0be5a-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0be5a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0be5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0be5a-110">S_OK</span></span>|<span data-ttu-id="0be5a-111">`GetNonHostStoreAssemblies`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="0be5a-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="0be5a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0be5a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0be5a-113">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="0be5a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0be5a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0be5a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0be5a-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="0be5a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0be5a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0be5a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0be5a-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="0be5a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0be5a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0be5a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0be5a-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="0be5a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0be5a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0be5a-120">E_FAIL</span></span>|<span data-ttu-id="0be5a-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="0be5a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0be5a-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="0be5a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0be5a-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="0be5a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0be5a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0be5a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0be5a-125">İstenen başvuruları listesini oluşturmak yeterli bellek yoktu `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="0be5a-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0be5a-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0be5a-126">Remarks</span></span>  
 <span data-ttu-id="0be5a-127">CLR başvuru yönergeleri aşağıdaki kümesini kullanarak çözer:</span><span class="sxs-lookup"><span data-stu-id="0be5a-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="0be5a-128">İlk olarak, listenin tarafından döndürülen derleme başvurularını danışır `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="0be5a-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="0be5a-129">Derleme listede görünüyorsa, CLR için normal olarak bağlar.</span><span class="sxs-lookup"><span data-stu-id="0be5a-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="0be5a-130">Derleme listede görünmez ve ana bilgisayar uygulaması sağlamıştır [Ihostassemblystore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR çağrıları [Ihostassemblystore::provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) sağlamak konak izin vermek için bağlamak için derleme.</span><span class="sxs-lookup"><span data-stu-id="0be5a-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="0be5a-131">Aksi takdirde, CLR derlemeye bağlamak başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="0be5a-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="0be5a-132">Ana bilgisayar ayarlarsa `ppReferenceList` null, CLR ilk araştırmalar Genel Derleme Önbelleği çağrılar `ProvideAssembly`ve bir derleme başvurusu çözümlemek için uygulama temel araştırmaları.</span><span class="sxs-lookup"><span data-stu-id="0be5a-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0be5a-133">Başlatma sırasında CLR çağırır `GetNonHostStoreAssemblies` yalnızca bir kez.</span><span class="sxs-lookup"><span data-stu-id="0be5a-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="0be5a-134">Yöntem yeniden çağrılmaz.</span><span class="sxs-lookup"><span data-stu-id="0be5a-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be5a-135">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0be5a-135">Requirements</span></span>  
 <span data-ttu-id="0be5a-136">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be5a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be5a-137">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0be5a-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0be5a-138">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="0be5a-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0be5a-139">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be5a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be5a-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0be5a-140">See Also</span></span>  
 [<span data-ttu-id="0be5a-141">Iclrassemblyreferencelist arabirimi</span><span class="sxs-lookup"><span data-stu-id="0be5a-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="0be5a-142">Ihostassemblymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="0be5a-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="0be5a-143">Ihostassemblystore arabirimi</span><span class="sxs-lookup"><span data-stu-id="0be5a-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)