---
title: "ICorDebugManagedCallback2::ChangeConnection Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="85df1-102">ICorDebugManagedCallback2::ChangeConnection Yöntemi</span><span class="sxs-lookup"><span data-stu-id="85df1-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="85df1-103">Hata ayıklayıcı belirtilen bağlantı ile ilişkili görevlerin değiştiğini bildirir.</span><span class="sxs-lookup"><span data-stu-id="85df1-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85df1-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="85df1-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85df1-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="85df1-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="85df1-106">[in] Değiştirilen bağlantıyı içeren işlemi temsil eden bir "ICorDebugProcess" nesnesi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="85df1-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="85df1-107">[in] Değiştirilen bağlantının kimliği.</span><span class="sxs-lookup"><span data-stu-id="85df1-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85df1-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85df1-108">Remarks</span></span>  
 <span data-ttu-id="85df1-109">A `ChangeConnection` geri çağırma harekete aşağıdaki durumlarda birini:</span><span class="sxs-lookup"><span data-stu-id="85df1-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="85df1-110">Ne zaman bir hata ayıklayıcı bağlantıları içeren bir işlem ekler.</span><span class="sxs-lookup"><span data-stu-id="85df1-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="85df1-111">Çalışma zamanı bu durumda, oluştur ve Dağıt bir [Icordebugmanagedcallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) olay ve `ChangeConnection` işlemdeki her bağlantı için olay.</span><span class="sxs-lookup"><span data-stu-id="85df1-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="85df1-112">A `ChangeConnection` olay görevler bu bağlantının kümesi oluşturulduktan sonra değiştirildi bağımsız olarak her var olan bağlantısı için oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="85df1-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="85df1-113">Bir konak çağırdığında [Iclrdebugmanager::setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) içinde [barındırma API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="85df1-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="85df1-114">Hata ayıklayıcı yeni değişiklikleri almak için işlemdeki tüm iş parçacıklarını taramalısınız.</span><span class="sxs-lookup"><span data-stu-id="85df1-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85df1-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="85df1-115">Requirements</span></span>  
 <span data-ttu-id="85df1-116">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85df1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85df1-117">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85df1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85df1-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85df1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85df1-119">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85df1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85df1-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85df1-120">See Also</span></span>  
 [<span data-ttu-id="85df1-121">Icordebugmanagedcallback2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="85df1-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="85df1-122">Icordebugmanagedcallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="85df1-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)