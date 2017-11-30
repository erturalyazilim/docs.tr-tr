---
title: "Normal İfadelerdeki Çeşitli Yapılar"
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
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a><span data-ttu-id="82cdc-102">Normal İfadelerdeki Çeşitli Yapılar</span><span class="sxs-lookup"><span data-stu-id="82cdc-102">Miscellaneous Constructs in Regular Expressions</span></span>
<span data-ttu-id="82cdc-103">.NET normal ifadelerde üç çeşitli dil yapıları içerir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-103">Regular expressions in .NET include three miscellaneous language constructs.</span></span> <span data-ttu-id="82cdc-104">Bir etkinleştirmek veya normal ifade deseni ortasında belirli eşleştirme seçenekleri devre dışı bırakmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-104">One lets you enable or disable particular matching options in the middle of a regular expression pattern.</span></span> <span data-ttu-id="82cdc-105">İki kalan normal ifadede açıklamalar dahil olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="82cdc-105">The remaining two let you include comments in a regular expression.</span></span>  
  
## <a name="inline-options"></a><span data-ttu-id="82cdc-106">Satır içi seçenekleri</span><span class="sxs-lookup"><span data-stu-id="82cdc-106">Inline Options</span></span>  
 <span data-ttu-id="82cdc-107">Ayarlayın veya belirli bir desene sözdizimini kullanarak eşleştirme için normal bir ifade parçası seçeneklerini devre dışı bırakma</span><span class="sxs-lookup"><span data-stu-id="82cdc-107">You can set or disable specific pattern matching options for part of a regular expression by using the syntax</span></span>  
  
```  
(?imnsx-imnsx)  
```  
  
 <span data-ttu-id="82cdc-108">Soru işareti sonra etkinleştirmek istediğiniz seçenekleri ve eksi sonra devre dışı bırakmak istediğiniz seçenekleri listeleyin.</span><span class="sxs-lookup"><span data-stu-id="82cdc-108">You list the options you want to enable after the question mark, and the options you want to disable after the minus sign.</span></span> <span data-ttu-id="82cdc-109">Aşağıdaki tabloda her bir seçenek açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="82cdc-109">The following table describes each option.</span></span> <span data-ttu-id="82cdc-110">Her bir seçenek hakkında daha fazla bilgi için bkz: [normal ifade seçenekleri](../../../docs/standard/base-types/regular-expression-options.md).</span><span class="sxs-lookup"><span data-stu-id="82cdc-110">For more information about each option, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
|<span data-ttu-id="82cdc-111">Seçenek</span><span class="sxs-lookup"><span data-stu-id="82cdc-111">Option</span></span>|<span data-ttu-id="82cdc-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-112">Description</span></span>|  
|------------|-----------------|  
|`i`|<span data-ttu-id="82cdc-113">Büyük küçük harf duyarsız eşleşen.</span><span class="sxs-lookup"><span data-stu-id="82cdc-113">Case-insensitive matching.</span></span>|  
|`m`|<span data-ttu-id="82cdc-114">Çok satırlı modu.</span><span class="sxs-lookup"><span data-stu-id="82cdc-114">Multiline mode.</span></span>|  
|`n`|<span data-ttu-id="82cdc-115">Yalnızca açık yakalar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-115">Explicit captures only.</span></span> <span data-ttu-id="82cdc-116">(Parantez yok davranan grupları yakalama olarak.)</span><span class="sxs-lookup"><span data-stu-id="82cdc-116">(Parentheses do not act as capturing groups.)</span></span>|  
|`s`|<span data-ttu-id="82cdc-117">Tek satırlı modu.</span><span class="sxs-lookup"><span data-stu-id="82cdc-117">Single-line mode.</span></span>|  
|`x`|<span data-ttu-id="82cdc-118">Atlanmayan boşluk yoksay ve x modu açıklamalara izin verme.</span><span class="sxs-lookup"><span data-stu-id="82cdc-118">Ignore unescaped white space, and allow x-mode comments.</span></span>|  
  
 <span data-ttu-id="82cdc-119">Normal ifade seçenekleri tarafından tanımlanan herhangi bir değişikliği `(?imnsx-imnsx)` kapsayan grubun sonuna kadar etkin kalır oluşturun.</span><span class="sxs-lookup"><span data-stu-id="82cdc-119">Any change in regular expression options defined by the `(?imnsx-imnsx)` construct remains in effect until the end of the enclosing group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82cdc-120">`(?imnsx-imnsx:` *Alt* `)` gruplama yapısı için bir alt aynı işlevselliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-120">The `(?imnsx-imnsx:`*subexpression*`)` grouping construct provides identical functionality for a subexpression.</span></span> <span data-ttu-id="82cdc-121">Daha fazla bilgi için bkz: [gruplandırma yapıları](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="82cdc-121">For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="82cdc-122">Aşağıdaki örnek kullanır `i`, `n`, ve `x` seçenekleri büyük/küçük harfe ve açık yakalamaları etkinleştirin ve normal bir ifade ortasında normal ifade deseni boşluk yoksay.</span><span class="sxs-lookup"><span data-stu-id="82cdc-122">The following example uses the `i`, `n`, and `x` options to enable case insensitivity and explicit captures, and to ignore white space in the regular expression pattern in the middle of a regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 <span data-ttu-id="82cdc-123">Örneğin, iki normal ifadeler tanımlar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-123">The example defines two regular expressions.</span></span> <span data-ttu-id="82cdc-124">İlk `\b(D\w+)\s(d\w+)\b`, "D" bir büyük harf ve küçük harf "d" ile başlayan iki ardışık sözcük eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-124">The first, `\b(D\w+)\s(d\w+)\b`, matches two consecutive words that begin with an uppercase "D" and a lowercase "d".</span></span> <span data-ttu-id="82cdc-125">İkinci normal ifade `\b(D\w+)(?ixn) \s (d\w+) \b`, aşağıdaki tabloda açıklandığı gibi bu deseni değiştirmek için satır içi seçeneklerini kullanır.</span><span class="sxs-lookup"><span data-stu-id="82cdc-125">The second regular expression, `\b(D\w+)(?ixn) \s (d\w+) \b`, uses inline options to modify this pattern, as described in the following table.</span></span> <span data-ttu-id="82cdc-126">Sonuçları karşılaştırması etkisini onaylar `(?ixn)` oluşturun.</span><span class="sxs-lookup"><span data-stu-id="82cdc-126">A comparison of the results confirms the effect of the `(?ixn)` construct.</span></span>  
  
|<span data-ttu-id="82cdc-127">Desen</span><span class="sxs-lookup"><span data-stu-id="82cdc-127">Pattern</span></span>|<span data-ttu-id="82cdc-128">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-128">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="82cdc-129">Bir sözcük sınırında başla.</span><span class="sxs-lookup"><span data-stu-id="82cdc-129">Start at a word boundary.</span></span>|  
|`(D\w+)`|<span data-ttu-id="82cdc-130">Büyük harf "bir veya daha fazla word karakterle devam etmelidir D" eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-130">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="82cdc-131">Bu ilk yakalama grubudur.</span><span class="sxs-lookup"><span data-stu-id="82cdc-131">This is the first capture group.</span></span>|  
|`(?ixn)`|<span data-ttu-id="82cdc-132">Bu noktasında, büyük küçük harf duyarsız yapma karşılaştırmaları, yalnızca açık olun yakalar ve normal ifade deseni boşluk yoksay.</span><span class="sxs-lookup"><span data-stu-id="82cdc-132">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`\s`|<span data-ttu-id="82cdc-133">Bir boşluk karakteri ile eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="82cdc-133">Match a white-space character.</span></span>|  
|`(d\w+)`|<span data-ttu-id="82cdc-134">Eşleşen bir büyük veya küçük harf "d" bir veya daha fazla word karakterle devam etmelidir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-134">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="82cdc-135">Bu grup, çünkü sayılmaz `n` (açık yakalama) seçeneği etkinleştirilmiş...</span><span class="sxs-lookup"><span data-stu-id="82cdc-135">This group is not captured because the `n` (explicit capture) option was enabled..</span></span>|  
|`\b`|<span data-ttu-id="82cdc-136">Bir sözcük sınırıyla eşleş.</span><span class="sxs-lookup"><span data-stu-id="82cdc-136">Match a word boundary.</span></span>|  
  
## <a name="inline-comment"></a><span data-ttu-id="82cdc-137">Satır içi açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-137">Inline Comment</span></span>  
 <span data-ttu-id="82cdc-138">`(?#` *Açıklama* `)` yapı normal ifadede bir satır içi açıklama eklemek olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-138">The `(?#` *comment*`)` construct lets you include an inline comment in a regular expression.</span></span> <span data-ttu-id="82cdc-139">Normal ifade altyapısı tarafından döndürülen dize açıklama bulunmaktadır ancak desen eşleştirme, açıklaması, herhangi bir bölümünü kullanmaz <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="82cdc-139">The regular expression engine does not use any part of the comment in pattern matching, although the comment is included in the string that is returned by the <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="82cdc-140">Açıklama ilk kapanış parantezinde sona erer.</span><span class="sxs-lookup"><span data-stu-id="82cdc-140">The comment ends at the first closing parenthesis.</span></span>  
  
 <span data-ttu-id="82cdc-141">Aşağıdaki örnek, önceki bölümde örneğindeki ilk normal ifade deseni tekrarlar.</span><span class="sxs-lookup"><span data-stu-id="82cdc-141">The following example repeats the first regular expression pattern from the example in the previous section.</span></span> <span data-ttu-id="82cdc-142">İki satır içi açıklamalar karşılaştırma büyük küçük harfe duyarlı olup olmadığını belirtmek için normal ifade ekler.</span><span class="sxs-lookup"><span data-stu-id="82cdc-142">It adds two inline comments to the regular expression to indicate whether the comparison is case-sensitive.</span></span> <span data-ttu-id="82cdc-143">Normal ifade deseni `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, aşağıdaki gibi tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="82cdc-143">The regular expression pattern, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, is defined as follows.</span></span>  
  
|<span data-ttu-id="82cdc-144">Desen</span><span class="sxs-lookup"><span data-stu-id="82cdc-144">Pattern</span></span>|<span data-ttu-id="82cdc-145">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-145">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="82cdc-146">Bir sözcük sınırında başla.</span><span class="sxs-lookup"><span data-stu-id="82cdc-146">Start at a word boundary.</span></span>|  
|`(?# case-sensitive comparison)`|<span data-ttu-id="82cdc-147">Bir yorum.</span><span class="sxs-lookup"><span data-stu-id="82cdc-147">A comment.</span></span> <span data-ttu-id="82cdc-148">Desen eşleştirme davranışını etkilemez.</span><span class="sxs-lookup"><span data-stu-id="82cdc-148">It does not affect pattern-matching behavior.</span></span>|  
|`(D\w+)`|<span data-ttu-id="82cdc-149">Büyük harf "bir veya daha fazla word karakterle devam etmelidir D" eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-149">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="82cdc-150">Bu ilk yakalama grubudur.</span><span class="sxs-lookup"><span data-stu-id="82cdc-150">This is the first capturing group.</span></span>|  
|`\s`|<span data-ttu-id="82cdc-151">Bir boşluk karakteri ile eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="82cdc-151">Match a white-space character.</span></span>|  
|`(?ixn)`|<span data-ttu-id="82cdc-152">Bu noktasında, büyük küçük harf duyarsız yapma karşılaştırmaları, yalnızca açık olun yakalar ve normal ifade deseni boşluk yoksay.</span><span class="sxs-lookup"><span data-stu-id="82cdc-152">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`(?#case-insensitive comparison)`|<span data-ttu-id="82cdc-153">Bir yorum.</span><span class="sxs-lookup"><span data-stu-id="82cdc-153">A comment.</span></span> <span data-ttu-id="82cdc-154">Desen eşleştirme davranışını etkilemez.</span><span class="sxs-lookup"><span data-stu-id="82cdc-154">It does not affect pattern-matching behavior.</span></span>|  
|`(d\w+)`|<span data-ttu-id="82cdc-155">Eşleşen bir büyük veya küçük harf "d" bir veya daha fazla word karakterle devam etmelidir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-155">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="82cdc-156">Bu ikinci bir yakalama grubudur.</span><span class="sxs-lookup"><span data-stu-id="82cdc-156">This is the second capture group.</span></span>|  
|`\b`|<span data-ttu-id="82cdc-157">Bir sözcük sınırıyla eşleş.</span><span class="sxs-lookup"><span data-stu-id="82cdc-157">Match a word boundary.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a><span data-ttu-id="82cdc-158">Satır sonu açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-158">End-of-Line Comment</span></span>  
 <span data-ttu-id="82cdc-159">Sayı işareti (`#`) normal ifade deseni sonunda atlanmayan # karakteri başlar ve satırın sonuna kadar devam x modu yorum işaretler.</span><span class="sxs-lookup"><span data-stu-id="82cdc-159">A number sign (`#`)marks an x-mode comment, which starts at the unescaped # character at the end of the regular expression pattern and continues until the end of the line.</span></span> <span data-ttu-id="82cdc-160">Bu yapıyı kullanmak için Etkinleştir'i gerekir `x` seçeneği (satır içi seçenekleri) veya kaynağı <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> değeri `option` başlatılırken parametresi <xref:System.Text.RegularExpressions.Regex> nesnesi veya bir statik çağırma <xref:System.Text.RegularExpressions.Regex> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="82cdc-160">To use this construct, you must either enable the `x` option (through inline options) or supply the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> value to the `option` parameter when instantiating the <xref:System.Text.RegularExpressions.Regex> object or calling a static <xref:System.Text.RegularExpressions.Regex> method.</span></span>  
  
 <span data-ttu-id="82cdc-161">Aşağıdaki örnek, satır sonu açıklama yapı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-161">The following example illustrates the end-of-line comment construct.</span></span> <span data-ttu-id="82cdc-162">Bu bir dize en az bir biçim öğesi içeren bileşik biçim dizesi olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="82cdc-162">It determines whether a string is a composite format string that includes at least one format item.</span></span> <span data-ttu-id="82cdc-163">Aşağıdaki tabloda, normal ifade deseni yapılardan açıklanmaktadır:</span><span class="sxs-lookup"><span data-stu-id="82cdc-163">The following table describes the constructs in the regular expression pattern:</span></span>  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|<span data-ttu-id="82cdc-164">Desen</span><span class="sxs-lookup"><span data-stu-id="82cdc-164">Pattern</span></span>|<span data-ttu-id="82cdc-165">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82cdc-165">Description</span></span>|  
|-------------|-----------------|  
|`\{`|<span data-ttu-id="82cdc-166">Açılan parantez eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-166">Match an opening brace.</span></span>|  
|`\d+`|<span data-ttu-id="82cdc-167">Bir veya daha fazla ondalık basamağı eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="82cdc-167">Match one or more decimal digits.</span></span>|  
|`(,-*\d+)*`|<span data-ttu-id="82cdc-168">Bir veya daha fazla ondalık basamak ile izlenen isteğe bağlı bir eksi işareti, arkasından virgül, sıfır veya bir örneğini Bul.</span><span class="sxs-lookup"><span data-stu-id="82cdc-168">Match zero or one occurrence of a comma, followed by an optional minus sign, followed by one or more decimal digits.</span></span>|  
|`(\:\w{1,4}?)*`|<span data-ttu-id="82cdc-169">Sıfır veya bir geçişi dörde ancak olabildiğince az olabildiğince, boşluk karakterleri tarafından üste ile eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-169">Match zero or one occurrence of a colon, followed by one to four, but as few as possible, white-space characters.</span></span>|  
|`(?#case insensitive comparison)`|<span data-ttu-id="82cdc-170">Satır içi bir yorum.</span><span class="sxs-lookup"><span data-stu-id="82cdc-170">An inline comment.</span></span> <span data-ttu-id="82cdc-171">Desen eşleştirme davranışı üzerinde bir etkisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="82cdc-171">It has no effect on pattern-matching behavior.</span></span>|  
|`\}`|<span data-ttu-id="82cdc-172">Kapatılan parantez eşleşir.</span><span class="sxs-lookup"><span data-stu-id="82cdc-172">Match a closing brace.</span></span>|  
|`(?x)`|<span data-ttu-id="82cdc-173">Böylece satır sonu açıklama tanınan yoksay düzeni boşluk seçeneğini etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="82cdc-173">Enable the ignore pattern white-space option so that the end-of-line comment will be recognized.</span></span>|  
|`# Looks for a composite format item.`|<span data-ttu-id="82cdc-174">Bir satır sonu açıklaması.</span><span class="sxs-lookup"><span data-stu-id="82cdc-174">An end-of-line comment.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 <span data-ttu-id="82cdc-175">Sağlama yerine Not `(?x)` oluşturmak normal ifadede açıklama da çağırarak kabul edilmemiş <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> yöntemi ve onu <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> numaralandırma değeri.</span><span class="sxs-lookup"><span data-stu-id="82cdc-175">Note that, instead of providing the `(?x)` construct in the regular expression, the comment could also have been recognized by calling the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method and passing it the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> enumeration value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cdc-176">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="82cdc-176">See Also</span></span>  
 [<span data-ttu-id="82cdc-177">Normal ifade dili - hızlı başvuru</span><span class="sxs-lookup"><span data-stu-id="82cdc-177">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)