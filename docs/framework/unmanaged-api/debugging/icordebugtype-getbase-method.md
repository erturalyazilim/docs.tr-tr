---
title: ICorDebugType::GetBase Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de00e519b43d486e70d5ed8165eed01b59d6e725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase Metodu
Arabirim işaretçisi, bu tarafından temsil edilen türü varsa temel türünü temsil eden bir Icordebugtype alır `ICorDebugType`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pBase`  
 [out] Adresine bir işaretçi bir `ICorDebugType` temel türünü temsil eden nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tür için temel tür bakarak, tüm alanları bir nesne ya da üst yazdırma gibi ortak hata ayıklayıcı işlevlerini uygulamak yararlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
