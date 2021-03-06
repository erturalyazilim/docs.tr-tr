---
title: "ICorDebugController::EnumerateThreads Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.EnumerateThreads
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7575bf2b50f11fab1c14f8fb28dc65e079c21de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads Yöntemi
Bir numaralandırıcı etkin yönetilen iş parçacığı için işlem sırasında alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppThreads`  
 [out] Bir işaretçi adresine "ICorDebugThreadEnum" nesnenin işlemde etkin olan tüm yönetilen iş parçacığı için bir numaralandırıcı temsil eder.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir iş parçacığı sonra etkin olarak kabul [Icordebugmanagedcallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) geri çağırma gönderilir ve önce [Icordebugmanagedcallback::exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) geri çağırma gönderilir . Yönetilen iş parçacığı mutlaka herhangi bir yönetilen çerçeve kendi yığına sahip olmayabilir. İş parçacığı numaralandırılan bile önce [Icordebugmanagedcallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) geri çağırma. Numaralandırma doğal olarak boş olur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
