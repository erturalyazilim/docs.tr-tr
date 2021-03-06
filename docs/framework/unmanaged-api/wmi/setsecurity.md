---
title: "SetSecurity işlevi (yönetilmeyen API Başvurusu)"
description: "SetSecurity işlevi geçerli iş parçacığının kimliğe bürünme belirtecini alır."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SetSecurity
helpviewer_keywords: SetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fd7ccb0cfb25773da7e489f9ce4d6332b80a616
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="setsecurity-function"></a>SetSecurity işlevi
Geçerli iş parçacığı ile ilişkili kimliğe bürünme belirtecini alır.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a>Parametreler

`pNeedToReset`[out] İşlevi döndüğünde gösteren bir işaretçi içeren bir `boolean` belirten belirteç çağırarak sıfırlayıp sıfırlayamayacağını [ResetSecurity](resetsecurity.md) işlevi.  

`token`  
[out] İşlevi döndüğünde, geçerli iş parçacığı ile ilişkili kimliğe bürünme belirtecini işlemek için bir işaretçi içeriyor. Değerini olabilir `null` geçerli iş parçacığı ile ilişkili herhangi bir belirteci olup olmadığını. 

## <a name="return-value"></a>Dönüş değeri

İşlev başarılı olursa, dönüş değeri olan `S_OK` (0).

İşlev başarısız olursa, dönüş değeri sıfır olmayan bir hata kodudur. Genişletilmiş hata bilgilerini için arama [Geterrorınfo](geterrorinfo.md) işlevi.
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
