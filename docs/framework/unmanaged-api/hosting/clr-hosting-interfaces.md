---
title: "CLR Barındırma Arabirimleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="50086-102">CLR Barındırma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="50086-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="50086-103">Bu bölümde yönetilmeyen arabirimler açıklanmaktadır konakları ortak dil çalışma zamanı (CLR) uygulamalarına tümleştirmeleri için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="50086-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="50086-104">Bilgi, .NET Framework sürüm 2.0 ve sonraki sürümler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="50086-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="50086-105">Bu arabirimleri çalışma zamanı 1.0 ve 1.1 sürümleri içinde mümkün olandan çok daha fazla yönlerini denetlemek konak etkinleştirin ve CLR ve ana bilgisayarın yürütme modeli arasında çok sıkı tümleştirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="50086-106">.NET Framework sürüm 1.0 ve 1.1'da, barındırma model CLR belirli ayarları yapılandırmak ve olay bildirimlerini almak için bir işlem yüklemek yönetilmeyen bir ana bilgisayar etkin.</span><span class="sxs-lookup"><span data-stu-id="50086-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="50086-107">Ancak, genel olarak, konak ve CLR bağımsız olarak bu işleminde çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="50086-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="50086-108">.NET Framework sürüm 2.0 ve sonraki sürümler soyutlama yeni katmanları Win32 derlemesindeki türler tarafından şu anda sağlanan kaynakların çoğunu sağlar ve ana bilgisayar yapılandırabilirsiniz işlevler kümesini genişletmek konak olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="50086-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50086-109">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="50086-109">In This Section</span></span>  
 [<span data-ttu-id="50086-110">Iactiononclrevent arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="50086-111">Kayıtlı bir olay için bir geri çağırma gerçekleştiren bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="50086-112">Iapartmentcallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="50086-113">Geri aramalar bir grup içinde sağlama yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="50086-114">Iappdomainbinding arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="50086-115">Çalışma zamanı yapılandırma ayarlaması için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="50086-116">Icatalogservices arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="50086-117">Hizmetleri Katalog için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="50086-118">(Bu arabirim .NET Framework altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.)</span><span class="sxs-lookup"><span data-stu-id="50086-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="50086-119">Iclrassemblyıdentitymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="50086-120">CLR derlemeleri hakkında ile konak arasındaki iletişimi destekleyen yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="50086-121">Iclrassemblyreferencelist arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="50086-122">CLR tarafından ve ana bilgisayar tarafından yüklenen bir derleme listesi yönetir.</span><span class="sxs-lookup"><span data-stu-id="50086-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="50086-123">Iclrcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="50086-124">Erişim ve çeşitli yönlerini, CLR yapılandırmak ana bilgisayar için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="50086-125">Iclrdebugmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="50086-126">Bir dizi görevi bir tanımlayıcı ve kolay bir ad ile ilişkilendirmek bir konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="50086-127">Iclrerrorreportingmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="50086-128">Hata bildirimi için özel yığın dökümleri yapılandırmak konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="50086-129">Iclrgcmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="50086-130">CLR'ın çöp toplama sistemi ile etkileşim kurmak bir konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="50086-131">Iclrhostbindingpolicymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="50086-132">Değerlendirmek ve derlemeler için ilke bilgilerini değişiklikleri iletişim kurmak ana bilgisayar için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="50086-133">Iclrhostprotectionmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="50086-134">Yönetilen sınıflar, yöntemler, özellikler ve kısmen güvenilen kodu çalıştırma alanların engellemek ana bilgisayarı sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="50086-135">Iclrıocompletionmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="50086-136">Belirtilen g/ç isteklerin durumunu CLR bilgilendirmek için ana sağlayan bir geri çağırma yöntemi uygular.</span><span class="sxs-lookup"><span data-stu-id="50086-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="50086-137">Iclrmemorynotificationcallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="50086-138">Win32 için benzer bir yaklaşım kullanarak rapor bellek baskısı koşullarını konağa etkinleştirir `CreateMemoryResourceNotification` işlevi.</span><span class="sxs-lookup"><span data-stu-id="50086-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="50086-139">Iclroneventmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="50086-140">Kaydolun ve CLR olayları için geri çağırmaları kaydı için ana sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="50086-141">Iclrpolicymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="50086-142">İlke hataları ve zaman aşımları durumunda gerçekleştirilecek eylemleri belirtmek için ana sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="50086-143">Iclrprobingassemblyenum arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="50086-144">Oluşturma veya kimliğe anlamak zorunda kalmadan CLR için iç derlemenin kimlik bilgilerini kullanarak bir derleme yoklama kimliklerini almak konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="50086-145">Iclrreferenceassemblyenum arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="50086-146">Bir dosya veya CLR için iç oluşturun veya bu kimlikleri anlamak zorunda kalmadan derleme kimlik verilerini kullanarak akış tarafından başvurulan derlemeler kümesini işlemek için ana sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="50086-147">Iclrruntimehost arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="50086-148">Benzer özellikleri sağlayan [Icorruntimehost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), ana bilgisayar denetim arabirimi ayarlamak için ek bir yöntem ile.</span><span class="sxs-lookup"><span data-stu-id="50086-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="50086-149">Iclrsyncmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="50086-150">Kilitlenmeler, eşitleme uygulamasında algılamak için ve istenen görevler hakkında bilgi almak için ana bilgisayar için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="50086-151">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="50086-152">Ana bilgisayar CLR isteklerde veya CLR ilişkili görevle ilgili bildirim sağlamak için sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="50086-153">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="50086-154">CLR yeni bir görev oluşturma, şu anda yürütülen görev almak ve coğrafi dil ve kültür görev için ayarlanmış istemenin konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="50086-155">Iclrvalidator arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="50086-156">Taşınabilir yürütülebilir (PE) görüntüler doğrulama ve doğrulama hatalarını raporlama için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="50086-157">Icorconfiguration arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="50086-158">CLR yapılandırmak için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="50086-159">Icorthreadpool arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="50086-160">İş parçacığı havuzu erişmek için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="50086-161">Idebuggerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="50086-162">Hata ayıklama hizmetlerinin durumu hakkında bilgi almak için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="50086-163">Idebuggerthreadcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="50086-164">Engelleme hakkında konak bildirme ve hata ayıklama Hizmetleri tarafından iş parçacıklarının kaldırma için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="50086-165">Igchost arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="50086-166">Çöp toplama sistemi hakkında bilgi edinme ve atık toplama bazı yönlerini denetleme yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="50086-167">Igchost2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="50086-168">Sağlar [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) atık toplama kesim boyutunu ve en büyük boyutu sıfır atık toplama sistemin nesil değerlere büyük ayarlamak bir konak etkinleştirir yöntemi `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="50086-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="50086-169">Igchostcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="50086-170">Sanal bellek sınırları değiştirmek için ana istemek atık toplayıcı sağlayan bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="50086-171">Igcthreadcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="50086-172">Çöp toplama için engellenmesi iş parçacıklarını zamanlama içinde katılan için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="50086-173">Ihostassemblymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="50086-174">CLR veya ana bilgisayar tarafından yüklenmesi gereken derlemeler kümesini belirtmek bir konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="50086-175">Ihostassemblystore arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="50086-176">Derlemeler ve modüller CLR bağımsız olarak yüklemek bir konak sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="50086-177">Ihostautoevent arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="50086-178">Ana bilgisayar tarafından uygulanan bir otomatik sıfırlama olay gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="50086-179">Ihostcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="50086-180">Derlemeleri yükleme yapılandırma ve ana bilgisayar destekler hangi barındırma arabirimleri belirlemek için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="50086-181">Ihostcrst arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="50086-182">İş parçacığı oluşturma için önemli bir bölümü ana bilgisayarın gösterimi olarak görev yapar.</span><span class="sxs-lookup"><span data-stu-id="50086-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="50086-183">Ihostgcmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="50086-184">CLR tarafından uygulanan atık toplama mekanizması olayları ana bildir yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="50086-185">Ihostıocompletionmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="50086-186">Ana bilgisayar tarafından sağlanan g/ç tamamlama bağlantı noktaları ile etkileşim kurmak CLR sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="50086-187">Ihostmalloc arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="50086-188">Ana bilgisayar üzerinden öbek hassas ayırmaları istemesini CLR için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="50086-189">Ihostmanualevent arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="50086-190">Ana bilgisayarın uygulamasını elle sıfırlama olayı bir gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="50086-191">Ihostmemorymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="50086-192">Standart Win32 sanal bellek işlevleri kullanmak yerine ana bilgisayar üzerinden sanal bellek istekler yapmasını CLR için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="50086-193">Ihostpolicymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="50086-194">Durumunda, CLR gerçekleştirdiği işlemleri ana durdurur, zaman aşımı veya hatalar bildiren yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="50086-195">Ihostsecuritycontext arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="50086-196">Ana bilgisayar tarafından uygulanan güvenlik bağlamı bilgilerini korumak CLR sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="50086-197">Ihostsecuritymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="50086-198">Erişimi etkinleştir ve şu anda yürütülen iş parçacığı güvenlik bağlamı, üzerinde denetleyen yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="50086-199">Ihostsemaphore arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="50086-200">Ana bilgisayar tarafından uygulanan semafor gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="50086-201">Ihostsyncmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="50086-202">Eşitleme temelleri Win32 eşitleme işlevlerini kullanmak yerine ana çağırarak oluşturmak CLR için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="50086-203">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="50086-204">Görevleri yönetmek için konak ile iletişim kurmak CLR sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="50086-205">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="50086-206">Görevler için standart işletim sistemi iş parçacığı oluşturma veya fiber işlevlerini yerine ana bilgisayar üzerinden çalışmak CLR sağlayan yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="50086-207">Ihostthreadpoolmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="50086-208">İş parçacığı havuzu yapılandırmak için ve iş parçacığı havuzu iş öğelerine kuyruğuna CLR için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="50086-209">IManagedObject arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="50086-210">Yönetilen bir nesnenin denetleme yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="50086-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="50086-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="50086-212">Yöneltme açma sıralama değerli nesneleri için bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="50086-213">Itypename arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="50086-214">Tür adı bilgilerini alma yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="50086-215">(Bu arabirim .NET Framework altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.)</span><span class="sxs-lookup"><span data-stu-id="50086-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="50086-216">Itypenamebuilder arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="50086-217">Tür adı oluşturmak için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-217">Provides methods for building a type name.</span></span> <span data-ttu-id="50086-218">(Bu arabirim .NET Framework altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.)</span><span class="sxs-lookup"><span data-stu-id="50086-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="50086-219">Itypenamefactory arabirimi</span><span class="sxs-lookup"><span data-stu-id="50086-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="50086-220">Tür adı deconstructing için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="50086-221">(Bu arabirim .NET Framework altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.)</span><span class="sxs-lookup"><span data-stu-id="50086-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="50086-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="50086-222">"IValidator"</span></span>  
 <span data-ttu-id="50086-223">Taşınabilir yürütülebilir (PE) görüntüler doğrulama ve doğrulama hatalarını raporlama için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="50086-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50086-224">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="50086-224">Related Sections</span></span>  
 [<span data-ttu-id="50086-225">Kullanım dışı CLR barındırma arabirimleri ve coclass'ları</span><span class="sxs-lookup"><span data-stu-id="50086-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="50086-226">.NET Framework sürüm 1.0 ve 1.1 sağlanan barındırma arabirimleri açıklayan konuları içerir.</span><span class="sxs-lookup"><span data-stu-id="50086-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="50086-227">.NET Framework 4 ve 4.5 eklenen CLR barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="50086-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="50086-228">Sağlanan barındırma arabirimleri açıklayan konulara içeren [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50086-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>