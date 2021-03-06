---
title: "IHostTask::Alert Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Alert
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf48d3decd071c4c0f483476b885fc023b466f3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskalert-method"></a>IHostTask::Alert Yöntemi
Ana bilgisayar tarafından geçerli temsil görev Uyandırma isteklerini [Ihosttask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) görevi durduruldu şekilde örneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yöntem başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan kilidi kendisine ait değil.|  
|HOST_E_ABANDONED|Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.|  
|E_FAIL|Bilinmeyen yıkıcı bir hata oluştu. Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz. Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 CLR çağrıları `Alert` yöntemi zaman <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> kullanıcı koddan çağrılan veya ne zaman <xref:System.AppDomain> geçerli ilişkili <xref:System.Threading.Thread> kapanır. Arama zaman uyumsuz olarak yapıldığı için konak hemen döndürmesi gerekir. Ana bilgisayar görev hemen uyarı olamaz, sonraki zaman içinde uyarı onu almak bir duruma girdiği Uyandırma gerekir.  
  
> [!NOTE]
>  `Alert`çalışma zamanı geçtikten görevleri etkiler bir [waıt_optıon](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) gibi yöntemler WAIT_ALERTABLE değerine [katılma](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iclrtask arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Iclrtaskmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Ihosttask arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Ihosttaskmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
