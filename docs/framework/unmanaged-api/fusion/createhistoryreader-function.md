---
title: "CreateHistoryReader İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader İşlevi
Belirtilen dosya için bir geçmiş okuyucu oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `wzFilePath`  
 [in] Dosya yolu.  
  
 `ppHistoryReader`  
 [out] Başarılı tamamlanma, geçmiş Okuyucu için bir işaretçi içeriyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem, ek olarak aşağıdaki tabloda açıklanan değerleri Winerror.h'de içinde tanımlanan standart COM hata kodlarını döndürür.  
  
|Dönüş kodu|Açıklama|  
|-----------------|-----------------|  
|S_OK|Yöntem başarıyla tamamlanıp tamamlanmadığını gösterir.|  
|E_INVALIDARG|Belirten `wzFilePath` veya `ppHistoryReader` null bir başvuru ayarlayın.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kitaplığı:** Fusion.dll  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Fusion genel statik işlevleri](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
