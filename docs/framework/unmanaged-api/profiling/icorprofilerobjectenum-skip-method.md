---
title: "ICorProfilerObjectEnum::Skip Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 84960af6e128f3a6aa9e3b45187e282ac7228e0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumskip-method"></a>ICorProfilerObjectEnum::Skip Yöntemi
Böylece belirtilen sayıda öğeyi atlanır imleci bu Numaralayıcı geçerli konumundan ilerler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Atlanan öğe sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu Numaralandırıcının imleç yeni konumu: (geçerli konumu) + `celt` .  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icorprofilerobjectenum arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
