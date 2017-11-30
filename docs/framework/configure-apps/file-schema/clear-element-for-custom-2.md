---
title: "&lt;Clear&gt; NameValueSectionHandler ve DictionarySectionHandler öğesi"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e91c3d9693cf656a8c56c82d1997f74c2b3d64c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="12041-102">\<Clear > öğesi NameValueSectionHandler ve DictionarySectionHandler için</span><span class="sxs-lookup"><span data-stu-id="12041-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="12041-103">Bir bölümdeki tüm önceden tanımlanmış ayarları temizler.</span><span class="sxs-lookup"><span data-stu-id="12041-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="12041-104">[**\<Yapılandırma >**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="12041-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="12041-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="12041-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="12041-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Clear >**</span><span class="sxs-lookup"><span data-stu-id="12041-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="12041-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="12041-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="12041-108">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="12041-108">Attributes</span></span>

<span data-ttu-id="12041-109">Yok.</span><span class="sxs-lookup"><span data-stu-id="12041-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="12041-110">Üst öğesi</span><span class="sxs-lookup"><span data-stu-id="12041-110">Parent element</span></span>

|     | <span data-ttu-id="12041-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="12041-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="12041-112">**\<sectionName >** öğesi</span><span class="sxs-lookup"><span data-stu-id="12041-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="12041-113">Kullanan özel yapılandırma bölümlerinin ayarlarını tanımlar <xref:System.Configuration.NameValueSectionHandler> ve <xref:System.Configuration.DictionarySectionHandler> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="12041-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="12041-114">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="12041-114">Child elements</span></span>

<span data-ttu-id="12041-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="12041-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="12041-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="12041-116">Remarks</span></span>

<span data-ttu-id="12041-117">Kullanabileceğiniz  **\<temizleyin >** uygulamanızdan yapılandırma dosyası hiyerarşisinde daha yüksek bir düzeyde tanımlanan tüm ayarlar kaldırılacak öğe.</span><span class="sxs-lookup"><span data-stu-id="12041-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="12041-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="12041-118">Example</span></span>

<span data-ttu-id="12041-119">Bu örnek bir uygulama yapılandırma dosyasını ve makine yapılandırma dosyasını tanımlar ve nasıl kullanılacağını gösterir  **\<temizleyin >** önceden tanımlanmış bir bölümü temizlemek için bir uygulama yapılandırma dosyasında öğesi makine yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="12041-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="12041-120">Bölümü aşağıdaki makine yapılandırma dosyası kodu bildirir  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="12041-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="12041-121">Aşağıdaki uygulama yapılandırma dosyası kodu tüm ayarlarından kaldırır  **\<mySection >**.</span><span class="sxs-lookup"><span data-stu-id="12041-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="12041-122">Uygulama içinde bildirilen ayarlardan herhangi birini alınamıyor,  **\<mySection >** makine yapılandırma dosyası bölümünü.</span><span class="sxs-lookup"><span data-stu-id="12041-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="12041-123">Yapılandırma dosyası</span><span class="sxs-lookup"><span data-stu-id="12041-123">Configuration file</span></span>

<span data-ttu-id="12041-124">Bu öğe uygulama yapılandırma dosyasında makine yapılandırma dosyası kullanılabilir (*Machine.config*), ve *Web.config* uygulama dizin düzeyinde olmayan dosyalar.</span><span class="sxs-lookup"><span data-stu-id="12041-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="12041-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="12041-125">See also</span></span>

[<span data-ttu-id="12041-126">.NET Framework için yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="12041-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)