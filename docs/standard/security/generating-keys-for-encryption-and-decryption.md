---
title: "Şifreleme ve Şifre Çözme için Anahtarlar Oluşturma"
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
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0b40e09a9a2c534d3376fa6930d8166591873a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="4202d-102">Şifreleme ve Şifre Çözme için Anahtarlar Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4202d-102">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="4202d-103">Anahtarları oluşturmak ve yönetmek, şifreleme işleminin önemli bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="4202d-103">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="4202d-104">Simetrik algoritmalar, bir anahtarın ve başlangıç vektörünün (IV) oluşturulmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="4202d-104">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="4202d-105">Anahtar, verinizin şifresini çözmemesi gereken herkesten gizli tutulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4202d-105">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="4202d-106">IV'nin gizli olması gerekmez ancak her oturum için değiştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="4202d-106">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="4202d-107">Asimetrik algoritmalar bir ortak anahtarın, bir de özel anahtarın oluşturulmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="4202d-107">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="4202d-108">Ortak anahtar herhangi birine verilebilirken, özel anahtar yalnızca ortak anahtar ile şifrelenen verilerin şifresini çözecek tarafça bilinmelidir.</span><span class="sxs-lookup"><span data-stu-id="4202d-108">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="4202d-109">Bu bölümde, hem simetrik, hem de asimetrik algoritmalar için anahtarların nasıl oluşturulacağı ve yönetileceği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4202d-109">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="4202d-110">Simetrik Anahtarlar</span><span class="sxs-lookup"><span data-stu-id="4202d-110">Symmetric Keys</span></span>  
 <span data-ttu-id="4202d-111">.NET Framework tarafından sağlanan simetrik şifreleme sınıfları, veriler üzerine şifreleme ve şifre çözme yapabilmek için bir anahtar ve yeni bir başlatma vektörü (IV) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="4202d-111">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="4202d-112">Varsayılan oluşturucuyu kullanarak yönetilen simetrik şifreleme sınıflarından birinin yeni bir örneğini oluşturduğunuzda, otomatik olarak yeni bir anahtar ve IV oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4202d-112">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the default constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="4202d-113">Verilerinizin şifresini çözmesine izin verdiğiniz kişilerin aynı anahtara ve IV'ye sahip olup aynı algoritmayı kullanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="4202d-113">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="4202d-114">Genellikle, her oturum için yeni bir anahtar ve IV oluşturulmalıdır, ve ne anahtar ne de IV daha sonraki bir oturumda kullanılmak üzere saklanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4202d-114">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="4202d-115">Bir simetrik anahtarı ve IV'yi uzaktaki bir kişiye iletmek için, genellikle simetrik anahtarı asimetrik şifreleme kullanarak şifrelersiniz.</span><span class="sxs-lookup"><span data-stu-id="4202d-115">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="4202d-116">Anahtarı güvenli olmayan bir ağ üzerinde şifrelemeden göndermek güvenli değildir, çünkü anahtarı ve IV'yi yakalayan herhangi biri verilerinizin şifresini çözebilir.</span><span class="sxs-lookup"><span data-stu-id="4202d-116">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="4202d-117">Şifreleme kullanarak veri değişimi hakkında daha fazla bilgi için bkz: [şifreleme düzeni oluşturma](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span><span class="sxs-lookup"><span data-stu-id="4202d-117">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="4202d-118">Aşağıdaki örnek, TripleDES algoritmasını uygulayan <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> sınıfının yeni bir örneğinin oluşturulmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4202d-118">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="4202d-119">Önceki kod çalıştırıldığında yeni bir anahtar ve IV yaratılır ve bulundukları **anahtar** ve **IV** özellikleri, sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="4202d-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="4202d-120">Bazen birden çok anahtar oluşturmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="4202d-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="4202d-121">Bu durumda, bir Simetrik algoritma uygulayan bir sınıf yeni bir örneğini oluşturun ve sonra da çağırarak yeni bir anahtar ve IV oluşturun **GenerateKey** ve **GenerateIV** yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="4202d-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="4202d-122">Aşağıdaki kod örneği, asimetrik şifreleme sınıfının yeni bir örneği oluşturulduktan sonra yeni anahtar ve IV'lerin nasıl oluşturulduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="4202d-122">The following code example illustrates how to create new keys and IVs after a new instance of the asymmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
TDES.GenerateIV()  
TDES.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
TDES.GenerateIV();  
TDES.GenerateKey();  
```  
  
 <span data-ttu-id="4202d-123">Önceki kod yürütüldüğünde, bir anahtar ve IV oluşturulan zaman yeni bir örneğini **TripleDESCryptoServiceProvider** yapılır.</span><span class="sxs-lookup"><span data-stu-id="4202d-123">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="4202d-124">Başka bir anahtar IV ne zaman oluşturulduğunu ve **GenerateKey** ve **GenerateIV** yöntemleri çağrılır.</span><span class="sxs-lookup"><span data-stu-id="4202d-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="4202d-125">Asimetrik Anahtarlar</span><span class="sxs-lookup"><span data-stu-id="4202d-125">Asymmetric Keys</span></span>  
 <span data-ttu-id="4202d-126">.NET Framework, asimetrik şifreleme için <xref:System.Security.Cryptography.RSACryptoServiceProvider> ve <xref:System.Security.Cryptography.DSACryptoServiceProvider> sınıflarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="4202d-126">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="4202d-127">Bu sınıflar, yeni bir örnek oluşturmak için varsayılan oluşturucuyu kullandığınızda bir ortak/özel anahtar çifti oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4202d-127">These classes create a public/private key pair when you use the default constructor to create a new instance.</span></span> <span data-ttu-id="4202d-128">Asimetrik anahtarlar birden çok oturumda kullanılmak üzere saklanabilir ya da yalnızca tek bir oturum için oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="4202d-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="4202d-129">Ortak anahtar genel olarak kullanılabilir olabilse de, özel anahtar dikkatle korunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4202d-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="4202d-130">Bir asimetrik sınıfın her yeni örneği oluşturulduğunda bir ortak/özel anahtar çifti oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4202d-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="4202d-131">Sınıfın yeni bir örneği oluşturulduktan sonra, anahtar bilgileri şu iki yöntemden biriyle alınabilir:</span><span class="sxs-lookup"><span data-stu-id="4202d-131">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
-   <span data-ttu-id="4202d-132"><xref:System.Security.Cryptography.RSA.ToXmlString%2A> Anahtar bilgileri XML gösterimini döndürür yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4202d-132">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
-   <span data-ttu-id="4202d-133">Anahtar bilgilerini tutan bir <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> yapısı döndüren <xref:System.Security.Cryptography.RSAParameters> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4202d-133">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="4202d-134">İki yöntem de yalnızca ortak anahtar bilgisinin mi dönüleceğini yoksa hem ortak anahtar hem de özel anahtar bilgisinin mi dönüleceğini belirten bir Boolean değerini kabul eder.</span><span class="sxs-lookup"><span data-stu-id="4202d-134">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="4202d-135">Bir **RSACryptoServiceProvider** sınıfı değerine başlatılabilir bir **RSAParameters** kullanarak yapısı <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4202d-135">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="4202d-136">Asimetrik özel anahtarlar yerel bilgisayarda asla oldukları gibi veya düz metin olarak tutulmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="4202d-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="4202d-137">Özel anahtarı depolamanız gerekiyorsa, bir anahtar kapsayıcısı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4202d-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="4202d-138">Bir anahtar kapsayıcısında özel anahtar depolama konusunda daha fazla bilgi için bkz: [nasıl yapılır: bir anahtar kapsayıcısında asimetrik anahtarlar depolama](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="4202d-138">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="4202d-139">Aşağıdaki kod örneğinde yeni bir örneğini oluşturur **RSACryptoServiceProvider** sınıfı, bir ortak/özel anahtar çifti oluşturma ve ortak anahtar bilgileri kaydeden bir **RSAParameters** yapısı.</span><span class="sxs-lookup"><span data-stu-id="4202d-139">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim RSA as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim RSAKeyInfo As RSAParameters = RSA.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters RSAKeyInfo = RSA.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4202d-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4202d-140">See Also</span></span>  
 [<span data-ttu-id="4202d-141">Veri şifreleme</span><span class="sxs-lookup"><span data-stu-id="4202d-141">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
 [<span data-ttu-id="4202d-142">Verilerin şifresini çözme</span><span class="sxs-lookup"><span data-stu-id="4202d-142">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
 [<span data-ttu-id="4202d-143">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="4202d-143">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="4202d-144">Nasıl yapılır: bir anahtar kapsayıcısında asimetrik anahtarlar depolama</span><span class="sxs-lookup"><span data-stu-id="4202d-144">How to: Store Asymmetric Keys in a Key Container</span></span>](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)