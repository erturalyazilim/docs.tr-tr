---
title: "ICorRuntimeHost::CreateDomain Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0da99f05b09d44338a5f4d695fb2a4114f0e1f30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="4dc1b-102">ICorRuntimeHost::CreateDomain Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4dc1b-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="4dc1b-103">Uygulama etki alanı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-103">Creates an application domain.</span></span> <span data-ttu-id="4dc1b-104">Çağıran bir arabirim işaretçisi türü alan <xref:System._AppDomain> türünün bir örneği için <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc1b-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4dc1b-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4dc1b-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4dc1b-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="4dc1b-107">[in] Etki alanı için kolay bir ad vermek için kullanılan isteğe bağlı bir parametre.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="4dc1b-108">Bu kolay adı etki alanını tanımlamak için hata ayıklayıcıları gibi kullanıcı arabirimleri görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="4dc1b-109">[in] İşaretçiler isteğe bağlı bir dizi `IIdentity` bir izin kümesi oluşturmak için Güvenlik İlkesi aracılığıyla eşlenen kanıt temsil örnekleri.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="4dc1b-110">Bir `IIdentity` nesne elde edilebilir çağırarak [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="4dc1b-111">[out] Arabirim işaretçisi türü <xref:System._AppDomain> örneğine <xref:System.AppDomain?displayProperty=nameWithType> daha fazla etki alanı denetlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dc1b-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="4dc1b-112">Return Value</span></span>  
  
|<span data-ttu-id="4dc1b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dc1b-113">HRESULT</span></span>|<span data-ttu-id="4dc1b-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4dc1b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dc1b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dc1b-115">S_OK</span></span>|<span data-ttu-id="4dc1b-116">İşlem başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-116">The operation was successful.</span></span>|  
|<span data-ttu-id="4dc1b-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4dc1b-117">S_FALSE</span></span>|<span data-ttu-id="4dc1b-118">İşlemi tamamlayamadı.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4dc1b-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4dc1b-119">E_FAIL</span></span>|<span data-ttu-id="4dc1b-120">Bilinmeyen, geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4dc1b-121">Ortak dil çalışma zamanı (CLR), artık bir yöntem E_FAIL döndürürse, işlemde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4dc1b-122">Barındırma hiçbir API'leri yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4dc1b-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4dc1b-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4dc1b-124">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dc1b-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4dc1b-125">Requirements</span></span>  
 <span data-ttu-id="4dc1b-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dc1b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dc1b-127">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4dc1b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4dc1b-128">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="4dc1b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dc1b-129">**.NET framework sürümleri:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4dc1b-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc1b-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4dc1b-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="4dc1b-131">Icorruntimehost arabirimi</span><span class="sxs-lookup"><span data-stu-id="4dc1b-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)