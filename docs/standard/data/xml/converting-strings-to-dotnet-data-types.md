---
title: ".NET Framework veri türleri için dizeleri dönüştürme"
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="8244f-102">.NET Framework veri türleri için dizeleri dönüştürme</span><span class="sxs-lookup"><span data-stu-id="8244f-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="8244f-103">Bir dizeyi bir .NET Framework veri türüne dönüştürmek istiyorsanız, kullanmak **XmlConvert** uygulama gereksinimlerine uygun yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8244f-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="8244f-104">Kullanılabilir tüm dönüştürme yöntemleri listesi **XmlConvert** sınıfı için bkz: <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="8244f-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="8244f-105">Döndürülen dize **ToString** geçirilen verileri dize sürümü bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="8244f-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="8244f-106">Ayrıca, kullanarak Dönüştür çeşitli .NET Framework türleri vardır **XmlConvert** yöntemlere kullanmayın henüz sınıf **System.Convert'i** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="8244f-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="8244f-107">**XmlConvert** sınıf XML Şeması (XSD) veri türü izler ve bir veri, türü **XmlConvert** eşleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8244f-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="8244f-108">Aşağıdaki tabloda, .NET Framework veri türleri ve XML Şeması (XSD) veri türü eşlemesi kullanarak döndürülen dize türlerini listeler.</span><span class="sxs-lookup"><span data-stu-id="8244f-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="8244f-109">Bu .NET Framework türleri kullanılarak işlenemez **System.Convert'i**.</span><span class="sxs-lookup"><span data-stu-id="8244f-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="8244f-110">.NET Framework türü</span><span class="sxs-lookup"><span data-stu-id="8244f-110">.NET Framework type</span></span>|<span data-ttu-id="8244f-111">Döndürülen dize</span><span class="sxs-lookup"><span data-stu-id="8244f-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="8244f-112">Boole değeri</span><span class="sxs-lookup"><span data-stu-id="8244f-112">Boolean</span></span>|<span data-ttu-id="8244f-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="8244f-113">"true", "false"</span></span>|  
|<span data-ttu-id="8244f-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="8244f-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-115">"INF"</span></span>|  
|<span data-ttu-id="8244f-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="8244f-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-117">"-INF"</span></span>|  
|<span data-ttu-id="8244f-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="8244f-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-119">"INF"</span></span>|  
|<span data-ttu-id="8244f-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="8244f-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-121">"-INF"</span></span>|  
|<span data-ttu-id="8244f-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="8244f-122">DateTime</span></span>|<span data-ttu-id="8244f-123">Biçim "yyyy-aa-ddTHH:mm:sszzzzzz" ve onun alt kümeleri.</span><span class="sxs-lookup"><span data-stu-id="8244f-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="8244f-124">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8244f-124">Timespan</span></span>|<span data-ttu-id="8244f-125">Biçimidir PnYnMnTnHnMnS diğer bir deyişle, `P2Y10M15DT10H30M20S` 2 yıl, 10 ay, 15 gün, 10 saat, 30 dakika, ve 20 saniye süresince.</span><span class="sxs-lookup"><span data-stu-id="8244f-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8244f-126">.NET Framework türlerinden herhangi birini dönüştürme kullanarak bir dize için tabloda listelenen **ToString** yöntemi, döndürülen dize temel türü, ancak XML Şeması (XSD) dize türü değil.</span><span class="sxs-lookup"><span data-stu-id="8244f-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="8244f-127">**DateTime** ve **Timespan** değer türü içinde farklı bir **DateTime** ise, zaman içindeki bir anlık temsil eden bir **TimeSpan** bir zaman aralığı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="8244f-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="8244f-128">**DateTime** ve **Timespan** biçimleri XML Şeması (XSD) veri türleri belirtiminde belirtilir.</span><span class="sxs-lookup"><span data-stu-id="8244f-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="8244f-129">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="8244f-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="8244f-130">**Çıktı**</span><span class="sxs-lookup"><span data-stu-id="8244f-130">**Output**</span></span>  
  
 <span data-ttu-id="8244f-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="8244f-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="8244f-132">Aşağıdaki kod, tamsayı bir dizeye dönüştürür:</span><span class="sxs-lookup"><span data-stu-id="8244f-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="8244f-133">**Çıktı**</span><span class="sxs-lookup"><span data-stu-id="8244f-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="8244f-134">Ancak, bir dizeyi dönüştürüyorsanız **Boolean**, **tek**, veya **çift**, döndürülen .NET Framework türü kullanırken döndürülen tür ile aynı değil **System.Convert'i** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="8244f-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="8244f-135">Boole değeri bir dize</span><span class="sxs-lookup"><span data-stu-id="8244f-135">String to Boolean</span></span>  
 <span data-ttu-id="8244f-136">Aşağıdaki tabloda, ne tür verilen Giriş dizeleri için bir dizeye dönüştürme sırasında oluşturulan gösterilmektedir **Boolean** kullanarak **ToBoolean** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8244f-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="8244f-137">Giriş parametresi geçerli bir dize</span><span class="sxs-lookup"><span data-stu-id="8244f-137">Valid string input parameter</span></span>|<span data-ttu-id="8244f-138">.NET framework çıktı türü</span><span class="sxs-lookup"><span data-stu-id="8244f-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="8244f-139">"true"</span><span class="sxs-lookup"><span data-stu-id="8244f-139">"true"</span></span>|<span data-ttu-id="8244f-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="8244f-140">Boolean.True</span></span>|  
|<span data-ttu-id="8244f-141">"1"</span><span class="sxs-lookup"><span data-stu-id="8244f-141">"1"</span></span>|<span data-ttu-id="8244f-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="8244f-142">Boolean.True</span></span>|  
|<span data-ttu-id="8244f-143">"false"</span><span class="sxs-lookup"><span data-stu-id="8244f-143">"false"</span></span>|<span data-ttu-id="8244f-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="8244f-144">Boolean.False</span></span>|  
|<span data-ttu-id="8244f-145">"0"</span><span class="sxs-lookup"><span data-stu-id="8244f-145">"0"</span></span>|<span data-ttu-id="8244f-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="8244f-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="8244f-147">Örneğin, aşağıdaki XML verilen:</span><span class="sxs-lookup"><span data-stu-id="8244f-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="8244f-148">**Giriş**</span><span class="sxs-lookup"><span data-stu-id="8244f-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="8244f-149">Her ikisi de aşağıdaki kodla anlaşılabilir ve **bDeğer** olan **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="8244f-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="8244f-150">Tek bir dize</span><span class="sxs-lookup"><span data-stu-id="8244f-150">String to Single</span></span>  
 <span data-ttu-id="8244f-151">Aşağıdaki tabloda, ne tür verilen Giriş dizeleri için bir dizeye dönüştürme sırasında oluşturulan gösterilmektedir bir **tek** kullanarak **ToSingle** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8244f-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="8244f-152">Giriş parametresi geçerli bir dize</span><span class="sxs-lookup"><span data-stu-id="8244f-152">Valid string input parameter</span></span>|<span data-ttu-id="8244f-153">.NET framework çıktı türü</span><span class="sxs-lookup"><span data-stu-id="8244f-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="8244f-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-154">"INF"</span></span>|<span data-ttu-id="8244f-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="8244f-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-156">"-INF"</span></span>|<span data-ttu-id="8244f-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="8244f-158">Çift dizeye</span><span class="sxs-lookup"><span data-stu-id="8244f-158">String to Double</span></span>  
 <span data-ttu-id="8244f-159">Aşağıdaki tabloda, ne tür verilen Giriş dizeleri için bir dizeye dönüştürme sırasında oluşturulan gösterilmektedir bir **tek** kullanarak **ToDouble** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8244f-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="8244f-160">Giriş parametresi geçerli bir dize</span><span class="sxs-lookup"><span data-stu-id="8244f-160">Valid string input parameter</span></span>|<span data-ttu-id="8244f-161">.NET framework çıktı türü</span><span class="sxs-lookup"><span data-stu-id="8244f-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="8244f-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-162">"INF"</span></span>|<span data-ttu-id="8244f-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="8244f-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="8244f-164">"-INF"</span></span>|<span data-ttu-id="8244f-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="8244f-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="8244f-166">Aşağıdaki kod yazma `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="8244f-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="8244f-167">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8244f-167">See Also</span></span>  
 [<span data-ttu-id="8244f-168">XML veri türlerini dönüştürme</span><span class="sxs-lookup"><span data-stu-id="8244f-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="8244f-169">.NET Framework türleri dizeleri dönüştürme</span><span class="sxs-lookup"><span data-stu-id="8244f-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)