---
title: ".NET Framework 4 ve 4.5'e Eklenen CLR Barındırma Arabirimleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65d80734bfbe16c8b5052f8de1e4c6280b663707
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>.NET Framework 4 ve 4.5'e Eklenen CLR Barındırma Arabirimleri
Bu bölümde yönetilmeyen arabirimler açıklanmaktadır konakları ortak dil çalışma zamanı (CLR) içinde tümleştirmek için kullanabilir [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]ve sonraki sürümlerinde uygulamalarına. Bu arabirimleri yapılandırmak ve süreç içine çalışma zamanı yükleme bir konak için yöntemleri sağlar.  
  
 İle başlayarak [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], tüm barındırma arabirimleri aşağıdaki özelliklere sahiptir:  
  
-   Ömür yönetimini kullanın (`AddRef` ve `Release`), kapsülleme (örtük bağlamı) ve `QueryInterface` com gelen  
  
-   COM türleri gibi var. kullanmayın `BSTR`, `SAFEARRAY`, veya `VARIANT`.  
  
-   Hiçbir grup modelleri, toplama veya kayıt defteri etkinleştirme kullanan vardır [CoCreateInstance işlevi](http://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Iclrappdomainresourcemonitor arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Bir uygulama etki alanının bellek ve CPU kullanımını denetleme yöntemleri sağlar.  
  
 [Iclrdomainmanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Varsayılan uygulama etki alanı başlatın ve başlatma özelliklerini belirtmek için kullanılan uygulama etki alanı yöneticisi belirtmek ana bilgisayarı sağlar.  
  
 [Iclrgcmanager2 arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Sağlar [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) atık toplama kesim boyutunu ve en büyük boyutu 0 atık toplama sistemin nesil değerlere büyük ayarlamak bir konak etkinleştirir yöntemi `DWORD`.  
  
 [Iclrmetahost arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 CLR belirli bir sürümünü döndürür, tüm yüklü CLRs listesinde, tüm işlem çalışma zamanları listesinde, etkinleştirme arabirimini döndürür ve bir derlemeyi derlemek için kullanılan CLR sürümünü bulma yöntemleri sağlar.  
  
 [Iclrmetahostpolicy arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Sağlar [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) bir CLR arabirim sağlayan yöntemine temel İlkesi ölçütlerini, yönetilen derleme, sürüm ve yapılandırma dosyası.  
  
 [Iclrruntimeınfo arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Sürüm, dizin ve yük durumu da dahil olmak üzere belirli bir çalışma zamanı hakkında bilgi döndürmek yöntemleri sağlar.  
  
 [Iclrstrongname arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Derlemeleri tanımlayıcı adlar ile imzalama için temel genel statik işlevleri sağlar. Tüm [Iclrstrongname](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) yöntemleri standart COM HRESULTs döndürür.  
  
 [Iclrstrongname2 arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Tanımlayıcı adlar SHA-2 grubunu güvenli karma algoritması (SHA-256, SHA-384 ve SHA-512) kullanarak oluşturmanıza olanak sağlar.  
  
 [Iclrtask2 arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Tüm işlevselliğini sağlar [Iclrtask arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Ayrıca, iş parçacığı iptalleri geçerli iş parçacığı üzerinde Gecikmeli için izin yöntemleri sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kullanım dışı CLR barındırma arabirimleri ve coclass'ları](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 .NET Framework sürüm 1.0 ve 1.1 ile sağlanan barındırma arabirimleri açıklar.  
  
 [CLR barındırma arabirimleri](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 .NET Framework sürüm 2.0, 3.0 ve 3.5 ile sağlanan barındırma arabirimleri açıklar.  
  
 [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 .NET Framework'te barındırma tanıtır.
