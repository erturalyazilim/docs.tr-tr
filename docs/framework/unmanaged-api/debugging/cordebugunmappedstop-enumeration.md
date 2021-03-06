---
title: "CorDebugUnmappedStop Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUnmappedStop
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUnmappedStop
helpviewer_keywords: CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e75c827533a921c4cab31b2e8b0996dffa532fe2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop Numaralandırması
Kod yürütülmesine durdurmak tarafından Adımlayıcı tetikleyebilir eşlenmemiş kod türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`STOP_NONE`|Herhangi bir türde eşlenmemiş kod durdurmaz.|  
|`STOP_PROLOG`|Giriş kodu durdurun.|  
|`STOP_EPILOG`|Bitiş kodu durdurun.|  
|`STOP_NO_MAPPING_INFO`|Eşleme bilgi bulunmaz kodda durdurun.|  
|`STOP_OTHER_UNMAPPED`|Giriş, bitiş, Hayır eşleme bilgilerini veya yönetilmeyen kategori uymuyor eşlenmemiş kodda durdurun.|  
|`STOP_UNMANAGED`|Yönetilmeyen kod içinde durdurun. Bu değer yalnızca birlikte çalışma hata ayıklamaya geçerli değil.|  
|`STOP_ALL`|İçindeki tüm türler eşlenmemiş kod durdurun.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [ICorDebugStepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Adımlayıcı durduracak eşlenmemiş kod belirten bayrakları ayarlamak için yöntem.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama numaralandırmaları](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
