---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7df39bd0f6d6d4d309cf5c599ecd3795eb92067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="1022---startbookmarkworkitem"></a>1022 - StartBookmarkWorkItem
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimlik|1022|  
|Anahtar Sözcükler|WFRuntime|  
|Düzey|Ayrıntılı|  
|Kanal|Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama|  
  
## <a name="description"></a>Açıklama  
 Bir BookmarkWorkItem yürütme başlanacağını gösterir.  
  
## <a name="message"></a>İleti  
 '%1', DisplayName etkinliğinin BookmarkWorkItem yürütülmesi başlatılıyor: '%2', örnek kimliği: '%3'.  YerİşaretiAdı: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|Etkinlik|xs: String|Etkinlik türü adı.|  
|Görünen adı|xs: String|Etkinliğin görünen adı.|  
|örnek kimliği|xs: String|Etkinlik örnek kimliği.|  
|YerİşaretiAdı|xs: String|Yer işaretinin adı.|  
|BookmarkScope|xs: String|Yer işareti kapsamı.|  
|AppDomain|xs: String|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|
