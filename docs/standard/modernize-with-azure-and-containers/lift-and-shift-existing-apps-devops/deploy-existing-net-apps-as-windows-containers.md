---
title: "Windows kapsayıcılar olarak var olan .NET uygulamalarını dağıtma"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Windows kapsayıcılar olarak var olan .NET uygulamalarını dağıtma"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 87aa05895857a425f11820a564f2a249c77f98e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Windows kapsayıcılar olarak var olan .NET uygulamalarını dağıtma

Windows kapsayıcılarında tabanlı dağıtımlar, bulut için iyileştirilmiş uygulamaları, bulut yerel uygulamaları ve bulut DevOps çapında kullanılmaya hazır uygulamalar için geçerlidir.

Bu kılavuzdaki ve aşağıdaki bölümlerde Windows kapsayıcıları için kullanarak odaklanmak *buluta DevOps hazır* kaldırın ve mevcut .NET uygulamaları shift uygulamalar.

## <a name="what-are-containers-linux-or-windows"></a>Kapsayıcıları nelerdir? (Linux veya Windows)

Kapsayıcılar kendi yalıtılmış paketi bir uygulamaya sarmalamak için bir yoldur. Kendi kapsayıcısında uygulamalar veya dışında kapsayıcı mevcut işlemler uygulama etkilenmez. Bir işlem içinde kapsayıcıdır gibi her şeyi uygulama Çalıştır açın başarıyla bağlıdır. Yerde kapsayıcıyı taşıma (kitaplık bağımlılıkları, çalışma zamanları ve benzeri) çalıştırmak için gereken her şeyi ile getirilme çünkü uygulamanın gereksinimlerini her zaman, doğrudan bağımlılıklarını bakımından karşılanması.

Ana bir kapsayıcı kapsayıcı, gereken tüm bağımlılıkları ile geldiğinden ortamı aynı farklı dağıtımlar arasında kolaylaştırır, özelliğidir. Bu uygulamayı makinenizde hata ayıklama ve ardından garanti ortamıyla başka bir makineye dağıtma anlamına gelir.

Bir kapsayıcı, bir kapsayıcı görüntüsü örneğidir. Bir kapsayıcı görüntüsü, bir uygulama ya da (snapshot gibi) hizmet paketini ve güvenilir ve tekrarlanabilir bir şekilde dağıtmak için bir yoldur. Docker bir felsefesi ve bir işlemi yalnızca bir teknoloji-BT ayrıca kullanıcının olmadığını diyebilirsiniz.

Kapsayıcıları günlük daha yaygın hale geldikçe bir sektör çapında "dağıtım birimidir." gelmektedir

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Kapsayıcılar (Linux veya Windows Docker altyapısı) yararları

Kapsayıcılar ve kullanarak uygulamaları derleme de olabilir basit yapı taşları teklifleri oluşturmak, sevkiyat ve herhangi bir uygulama arasında herhangi bir altyapı çalıştırmak çeviklik önemli bir artış tanımlanmış.

İle kapsayıcıları, tüm uygulamaları geliştirme için üretim çok az kayıpla veya hiç kod değişikliği, Microsoft Geliştirici Araçları, işletim sistemleri ve bulut arasında Docker tümleştirmesi sayesinde ile alabilir.

Düz VM'ler dağıttığınızda, büyük olasılıkla zaten bir yöntem Vm'leriniz için ASP.NET uygulamalarını dağıtmak için yerinde vardır. Ancak, yönteminizi birden çok adımları el ile veya karmaşık otomatik işlemleri Puppet gibi bir dağıtım araç veya benzer bir aracı kullanarak içerdiğini, olasıdır. Yapılandırma öğeleri değiştirerek, uygulama içeriği sunucular arasında kopyalama ve test ederek ve ardından .msi kurulumları dayalı etkileşimli kurulum programları çalıştırmak gibi görevleri gerçekleştirmeniz gerekebilir. Dağıtımdaki tüm adımları dağıtımları için saat ve risk ekleyin. Hedef ortamda bir bağımlılık yok olduğunda hataları alırsınız.

Windows kapsayıcılarında uygulama Paketleme işlemini tamamen otomatik hale getirilmiştir. Windows kapsayıcıları otomatik güncelleştirmeler ve kapsayıcı dağıtımlarını düzeyine sunar Docker platform temel alır. Docker altyapısına kullanarak alma ana geliştirme tüm bağımlılıkları ile uygulamanızı anlık görüntüleri gibi olan görüntüleri oluşturacağı açıklanmaktadır. Görüntüleri Docker görüntüleri (bir Windows kapsayıcı görüntü, bu durumda) bağımsızdır. Kaynak koduna geçmeden kapsayıcılara ASP.NET uygulamalarını çalıştırmak görüntüler. Kapsayıcı anlık görüntü dağıtımının birim haline gelir.

Kuruluşlar, çok sayıda tek yapılı uygulamalarınız şu nedenlerden dolayı containerizing:

-   **Yayın geliştirilmiş dağıtım aracılığıyla çevikliği**. Kapsayıcıları geliştirme ve işlemler arasında tutarlı bir dağıtım sözleşme sunar. Kapsayıcıları kullandığınızda, söyleyin geliştiriciler duyduğunuz kalmaz, "Benim makinede neden üretimde çalıştığını?" Bunlar basitçe söyleyin, "üretimde çalıştırılabilmesi, bir kapsayıcı olarak çalışır, böylece." Paketlenen uygulamayı ile tüm bağımlılıkları, desteklenen tüm kapsayıcı tabanlı ortamda çalıştırılabilir. Tüm dağıtım hedefleri (geliştirme, QA, hazırlama, üretim) çalıştırmak için tasarlanmıştır şekilde çalışır. Dağıtım önemli ölçüde iyileştirir, sonraki bir aşamadan diğerine taşıdığınızda kapsayıcıları çoğu frictions ortadan kaldırabilir ve daha hızlı gönderebilirsiniz.

-   **Azaltması maliyet**. Kapsayıcıları, birleştirme ve temizleme mevcut donanım veya donanım birimi başına daha yüksek yoğunluk sırasında çalışan uygulamalar tarafından ya da maliyetlerine yol açar.

-   **Taşınabilirlik**. Modüler ve taşınabilir kapsayıcılardır. Docker kapsayıcıları herhangi bir sunucu işletim sistemi (Linux ve Windows), tüm önemli genel bulut (Microsoft Azure, Amazon AWS, Google, IBM) ve şirket içi ve özel veya karma bulut ortamları için desteklenir.

-   **Denetim**. Kapsayıcılar kapsayıcı düzeyinde denetlenir esnek ve güvenli bir ortam sağlar. Bir kapsayıcı güvenli, yalıtılmış ve hatta yürütme kısıtlama ilkeleri kapsayıcısında ayarlayarak sınırlı. Windows kapsayıcıları hakkında bölümündeki olarak ayrıntılı, Windows Server 2016 ve Hyper-V kapsayıcı ek kurumsal destek seçenekleri sunar.

Kapsayıcıları geliştirmek ve uygulamalarını korumak için kullandığınızda çeviklik, taşınabilirlik ve denetim önemli geliştirmeler sonuçta önemli maliyet azaltması yol açar.

## <a name="what-is-docker"></a>Docker nedir?

[Docker](https://www.docker.com/) olan bir [açık kaynaklı proje](https://github.com/docker/docker) uygulamalarının dağıtımını Bulut veya şirket içi çalıştırabilirsiniz taşınabilir, sünece kapsayıcı olarak otomatikleştirir. Docker da olan bir [şirket](https://www.docker.com/) yükseltir ve bu teknolojisi geliştikçe. Bulut, Linux ve Windows satıcılar, dahil olmak üzere Microsoft ile işbirliğiyle şirket çalışır.

![](./media/image6.png)

> **Şekil 4-6.** Karma bulut tüm katmanlarını adresindeki kapsayıcıları docker dağıtır

Birine sanal makineleri aşina kapsayıcıları çok benzer şekilde görünebilir. Bir kapsayıcı bir işletim sistemi çalıştıran bir dosya sistemine sahip ve bir fiziksel veya sanal bilgisayar sistemi gibi bir ağ üzerinden erişilebilir. Ancak, teknoloji ve kapsayıcıları kavramları sanal makinelerden çok farklı değildir. Bir geliştirici açısından bakıldığında, bir kapsayıcı daha gibi tek bir işlem değerlendirilmesi gerekir. Aslında, kapsayıcı bir işlem için bir tek giriş noktası vardır.

Docker kapsayıcıları (basitleştirmek için *kapsayıcıları*) Linux ve Windows'da yerel olarak çalıştırabilirsiniz. Normal kapsayıcıları çalıştırırken Windows kapsayıcıları yalnızca Windows konaklarda (bir konak sunucusu veya VM) çalıştırabilirsiniz ve Linux kapsayıcılar yalnızca Linux ana bilgisayarlarında çalıştırabilirsiniz. Ancak, Windows Server ve Hyper-V kapsayıcılardaki en güncel sürümlerini Linux kapsayıcı de yerel olarak Windows Server üzerinde şu anda yalnızca Windows Server kapsayıcıları kullanılabilir Hyper-V yalıtım teknolojisini kullanarak çalıştırabilirsiniz.

Yakın gelecekte, Linux ve Windows kapsayıcıları sahip karma ortamlar olası ve hatta ortak olacaktır.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Var olan .NET uygulamalarınız için Windows kapsayıcıların avantajları

Windows kapsayıcıları kullanmanın avantajları temelde kapsayıcılardan genel alma aynı yararlar şunlardır. Windows kapsayıcıları çeviklik, taşınabilirlik ve denetim büyük ölçüde artırmak hakkında kullanmaktır.

Biz varolan .NET uygulamaları hakkında konuşurken biz çoğunlukla .NET Framework kullanılarak oluşturulan geleneksel uygulamaları anlamına gelir. Örneğin, geleneksel ASP.NET web uygulamaları olabilir-daha yeni olan ve platformlar arası çalışan .NET Core kullanmayan Linux, Windows ve MacOS.

.NET Framework'teki ana bağımlılık Windows ' dir. Ayrıca ikincil bağımlılıkları, IIS ve System.Web gibi geleneksel ASP.NET sahiptir.

Bir .NET Framework uygulamasını Windows üzerinde dönemi çalıştırmanız gerekir. Var olan .NET Framework uygulamaları containerize istediğiniz ve veya .NET Core geçiş yatırım yapmak istemiyorsunuz varsa ("düzgün çalışıp çalışmadığını yok geçirmeyi"), sahip olduğunuz için kapsayıcı yalnızca Windows kapsayıcılar kullanmak için bir seçimdir.

Bunlar, Windows aracılığıyla kapsayıcıyla taşıma çalıştıran var olan .NET Framework uygulamalarınızı modernize için bir yol sunar Windows kapsayıcıların ana avantajlarından biri olacak şekilde. Sonuç olarak, Windows kapsayıcıları kapsayıcıları çeviklik, taşınabilirlik ve daha iyi denetim kullanarak aradığınız avantajları alır.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Bir işletim sistemine sahip hedef seçin. NET tabanlı kapsayıcıları

.NET Framework ve .NET Core arasındaki farklar yanı sıra, Docker tarafından desteklenen işletim sistemlerinin seviyelerine verildiğinde, belirli bir işletim sistemi ve kullandığınız framework temel alınarak belirli sürümlerini hedefleyen.

Windows, Windows Server Core veya Windows Nano Server kullanabilirsiniz. Bu Windows sürümlerini .NET Framework veya .NET Core uygulamaları tarafından gerekebilecek farklı özellikleri (örneğin, IIS Kestrel gibi bir kendi kendini barındıran web sunucusu ile karşılaştırması) sağlar.

Linux için kullanılabilir ve desteklenen (Debian gibi) resmi .NET Docker görüntülerinde birden çok distro'lar.

Şekil 4-7, .NET Framework uygulamanın sürümüne bağlı olarak hedefleyebilirsiniz işletim sistemi sürümleri gösterir.

![](./media/image7.png)

> **Şekil 4-7.** .NET Framework sürümü temel hedef işletim sistemleri

.NET Framework uygulamalarını temel var olan veya eski uygulamalar için geçiş senaryolarında ana Windows ve IIS bağımlılıklardır. Tek seçeneğiniz Windows Sunucu Çekirdeği ve .NET Framework tabanlı Docker görüntüler kullanmaktır.

Görüntü adı Dockerfile dosyanızı eklediğinizde, .NET Framework tabanlı Windows kapsayıcı görüntüleri ilişkin aşağıdaki örneklerde olduğu gibi bir etiket kullanarak işletim sistemi ve sürümü seçebilirsiniz:

> | **Etiket** | **Sistemi ve sürümü** |
> |---|---|
> | **Microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x Windows Sunucu Çekirdeği |
> | **aspnet:4.x/Microsoft-windowsservercore** | .NET framework 4.x ile Windows Server Core üzerinde ek ASP.NET özelleştirme |

.NET Core (platformlar arası Linux ve Windows için) etiketleri şöyle olabilir:

> | **Etiket** | **Sistemi ve sürümü**
> |---|---|
> | **Microsoft/dotnet:2.0.0-Runtime** | .NET core 2.0 Linux'ta salt çalışma zamanı |
> | **Microsoft/dotnet:2.0.0-Runtime-nanoserver** | .NET core 2.0 Windows Nano Server salt çalışma zamanı |

### <a name="multi-arch-images"></a>Birden çok yay görüntüleri

Mid-2017 içinde başlayarak, yeni bir özellik olarak adlandırılan Docker içinde kullanabilirsiniz [çok arch](https://github.com/moby/moby/issues/15866) görüntüler. .NET core Docker görüntüleri çok yay etiketlerini kullanabilirsiniz. Dockerfile artık, hedeflediğiniz işletim sistemini tanımlamak için gereksinim dosyaları. Birden çok yay özelliği birden çok makine yapılandırmalarını kullanılacak tek bir etiket sağlar. Örneğin, çok mimarisi ile tek bir ortak etiket kullanabilirsiniz: **microsoft/dotnet:2.0.0-runtime**. Bu etiketi Linux kapsayıcı ortamından çekme, Debian tabanlı görüntü alırsınız. Bir Windows kapsayıcı ortamından metnimizi çekme, Nano Server tabanlı görüntü alırsınız.

Geleneksel .NET Framework yalnızca Windows desteklediğinden, .NET Framework görüntüler için çok yay özelliği kullanamaz.

## <a name="windows-container-types"></a>Windows kapsayıcı türleri

Linux kapsayıcıları gibi Windows Server kapsayıcıları, Docker altyapısına kullanılarak yönetilir. Linux kapsayıcıları aksine Windows kapsayıcıları iki farklı kapsayıcı türler veya kez Windows Server kapsayıcıları ve Hyper-V yalıtım çalıştırın.

**Windows Server kapsayıcıları**: işlem ve ad alanı yalıtım teknolojisi aracılığıyla uygulama yalıtımı sağlar. Bir Windows Server kapsayıcı bir çekirdek kapsayıcı ana bilgisayar ve ana bilgisayarda çalışan tüm kapsayıcıları ile paylaşır. Bu kapsayıcıların bir saldırgan güvenlik sınırı sağlamaz ve güvenilmeyen kod yalıtmak için kullanılmamalıdır. Paylaşılan çekirdek alanı nedeniyle bu kapsayıcılar aynı çekirdek sürümü ve yapılandırma gerektirir.

**Hyper-V yalıtım**: yüksek oranda iyileştirilmiş bir VM üzerinde her kapsayıcı çalıştırarak Windows Server kapsayıcıları tarafından sağlanan yalıtımı genişletir. Bu yapılandırmada, aynı ana bilgisayardaki diğer kapsayıcılarla kapsayıcı konağının çekirdek paylaşılmaz. Bu kapsayıcılar, saldırgan çok müşterili, bir VM ile aynı güvenlik çıkışların barındırmak için tasarlanmıştır. Bu kapsayıcılar konak veya konak üzerindeki diğer kapsayıcıları çekirdek paylaşmayın olduğundan farklı sürümleri ve yapılandırmalarla (desteklenen sürümler) tekrar çalıştırabilirsiniz. Örneğin, tüm Windows kapsayıcıları Windows 10 Windows Server çekirdek sürümü ve yapılandırmasını kullanmak için Hyper-V yalıtımını kullanın.

Bir kapsayıcı ile veya Hyper-V yalıtım olmadan Windows üzerinde çalışan çalışma zamanında bir karardır. Başlangıçta Hyper-V yalıtım ile kapsayıcı oluşturulacağını seçin ve çalıştırmak Windows Server kapsayıcı olarak bunun yerine çalışma zamanında seçin.

### <a name="additional-resources"></a>Ek kaynaklar

-   **Windows kapsayıcıları belgeleri**

    [https://docs.microsoft.com/Virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Windows kapsayıcıları temelleri**

    [https://docs.microsoft.com/Virtualization/windowscontainers/About/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **Bilgi grafiği: Microsoft ve kapsayıcıları**

    [https://info.microsoft.com/RS/157-GQE-382/images/Container%20infographic%201.4.17.PDF](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)

>[!div class="step-by-step"]
[Önceki](how-to-deploy-existing-net-apps-to-azure-app-service.md)
[sonraki](when-not-to-deploy-to-windows-containers.md)
