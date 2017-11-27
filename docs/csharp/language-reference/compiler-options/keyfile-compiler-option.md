---
title: "-keyfile (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d120b325f433108cd1b01dd1c25d2a0e55da401b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile-c-compiler-options"></a><span data-ttu-id="5fcb7-102">/keyfile (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="5fcb7-102">/keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="5fcb7-103">Şifreleme anahtarını içeren dosya adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fcb7-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5fcb7-104">Syntax</span></span>  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5fcb7-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="5fcb7-105">Arguments</span></span>  
  
|<span data-ttu-id="5fcb7-106">Terim</span><span class="sxs-lookup"><span data-stu-id="5fcb7-106">Term</span></span>|<span data-ttu-id="5fcb7-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="5fcb7-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="5fcb7-108">Güçlü ad anahtarı içeren dosyanın adı.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fcb7-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5fcb7-109">Remarks</span></span>  
 <span data-ttu-id="5fcb7-110">Bu seçenek kullanıldığında, derleyici ortak anahtarı belirtilen dosyadan derleme bildirimine ekler ve ardından son derlemeyi özel anahtarıyla imzalar.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="5fcb7-111">Bir anahtar dosyası oluşturmak için sn -k yazın `file` komut satırında.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="5fcb7-112">İle derleme yaparsanız **/target: Module**, anahtar dosyasının adı modülde tutulur ve bir derleme derlediğinizde oluşturduğunuz derlemesini birleştirilmiş [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fcb7-112">If you compile with **/target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5fcb7-113">Derleyici ile şifreleme bilgilerinizi geçirebilirsiniz [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fcb7-113">You can also pass your encryption information to the compiler with [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="5fcb7-114">Kullanım [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) kısmen imzalı bir derleme istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="5fcb7-115">/ Keyfile hem de/keycontainer (komut satırı seçeneği veya özel özniteliği tarafından) aynı derlemede belirtilmesi durumunda, derleyici ilk anahtar kapsayıcısı deneyin.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-115">In case both /keyfile and /keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="5fcb7-116">Bu başarılı olursa, derleme anahtar kapsayıcısı içindeki bilgilerle imzalanır.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="5fcb7-117">Derleyici anahtar kapsayıcısını bulamazsa/keyfile ile belirtilen dosyayı çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-117">If the compiler does not find the key container, it will try the file specified with /keyfile.</span></span> <span data-ttu-id="5fcb7-118">Bu başarılı olursa, derleme anahtar dosyası içindeki bilgilerle imzalanır ve anahtar bilgileri anahtar kapsayıcısında yüklenecek (sn benzer -i) sonraki derlemede anahtar kapsayıcısı geçerli olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="5fcb7-119">Bir anahtar dosyası yalnızca ortak anahtar içerebileceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="5fcb7-120">Daha fazla bilgi için bkz: [bkz](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) ve [Gecikmeli bir derleme imzalama](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="5fcb7-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5fcb7-121">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="5fcb7-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5fcb7-122">Açık **özellikleri** projesi için sayfa.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-122">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="5fcb7-123">Tıklatın **imzalama** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-123">Click the **Signing** property page.</span></span>  
  
3.  <span data-ttu-id="5fcb7-124">Değiştirme **güçlü ad anahtar dosyası seçin** özelliği.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="5fcb7-125">Bu derleyici seçeneği ile program aracılığıyla erişebilirsiniz <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fcb7-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5fcb7-126">See Also</span></span>  
 [<span data-ttu-id="5fcb7-127">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="5fcb7-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5fcb7-128">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="5fcb7-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)