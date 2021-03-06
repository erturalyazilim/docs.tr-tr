---
title: "XNA Uygulamasında Düzenlemeleri ve Eylemsizliği Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: adf48310c1c2e0c59224ab820211e818a2401579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>XNA Uygulamasında Düzenlemeleri ve Eylemsizliği Kullanma
Bu makalede, oyun parça hareketini denetlemek için düzenlemeler ve eylemsizlik Microsoft XNA uygulamasında işleme nasıl kullanabileceğinizi açıklar. Bu makalede okumadan önce aşina olmalısınız [düzenlemelere ve Eylemsizliğe genel bakış](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) konusuna ve temel XNA ile programlama kavramları hakkında bilgi sahibi olun.  
  
 Bu makalede açıklanan görevleri gerçekleştirmek için XNA projenizi başvurmalıdır <xref:System.Windows.Input.Manipulations> derleme ve olmalıdır [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([karşıdan](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)), bu nedenle, bilgisayarınızda, Proje XNA derlemeleri başvuruda bulunabilir.  
  
## <a name="overview-of-functionality"></a>İşlevselliğine genel bakış  
 Bu makalede işleme ve eylemsizlik işleme kullanan bir oyun gösteren özel bir sınıfın nasıl oluşturulacağı gösterilmektedir. Bu sınıf, bir oyun parça fareyle sürükleyin ve bunu serbest ekran boyunca yönetmenize olanak sağlar. Serbest sonra tutar işleme eylemsizlik kademeli taşımadan oyun parça yavaşlar. Doğrusal ve Açısal taşıma.  
  
 ![Basit düzenlemeler ve eylemsizlik uygulama. ] (../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 Ayrıca, özel bir koleksiyona, birden çok oyun parça yöneten oluşturulur. XNA oyun sınıfından gereklidir işleme basitleştirir.  
  
 [GamePiece sınıfı oluşturma](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [GamePieceCollection sınıfı oluşturma](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Game1 sınıfı oluşturma](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Tam kod listeleri](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Input.Manipulations>  
 [Düzenlemelere ve Eylemsizliğe genel bakış](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
