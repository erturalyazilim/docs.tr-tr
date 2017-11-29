---
title: ICorProfilerInfo3::GetFunctionEnter3Info Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a75f76af924c3e75d280c36fb5f436498dc6c862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="bec87-102">ICorProfilerInfo3::GetFunctionEnter3Info Metodu</span><span class="sxs-lookup"><span data-stu-id="bec87-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="bec87-103">Profil Oluşturucu tarafından için bildirilen işlevi yığın çerçevesi ve bağımsız değişkeni bilgi verilmektedir [Functionenter3withınfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="bec87-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="bec87-104">Bu yöntem yalnızca sırasında çağrılabilir `FunctionEnter3WithInfo` geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="bec87-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec87-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bec87-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bec87-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="bec87-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="bec87-107">[in] `FunctionID` Giriliyor işlevi.</span><span class="sxs-lookup"><span data-stu-id="bec87-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="bec87-108">[in] Verilen yığın çerçevesi ilgili bilgileri temsil eder donuk işleci.</span><span class="sxs-lookup"><span data-stu-id="bec87-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="bec87-109">Profil Oluşturucu aynı sağlamalıdır `eltInfo` tarafından verilen [Functionenter3withınfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="bec87-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="bec87-110">[out] Verilen yığın çerçevesi genel türler bilgilerini temsil eden bir donuk tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="bec87-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="bec87-111">Bu işleme yalnızca sırasında geçerli `FunctionEnter3WithInfo` profil oluşturucu çağırıldığı geri çağırma `GetFunctionEnter3Info` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="bec87-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="bec87-112">[içinde out] Bayt olarak toplam boyutu için bir işaretçi, [cor_prf_functıon_argument_ınfo](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) yapısı (artı ek [cor_prf_functıon_argument_range](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) tarafındanişaretbağımsızdeğişkeniaralıklarıiçinyapıları`pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="bec87-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="bec87-113">Belirtilen boyut yeterli değildir, ERROR_INSUFFICIENT_BUFFER döndürülür ve beklenen boyutu depolanan `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="bec87-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="bec87-114">Çağrılacak `GetFunctionEnter3Info` yalnızca için beklenen değer almak için `*pcbArgumentInfo`ayarlayın `*pcbArgumentInfo`= 0 ve `pArgumentInfo`= NULL.</span><span class="sxs-lookup"><span data-stu-id="bec87-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="bec87-115">[out] Bir işaretçi bir [cor_prf_functıon_argument_ınfo](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) işlev bağımsız değişkenleri soldan sağa sırayla bellekte konumlarını tanımlayan yapısı.</span><span class="sxs-lookup"><span data-stu-id="bec87-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bec87-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bec87-116">Remarks</span></span>  
 <span data-ttu-id="bec87-117">Profil Oluşturucu için yeterli alanı ayırmalısınız `COR_PRF_FUNCTION_ARGUMENT_INFO` Denetlenmekte olan ve boyutu belirtmelidir işlev yapısını `pcbArgumentInfo` parametresi.</span><span class="sxs-lookup"><span data-stu-id="bec87-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec87-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="bec87-118">Requirements</span></span>  
 <span data-ttu-id="bec87-119">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bec87-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec87-120">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bec87-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bec87-121">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bec87-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bec87-122">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec87-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec87-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bec87-123">See Also</span></span>  
 [<span data-ttu-id="bec87-124">Functionenter3withınfo</span><span class="sxs-lookup"><span data-stu-id="bec87-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="bec87-125">Functionleave3withınfo</span><span class="sxs-lookup"><span data-stu-id="bec87-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="bec87-126">Functiontailcall3withınfo</span><span class="sxs-lookup"><span data-stu-id="bec87-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="bec87-127">Icorprofilerınfo3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="bec87-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="bec87-128">Profil oluşturma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="bec87-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="bec87-129">Profil oluşturma</span><span class="sxs-lookup"><span data-stu-id="bec87-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)