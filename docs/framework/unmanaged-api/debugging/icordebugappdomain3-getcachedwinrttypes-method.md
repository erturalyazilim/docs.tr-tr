---
title: ICorDebugAppDomain3::GetCachedWinRTTypes Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3.GetCachedWinRTTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb41b278b21b2289c7f5a7164a1bd01bc39423b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypes Metodu
Tüm önbelleğe alınmış bir numaralandırıcı alır [!INCLUDE[wrt](../../../../includes/wrt-md.md)] türleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppGuidToTypeEnum`  
 [out] Bir işaretçi bir [Icordebugguidtotypeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) yönetilen gösterimlerini numaralandırabilir arabirimi nesnesi [!INCLUDE[wrt](../../../../includes/wrt-md.md)] türleri uygulama etki alanında şu anda yüklü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icordebugappdomain3 arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
