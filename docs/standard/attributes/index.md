---
title: "Öznitelikleri Kullanarak Meta Verileri Genişletme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8151fd7738dd41ee6ae330a90f3814ec2cc9eb62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="extending-metadata-using-attributes"></a>Öznitelikleri Kullanarak Meta Verileri Genişletme
Ortak dil çalışma zamanı anahtar sözcük benzeri tanımlayıcı bildirimler eklemenize olanak sağlayan türleri, alanları, yöntemleri ve özellikleri gibi programlama öğelerine ek açıklama eklemek için öznitelikler çağrılır. Çalışma zamanı için kodunuzu derlerken Microsoft Ara dile (MSIL) dönüştürülür ve taşınabilir yürütülebilir (PE) dosya derleyici tarafından oluşturulan meta verilerinin yanı sıra içinde yerleştirilir. Öznitelikler, çalışma zamanı yansıma Hizmetleri kullanarak ayıklanan meta verileri içine fazladan açıklayıcı bilgiler yerleştirin olanak tanır. Öğesinden türetilen özel sınıfların örneklerini bildirirken derleyici öznitelikleri oluşturur <xref:System.Attribute?displayProperty=nameWithType>.  
  
 .NET Framework öznitelikleri çeşitli nedenleri ve bir dizi sorununu gidermek için kullanır. Öznitelikler, verilerini seri hale getirmek, güvenlik uygulamak için kullanılan özellikleri belirtin ve böylece kodu hata ayıklamak kolay tam zamanında (JIT) derleyici tarafından en iyi duruma getirme sınırı anlatmaktadır. Öznitelikleri ayrıca bir dosya adı veya kod yazarı kaydedin veya forms geliştirme sırasında denetimleri ve üye görünürlüğünü denetleme.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Öznitelikleri uygulama](../../../docs/standard/attributes/applying-attributes.md)|Bir öznitelik kodunuzun bir öğeye uygulamak açıklar.|  
|[Özel öznitelikler yazma](../../../docs/standard/attributes/writing-custom-attributes.md)|Özel öznitelik sınıfları tasarım konuları açıklanmaktadır.|  
|[Özniteliklerde depolanan bilgileri alma](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)|Yürütme bağlamına yüklenen kod için özel öznitelikleri almak açıklar.|  
|[Meta veriler ve kendiliğinden açıklayıcı bileşenler](../../../docs/standard/metadata-and-self-describing-components.md)|Meta veri genel bir bakış sağlar ve bir .NET Framework taşınabilir yürütülebilir (PE) dosyasında nasıl uygulandığı açıklanmaktadır.|  
|[Nasıl yapılır: salt yansıma bağlamına derlemeleri yükleme](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Yalnızca yansıma bağlamda özel öznitelik bilgileri almak açıklanmaktadır.|  
  
## <a name="reference"></a>Başvuru  
 <xref:System.Attribute?displayProperty=nameWithType>
