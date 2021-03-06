---
title: "GetTypeLibInfo İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetTypeLibInfo
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: GetTypeLibInfo
helpviewer_keywords: GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5dc55a9538798b81dce9db02583c271b9f2ed54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo İşlevi
Belirtilen tür kitaplığı hakkında bilgi inceleyerek döndürür, [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szFile`  
 [in] Tür kitaplığı dosya adı.  
  
 `pTypeLibID`  
 [out] Tür kitaplığı GUID.  
  
 `pTypeLibLCID`  
 [out] Tür kitaplığı yerelleştirme kimliği.  
  
 `pTypeLibPlatform`  
 [out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) tür kitaplığı için hedef işletim sistemini tanımlayan bayrağı. SYS_WIN32 ve SYS_WIN64 bunun ortak değerlerdir.  
  
 `pTypeLibMajorVer`  
 [out] Tür kitaplığı ana sürüm numarası. Örneğin, sürüm *x.y*, ana sürüm numarası *x*.  
  
 `pTypeLibMinorVer`  
 [out] Tür kitaplığı ikincil sürüm numarası. Örneğin, sürüm *x.y*, ikincil sürüm numarası *y*.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetTypeLibInfo` İşlevi çağrıldığında [Tlbexp.exe (tür kitaplığı dışarı Aktarıcı)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Bu araç, bir ortak dil çalışma zamanı (CLR) derlemesindeki türler açıklayan bir tür kitaplığı oluşturur.  
  
 Herhangi bir parametre null ise işlev verir bir `HRESULT` , `E_POINTER`. Aksi takdirde, döndürür `S_OK`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** TlbRef.h  
  
 **Kitaplığı:** TlbRef.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tlbexp yardımcı işlevleri](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx işlevi](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
