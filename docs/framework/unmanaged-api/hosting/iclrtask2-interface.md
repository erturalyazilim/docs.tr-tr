---
title: ICLRTask2 Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a>ICLRTask2 Arabirimi
Tüm işlevselliğini sağlar [Iclrtask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) arabirim; Ayrıca, iş parçacığı iptalleri geçerli iş parçacığı üzerinde Gecikmeli için izin yöntemleri sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[BeginPreventAsyncAbort yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Yeni bir iş parçacığı gecikmeler geçerli iş parçacığının isteklerinde durdur.|  
|[EndPreventAsyncAbort yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Yeni izin verir veya bekleyen iş parçacığı elde etmek iş parçacığı durdurma isteği geçerli iş parçacığı üzerinde durdurur.|  
  
## <a name="remarks"></a>Açıklamalar  
 `ICLRTask2` Arabirimi devralır `ICLRTask` arabirim ve bir bölge başarısız gerekir kodu korumak için iş parçacığı iptalleri gecikme konağının yöntemleri ekler. Çağırma `BeginPreventAsyncAbort` geçerli iş parçacığının ve arama için gecikme iş parçacığı iptal sayaç artırılır `EndPreventAsyncAbort` azaltır. Çağrılar `BeginPreventAsyncAbort` ve `EndPreventAsyncAbort` iç içe olamaz. Sayaç sıfırdan büyük olduğu sürece, geçerli iş parçacığı için iş parçacığı iptalleri gecikir.  
  
 Varsa çağrılar `BeginPreventAsyncAbort` ve `EndPreventAsyncAbort` olan eşleştirilmiş değil, hangi iş parçacığı iptalleri olamaz teslim edilemiyor geçerli iş parçacığına durumuna ulaşması mümkündür.  
  
 Gecikme kendisini durdurur bir iş parçacığı için dikkate alınır değil.  
  
 Bu özellik tarafından sunulan işlevselliği sanal makine (VM) tarafından dahili olarak kullanılır. Bu yöntemlerin kötüye VM'yi belirtilmeyen davranışlara neden olabilir. Örneğin, arama `EndPreventAsyncAbort` ilk çağırmadan `BeginPreventAsyncAbort` VM daha önce onu artar olduğunda Sayaç sıfıra ayarlanamıyor. Benzer şekilde, iç sayaç için taşma işaretlenmemiştir. Konak ve VM tarafından artırılır çünkü tam sayı sınırını aşarsa, bunun sonucunda oluşan davranışı belirtilmemiş.  
  
 Devralınan üyeleri hakkında bilgi için `ICLRTask` ve diğer kullanımlar bu arabirimin hakkında bkz: [Iclrtask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iclrtask arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Iclrtaskmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Ihosttask arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Ihosttaskmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Barındırma arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
