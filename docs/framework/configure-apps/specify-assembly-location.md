---
title: Bir derlemeyi &#39; belirtme s konumu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f747d921e9c131edaa8a1749c5adc5eae14623c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-an-assembly39s-location"></a>Bir derlemeyi &#39; belirtme s konumu
Derlemenin konumunu belirtmek için iki yolu vardır:  
  
-   Kullanarak [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) öğesi.  
  
-   Kullanarak [ \<yoklama >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) öğesi.  
  
 Aynı zamanda [.NET Framework yapılandırma aracını (Mscorcfg.msc)](http://msdn.microsoft.com/en-us/a7106c52-68da-490e-b129-971b2c743764) derleme konumları belirtin veya derlemeler için araştırma ortak dil çalışma zamanı için konumlarını belirtin.  
  
## <a name="using-the-codebase-element"></a>Kullanarak \<codeBase > öğesi  
 Kullanabileceğiniz  **\<codeBase >** derleme sürümünü de yönlendiren yalnızca makine yapılandırma veya yayımcı ilke dosyaları öğesinde. Çalışma zamanı kullanmak için hangi derleme sürümü belirlediğinde, sürüm belirleyen dosyasından kod temel ayar uygulanır. Hiçbir kod temeli belirtilirse, çalışma zamanı derlemesi için normal bir şekilde araştırmaları. Ayrıntılar için bkz [nasıl çalışma zamanı bulur derlemeleri](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Aşağıdaki örnek derlemenin konumunu belirtme gösterir.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **Sürüm** özniteliği tüm Tanımlayıcı adlı derlemeler için gerekli değildir ancak güçlü-adlandırılmamış derlemelerde alınmamalıdır. **\<CodeBase >** öğesi gerektiriyor **href** özniteliği. Sürüm aralıklardaki belirtemezsiniz  **\<codeBase >** öğesi.  
  
> [!NOTE]
>  Tanımlayıcı adlı olmayan bir derleme için bir kod temel ipucu sağlayarak, ipucu uygulama temel veya uygulamanın ana dizin alt işaret etmelidir.  
  
## <a name="using-the-probing-element"></a>Kullanarak \<yoklama > öğesi  
 Çalışma zamanı temel bir kod yoklama tarafından yok derlemeleri bulur. Yoklama hakkında daha fazla bilgi için bkz: [nasıl çalışma zamanı bulur derlemeleri](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Kullanabileceğiniz [ \<yoklama >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) alt dizinleri çalışma zamanı bütünleştirilmiş belirlerken arama belirtmek için uygulama yapılandırma dosyasında öğesi. Aşağıdaki örnek, çalışma zamanı arayacağı dizinlerini belirt gösterilmektedir.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **PrivatePath** özniteliği çalışma zamanı derlemeleri için arayacağı dizinleri içerir. Uygulama C:\Program Files\MyApp bulunuyorsa, çalışma zamanı kod temeli C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin ve C:\Program Files\MyApp\Bin3 belirtmeyin derlemeleri arar. Belirtilen dizin **privatePath** uygulamanın ana dizin alt dizinleri olmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortak dil çalışma zamanı derlemeleri](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Derlemelerle programlama](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Çalışma zamanı derlemeleri nasıl bulur](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [.NET Framework uygulamaları yapılandırma](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
