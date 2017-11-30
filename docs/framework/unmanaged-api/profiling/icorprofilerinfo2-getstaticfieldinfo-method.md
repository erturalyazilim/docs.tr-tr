---
title: ICorProfilerInfo2::GetStaticFieldInfo Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7cf16a0fae7f3e2afd095534b2e7f7957d44e3e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="ddb11-102">ICorProfilerInfo2::GetStaticFieldInfo Metodu</span><span class="sxs-lookup"><span data-stu-id="ddb11-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="ddb11-103">Belirtilen alan geçerlidir statik türünü belirten bir değer alır.</span><span class="sxs-lookup"><span data-stu-id="ddb11-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb11-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ddb11-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddb11-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="ddb11-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ddb11-106">[in] Statik alan tanımlandığı sınıfı kimliği.</span><span class="sxs-lookup"><span data-stu-id="ddb11-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="ddb11-107">[in] Statik alan için meta veri simgesi.</span><span class="sxs-lookup"><span data-stu-id="ddb11-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="ddb11-108">[out] Değerini gösteren bir işaretçi [cor_prf_statıc_type](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) numaralandırma belirten belirtilen alan statik olup ve bu nedenle, statik türü, alan için geçerli olup olmadığını.</span><span class="sxs-lookup"><span data-stu-id="ddb11-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddb11-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ddb11-109">Remarks</span></span>  
 <span data-ttu-id="ddb11-110">Bu bilgiler, statik alan adresini almak için çağırmak için hangi işlevi belirlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ddb11-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="ddb11-111">Profil Oluşturucu kodu hala, aslında bir adresi olduğundan emin olmak için statik bir alan için meta verileri kontrol etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ddb11-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="ddb11-112">Statik değişmez değerleri (diğer bir deyişle, sabitler) yalnızca meta verilerde mevcut ve bir adresi yok.</span><span class="sxs-lookup"><span data-stu-id="ddb11-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddb11-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ddb11-113">Requirements</span></span>  
 <span data-ttu-id="ddb11-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddb11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddb11-115">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ddb11-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ddb11-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddb11-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddb11-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddb11-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb11-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ddb11-118">See Also</span></span>  
 [<span data-ttu-id="ddb11-119">Icorprofilerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="ddb11-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="ddb11-120">Icorprofilerınfo2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="ddb11-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)