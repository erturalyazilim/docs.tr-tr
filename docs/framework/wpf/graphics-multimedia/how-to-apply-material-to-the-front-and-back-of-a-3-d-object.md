---
title: "Nasıl yapılır: 3B Nesnenin Ön ve Arkasına Malzeme Uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce4605208be264418088399253298798205c3f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="456fa-102">Nasıl yapılır: 3B Nesnenin Ön ve Arkasına Malzeme Uygulama</span><span class="sxs-lookup"><span data-stu-id="456fa-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="456fa-103">Aşağıdaki örnekte nasıl uygulanacağını gösterir bir <xref:System.Windows.Media.Media3D.Material> önüne ve 3-b arkasına nesnesi ve her iki tarafında nesne göstermek için nesnenin animasyon.</span><span class="sxs-lookup"><span data-stu-id="456fa-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="456fa-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Özelliği bir <xref:System.Windows.Media.Media3D.GeometryModel3D> kırmızı uygulamak için kullanılan <xref:System.Windows.Media.Brush> nesne ön tarafına ve <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> özelliği <xref:System.Windows.Media.Media3D.GeometryModel3D> mavi uygulamak için kullanılan <xref:System.Windows.Media.Brush> nesnenin arka tarafına.</span><span class="sxs-lookup"><span data-stu-id="456fa-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="456fa-105">Aşağıdaki kod, nesne malzemeleri uygulamaya gösterir:</span><span class="sxs-lookup"><span data-stu-id="456fa-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="456fa-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="456fa-106">Example</span></span>  
 <span data-ttu-id="456fa-107">Aşağıdaki kod tüm örneği gösterir.</span><span class="sxs-lookup"><span data-stu-id="456fa-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="456fa-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="456fa-108">See Also</span></span>  
 [<span data-ttu-id="456fa-109">3B Sahne oluşturma</span><span class="sxs-lookup"><span data-stu-id="456fa-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="456fa-110">3B Grafiklere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="456fa-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="456fa-111">3B Sahne içinde Malzeme özelliklerine animasyon ekleme</span><span class="sxs-lookup"><span data-stu-id="456fa-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="456fa-112">3B nesnesine Yayıcı malzeme Uygula</span><span class="sxs-lookup"><span data-stu-id="456fa-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)