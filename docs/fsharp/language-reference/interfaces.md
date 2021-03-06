---
title: Arabirimler (F#)
description: "F # arabirimleri diğer sınıflar uygulayan ilgili üye kümesi nasıl belirteceğinizi öğrenin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a082459-17d4-45cf-9153-0b7550a154ec
ms.openlocfilehash: d7c95e5f5cc0bc6c7f6393af990427ac491c5b79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="interfaces"></a>Arabirimler

*Arabirimleri* diğer sınıflar uygulayan ilgili üye kümesi belirtin.

## <a name="syntax"></a>Sözdizimi

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Açıklamalar
Hiçbir üye uygulanan dışında arabirim bildirimleri sınıf bildirimleri benzer. Bunun yerine, tüm üyeleri anahtar sözcüğüyle belirtildiği gibi Özet, `abstract`. Soyut yöntemler için bir yöntem gövdesi sağlamaz. Ayrıca ayrı bir üye tanımı ile birlikte bir yöntem olarak ekleyerek bir varsayılan uygulama ancak sağlayabilir `default` anahtar sözcüğü. Bunun yapılması, sanal bir yöntem diğer .NET dilleri temel sınıf oluşturmak için eşdeğerdir. Arabirimini uygulayan sınıflar sanal bir yöntem geçersiz kılınabilir.

İsteğe bağlı olarak, her yöntem parametresi normal F # sözdizimi kullanılarak bir ad verebilir:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

Yukarıdaki içinde `ISprintable` örnek, `Print` yöntemi sahip tek bir parametre türü `string` adıyla `format`.

Arabirimlerini iki yolu vardır: object ifadelerini kullanarak ve sınıf türleri kullanarak. Her iki durumda da sınıf türü ya da nesne deyim yöntem gövdeleri için arabiriminin Özet yöntemleri sağlar. Arabirimini uygulayan her türü için belirli uygulamalarıdır. Bu nedenle, farklı türlerde arabirim yöntemleri birbirinden farklı olabilir.

Anahtar sözcükler `interface` ve `end`, başlangıç ve bitiş tanımının işaretlemek isteğe bağlı basit sözdizimini kullandığınızda. Bu anahtar sözcükler kullanmayın türü bir sınıf veya arabirim kullandığınız yapıları çözümleyerek olup olmadığını anlamak derleyici çalışır. Bir üye tanımlayın veya diğer sınıf söz dizimini kullanın, türü bir sınıf olarak yorumlanır.

Tüm arabirimler büyük harfle başlamak için stil kodlama .NET olduğu `I`.


## <a name="implementing-interfaces-by-using-class-types"></a>Sınıf türleri kullanarak arabirimler uygulama
Kullanarak bir sınıf türünün bir veya daha fazla arabirimleri uygulayabilir `interface` anahtar sözcüğü, arabirimin adını ve `with` arabirim üye tanımları tarafından aşağıdaki kodda gösterildiği gibi anahtar sözcüğünü,.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Türetilen tüm sınıflar, bunları yeniden uygulamalı gerekmez. böylece arabirim uygulamaları devralınır.


## <a name="calling-interface-methods"></a>Arama Arabirim yöntemleri
Arabirimini uygulayan türünde herhangi bir nesne üzerinden değil, yalnızca arabiriminden arabirim yöntemleri çağrılamaz. Böylece, arabirim türüne yukarı çevrim kullanarak gerekebilir `:>` işleci veya `upcast` bu yöntemleri çağırmak için işleci.

Nesne türüne sahip olduğunda arabirim yöntemini çağırmak için `SomeClass`, aşağıdaki kodda gösterildiği gibi yukarı çevrim arabirim türü nesneye gerekir.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Alternatif bir yöntem bir nesne üzerinde bu upcasts bildirmektir ve aşağıdaki örnekteki gibi arabirim yöntemini çağırır.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>Nesne ifadeleri kullanarak arabirimler uygulama
Nesne ifadeleri bir arabirim için kısa bir yol sağlar. Bunlar, adlandırılmış bir tür oluşturmak zorunda değildir ve yalnızca ek yöntemleri olmadan arabirim yöntemleri destekleyen bir nesne istediğinizde kullanışlıdır. Aşağıdaki kodda bir nesne ifadesi gösterilmiştir.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>Arabirim devralma
Bir veya daha fazla temel arabirimlerinden arabirimleri devralabilirsiniz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>Ayrıca Bkz.
[F # dili başvurusu](index.md)

[Nesne ifadeleri](object-expressions.md)

[Sınıfları](classes.md)
