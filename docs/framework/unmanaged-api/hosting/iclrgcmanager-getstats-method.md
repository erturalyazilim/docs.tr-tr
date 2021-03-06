---
title: ICLRGCManager::GetStats Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06d52bd0348e4667f1e3ec43a371021922f12ded
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagergetstats-method"></a>ICLRGCManager::GetStats Metodu
Ortak dil çalışma zamanı 's çöp toplama sistemi hakkında geçerli istatistiklerini kümesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStats`  
 [içinde out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) istenen istatistikleri içeren örneği.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|`GetStats`başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan kilidi kendisine ait değil.|  
|HOST_E_ABANDONED|Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.|  
|E_FAIL|Bilinmeyen yıkıcı bir hata oluştu. CLR, artık bir yöntem E_FAIL döndükten sonra işlemi içinde kullanılamaz. Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 CLR hesaplar ve tarafından belirtilen istatistikleri döndürür `Flags` alanını `pStats`.  
  
 Ayarlama `Flags` bir veya daha fazla değerleri alan [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) hangi istatistiklerini belirtmek için numaralandırma [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) yapısı olan ayarlanacak.  
  
 Kullanım örneği aşağıdaki gibidir:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik bellek yönetimi](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS yapısı](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [COR_GC_STAT_TYPES numaralandırması](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [Çöp toplama](../../../../docs/standard/garbage-collection/index.md)  
 [Iclrcontrol arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Iclrgcmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [CLR barındırma arabirimleri](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Barındırma arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)
