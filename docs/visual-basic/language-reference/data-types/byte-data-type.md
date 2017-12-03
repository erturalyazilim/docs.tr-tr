---
title: "Byte Veri Türü (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6475ff3ed905abb022a9ef60204c04b45130ae22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="43026-102">Byte veri türü (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43026-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="43026-103">Değeri 0 ile 255 arasında imzalanmamış 8 bit (1-bayt) tamsayıları tutar.</span><span class="sxs-lookup"><span data-stu-id="43026-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="43026-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="43026-104">Remarks</span></span>

<span data-ttu-id="43026-105">Kullanım `Byte` veri türü ikili verileri içerir.</span><span class="sxs-lookup"><span data-stu-id="43026-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="43026-106">Varsayılan değer olan `Byte` 0'dır.</span><span class="sxs-lookup"><span data-stu-id="43026-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="43026-107">Değişmez değer atamaları</span><span class="sxs-lookup"><span data-stu-id="43026-107">Literal assignments</span></span>

<span data-ttu-id="43026-108">Bildirme ve başlatma bir `Byte` değişken bir ondalık değişmez değeri, onaltılık değişmez değeri bir sekizlik değişmez değeri atama veya (Visual Basic 2017 ile ikili bir hazır değer başlayarak).</span><span class="sxs-lookup"><span data-stu-id="43026-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="43026-109">Tam sayı sabit değeri aralığının dışında olması durumunda bir `Byte` (diğer bir deyişle, bu ise değerinden <xref:System.Byte.MinValue?displayProperty=nameWithType> veya daha büyük <xref:System.Byte.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="43026-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="43026-110">Aşağıdaki örnekte, ondalık sayı olarak, onaltılık temsil 201 tamsayılar eşit ve ikili değişmez değerleri gelen örtük olarak dönüştürülür [tamsayı](integer-data-type.md) için `byte` değerleri.</span><span class="sxs-lookup"><span data-stu-id="43026-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="43026-111">Önek kullanması `&h` veya `&H` bir onaltılık değişmez değeri, öneki belirtmek için `&b` veya `&B` ikili bir hazır değer ve öneki belirtmek için `&o` veya `&O` sekizlik değişmez değeri belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="43026-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="43026-112">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="43026-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="43026-113">Visual Basic 2017 ile başlayarak, alt çizgi karakteri de kullanabilirsiniz `_`, okunabilirliğini artırmak için bir basamak ayırıcı olarak, aşağıdaki örnekte görüldüğü gibi.</span><span class="sxs-lookup"><span data-stu-id="43026-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

## <a name="programming-tips"></a><span data-ttu-id="43026-114">Programlama ipuçları</span><span class="sxs-lookup"><span data-stu-id="43026-114">Programming tips</span></span>

-   <span data-ttu-id="43026-115">**Negatif sayılar.**</span><span class="sxs-lookup"><span data-stu-id="43026-115">**Negative Numbers.**</span></span> <span data-ttu-id="43026-116">Çünkü `Byte` imzasız bir tür negatif bir sayı temsil edilemez.</span><span class="sxs-lookup"><span data-stu-id="43026-116">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="43026-117">Tekli eksi kullanıyorsanız (`-`) yazmak için değerlendirilen bir ifade işlecinin `Byte`, Visual Basic ifade dönüştürür `Short` ilk.</span><span class="sxs-lookup"><span data-stu-id="43026-117">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="43026-118">**Biçim dönüşümler.**</span><span class="sxs-lookup"><span data-stu-id="43026-118">**Format Conversions.**</span></span> <span data-ttu-id="43026-119">Visual Basic okur veya dosyaları yazma veya DLL'leri, yöntemleri ve özellikleri aradığında, veri biçimleri arasında otomatik olarak dönüştürebilir.</span><span class="sxs-lookup"><span data-stu-id="43026-119">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="43026-120">Depolanan ikili veri `Byte` değişkenleri ve dizileri böyle formatı dönüştürme sırasında korunur.</span><span class="sxs-lookup"><span data-stu-id="43026-120">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="43026-121">Kullanılamaz bir `String` ANSI veya Unicode biçimleri arasında dönüştürme sırasında içeriğinin bozuk için değişken ikili veriler için.</span><span class="sxs-lookup"><span data-stu-id="43026-121">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="43026-122">**Genişletme.**</span><span class="sxs-lookup"><span data-stu-id="43026-122">**Widening.**</span></span> <span data-ttu-id="43026-123">`Byte` Veri türü widens için `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, veya `Double`.</span><span class="sxs-lookup"><span data-stu-id="43026-123">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="43026-124">Bu dönüştürebilirsiniz anlamına gelir `Byte` karşılaşmadan olmadan bu türdeki herhangi bir <xref:System.OverflowException?displayProperty=nameWithType> hata.</span><span class="sxs-lookup"><span data-stu-id="43026-124">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="43026-125">**Karakterleri yazın.**</span><span class="sxs-lookup"><span data-stu-id="43026-125">**Type Characters.**</span></span> <span data-ttu-id="43026-126">`Byte`değişmez değer türü karakteri ya da tanımlayıcı türü karakteri içeriyor.</span><span class="sxs-lookup"><span data-stu-id="43026-126">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="43026-127">**Framework türü.**</span><span class="sxs-lookup"><span data-stu-id="43026-127">**Framework Type.**</span></span> <span data-ttu-id="43026-128">.NET Framework'teki karşılık gelen tür <xref:System.Byte?displayProperty=nameWithType> yapısı.</span><span class="sxs-lookup"><span data-stu-id="43026-128">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="43026-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="43026-129">Example</span></span>

 <span data-ttu-id="43026-130">Aşağıdaki örnekte, `b` olan bir `Byte` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="43026-130">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="43026-131">Aralık değişkeninin ve bit kaydırma işleçleri uygulama ona deyimleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="43026-131">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="43026-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="43026-132">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="43026-133">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="43026-133">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="43026-134">Tür dönüşüm işlevleri</span><span class="sxs-lookup"><span data-stu-id="43026-134">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="43026-135">Dönüştürme özeti</span><span class="sxs-lookup"><span data-stu-id="43026-135">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="43026-136">Veri türlerinin etkili kullanımı</span><span class="sxs-lookup"><span data-stu-id="43026-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)