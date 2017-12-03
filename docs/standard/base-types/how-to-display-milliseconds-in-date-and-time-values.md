---
title: "Nasıl yapılır: Tarih ve Saat Değerlerinde Milisaniyeleri Görüntüleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="29181-102">Nasıl yapılır: Tarih ve Saat Değerlerinde Milisaniyeleri Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="29181-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="29181-103"><xref:System.DateTime.ToString?displayProperty=nameWithType> gibi varsayılan tarih ve saat biçimlendirme yöntemleri, bir zaman değerinin saatlerini, dakikalarını ve saniyelerini içerir ancak milisaniye bileşenini içermez.</span><span class="sxs-lookup"><span data-stu-id="29181-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="29181-104">Bu konu, biçimlendirilen tarih ve saat dizelerine bir tarihin ve saatin milisaniye bileşeninin nasıl eklendiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="29181-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="29181-105">Bir DateTime değerinin milisaniye bileşenini görüntülemek için</span><span class="sxs-lookup"><span data-stu-id="29181-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="29181-106">Eğer bir tarihin dize gösterimiyle çalışıyorsanız, statik <xref:System.DateTime> veya <xref:System.DateTimeOffset> yöntemini kullanarak bunu bir <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> veya bir <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> değerine dönüştürün.</span><span class="sxs-lookup"><span data-stu-id="29181-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="29181-107">Bir saatin milisaniye bileşeninin dize gösterimini ayıklamak için, tarih ve saat değerinin <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> veya <xref:System.DateTimeOffset.ToString%2A> yöntemini çağırın ve `fff` veya `FFF` özel biçim desenini tek başına veya başka özel biçim tanımlayıcılarıyla birlikte `format` parametresi olarak geçirin.</span><span class="sxs-lookup"><span data-stu-id="29181-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29181-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="29181-108">Example</span></span>  
 <span data-ttu-id="29181-109">Bu örnek, her ikisi de tek başına olan ve daha uzun bir tarih ve saat dizesine eklenen bir <xref:System.DateTime> ve bir <xref:System.DateTimeOffset> değerine ait milisaniye bileşenini konsolda görüntüler.</span><span class="sxs-lookup"><span data-stu-id="29181-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="29181-110">`fff` biçim deseni, milisaniye değerinin sonundaki sıfırları içerir.</span><span class="sxs-lookup"><span data-stu-id="29181-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="29181-111">`FFF` biçim deseni bunları bastırır.</span><span class="sxs-lookup"><span data-stu-id="29181-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="29181-112">Fark, aşağıdaki örnekte gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="29181-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="29181-113">Bir tarih ve saate ait milisaniye bileşenini içeren tam bir özel biçim tanımlayıcısını tanımlamadaki sorun, uygulamanın geçerli kültüründeki zaman öğelerinin düzenine karşılık gelmeyebilen sabit kodlanmış bir biçimi tanımlamasıdır.</span><span class="sxs-lookup"><span data-stu-id="29181-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="29181-114">Daha iyi bir alternatif olarak geçerli kültürün <xref:System.Globalization.DateTimeFormatInfo> nesnesi tarafından tanımlanan tarih ve saat görüntüleme desenlerinden birini alıp milisaniye içerecek şekilde değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="29181-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="29181-115">Örnek aynı zamanda bu yaklaşımı da gösterir.</span><span class="sxs-lookup"><span data-stu-id="29181-115">The example also illustrates this approach.</span></span> <span data-ttu-id="29181-116"><xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> özelliğinden geçerli kültürün tam tarih ve saat desenini alır ve ardından saniye deseninin sonrasına `.ffff` özel desenini ekler.</span><span class="sxs-lookup"><span data-stu-id="29181-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="29181-117">Bu işlemi tek bir yöntem çağrısında gerçekleştirmek için örneğin bir normal ifade kullandığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="29181-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="29181-118">Saniyelerin milisaniye dışındaki kesirli bir kısmını görüntülemek için aynı zamanda özel bir biçim tanımlayıcısı da kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="29181-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="29181-119">Örneğin, `f` veya `F` özel biçim tanımlayıcısı bir saniyenin onda birini, `ff` veya `FF` özel biçim tanımlayıcısı bir saniyenin yüzde birini ve `ffff` veya `FFFF` özel biçim tanımlayıcısı bir saniyenin on binde birini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="29181-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="29181-120">Bir milisaniyenin kesirli kısımları döndürülen dizede yuvarlanmak yerine kesilir.</span><span class="sxs-lookup"><span data-stu-id="29181-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="29181-121">Bu biçim tanımlayıcıları aşağıdaki örnekte kullanılır.</span><span class="sxs-lookup"><span data-stu-id="29181-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="29181-122">Bir saniyenin on binde biri veya yüz binde biri gibi çok küçük kesirli birimlerini görüntülemek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="29181-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="29181-123">Ancak, bu değerler anlamlı olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="29181-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="29181-124">Tarih ve saat değerlerinin duyarlığı, sistem saatinin çözünürlüğüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="29181-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="29181-125">Windows NT 3.5 ve üzeri sürümlerde ve [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] işletim sistemlerinde saatin çözünürlüğü yaklaşık olarak 10-15 milisaniyedir.</span><span class="sxs-lookup"><span data-stu-id="29181-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29181-126">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="29181-126">Compiling the Code</span></span>  
 <span data-ttu-id="29181-127">Kodu, csc.exe veya vb.exe kullanarak komut satırında derleyin.</span><span class="sxs-lookup"><span data-stu-id="29181-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="29181-128">Kodu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] içinde derlemek için, bir konsol uygulaması projesi şablonu içine koyun.</span><span class="sxs-lookup"><span data-stu-id="29181-128">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29181-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="29181-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="29181-130">Özel tarih ve saat biçim dizeleri</span><span class="sxs-lookup"><span data-stu-id="29181-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)