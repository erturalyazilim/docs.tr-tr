---
title: "Numaralandırma türleri yerine numaralandırma sınıflarını kullanma"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Numaralandırma türleri yerine numaralandırma sınıflarını kullanma"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a>Numaralandırma türleri yerine numaralandırma sınıflarını kullanma

[Numaralandırmalar](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*numaralandırmaları* kısaca) bir tam sayı türü çevresinde bir ince dil sarmalayıcı şunlardır. Kapalı bir değerler kümesinden bir değer depolarken kullanımları sınırlamak isteyebilirsiniz. Cinsiyeti (örneğin, erkek, kadın, bilinmeyen) veya boyutları (S, M, L, XL) temel alan sınıflandırma iyi örnekler verilmiştir. Denetim akışı veya daha sağlam soyutlamalar numaralandırmaları kullanmak olabilir bir [kod kokusu](http://deviq.com/code-smells/). Bu tür kullanımı kırılacak kodu Enum değerleri denetleme birçok denetim akışı deyimleri ile götürür.

Bunun yerine, tüm zengin bir nesne yönelimli dil özelliklerini etkinleştirmek numaralandırması sınıfları oluşturabilirsiniz. Ancak, bu kritik bir sorun değildir ve tercihinizi ise, çoğu durumda, kolaylık sağlamak için normal numaralandırmaları kullanmaya devam edebilirsiniz.

## <a name="implementing-enumeration-classes"></a>Numaralandırma sınıflarını uygulama

Sıralama mikro hizmet eShopOnContainers içinde aşağıdaki örnekte gösterildiği gibi bir örnek numaralandırması temel sınıf uygulamasını sağlar:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

Bu sınıf, aşağıdaki CardType numaralandırma sınıfı için olduğu gibi tüm varlık veya değer nesnesindeki türü olarak kullanabilirsiniz.

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }


    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a>Ek kaynaklar

-   **Enum'ın kötü — güncelleştirme**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)

-   **Daniel Hardman. Nasıl numaralandırmaları Hastalık yayılan — Ve onu temizlemeye yönelik nasıl**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

-   **Jimmy Bogard. Numaralandırma sınıflarını**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

-   **Steve Smith. C# Enum alternatifleri**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)

-   **Enumeration.cs.** EShopOnContainers numaralandırma sınıfında temel [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

-   **CardType.cs**. EShopOnContainers örnek numaralandırma sınıfı.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[Önceki] (uygulama-değer-objects.md) [sonraki] (etki alanı-model-katman-validations.md)
