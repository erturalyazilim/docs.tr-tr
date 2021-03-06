---
title: "Dinamik güncelleştirmeleri NodeLists ve NamedNodeMaps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Dinamik güncelleştirmeleri NodeLists ve NamedNodeMaps
Çünkü **XmlNodeList** ve **XmlNamedNodeMap** XML belgesi belleğe yüklenir ve değiştirilmekte olduğundan, henüz bir düğüm kümesini içeren World Wide Web Konsorsiyumu (W3C) bildiren bu nesneler Bu düğümler dinamik olarak gerek kümesi içerir. Temel alınan belge değişirse, diğer bir deyişle, ardından bu iki nesne verileri aynı zamanda değiştirmeniz gerekir. Bu nedenle, varsa bir **XmlNodeList** belirli bir öğenin (örneğin, X öğesi) tüm alt öğelerini içeren ve ardından ek öğe, belgenin öğesi X altında Q, öğesine ekleyin. **XmlNodeList** bu yeni bir öğesi kendi koleksiyonuna eklenen Q de olmalıdır. Aynı durum geçerlidir ters. Bir düğüm eklenirse **XmlNodeList**, temel alınan belge de güncelleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belge nesne modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
