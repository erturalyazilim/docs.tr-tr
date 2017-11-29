---
title: "Authenticode (Yönetilmeyen API Başvurusu)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e90a13ebf46f1891061c78435b7ba47d68de001d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="e0997-102">Authenticode (Yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="e0997-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="e0997-103">Authenticode XrML lisans oluşturma ve doğrulama modülü destekler.</span><span class="sxs-lookup"><span data-stu-id="e0997-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0997-104">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="e0997-104">In This Section</span></span>  
 [<span data-ttu-id="e0997-105">_Axlgetıssuerpublickeyhash işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="e0997-106">Belirtilen sertifika imzalamak için kullanılan özel anahtar ile ilişkili ortak anahtarın SHA-1 karma alır.</span><span class="sxs-lookup"><span data-stu-id="e0997-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="e0997-107">_AxlPublicKeyBlobToPublicKeyToken işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="e0997-108">Güçlü ad ve ortak anahtar belirteci CSP PUBLICKEYBLOB biçimden hesaplar.</span><span class="sxs-lookup"><span data-stu-id="e0997-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="e0997-109">_AxlRSAKeyValueToPublicKeyToken işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="e0997-110">Tanımlayıcı adlı bir ortak anahtar belirteci için bir mod ve üs dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="e0997-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="e0997-111">Certfreeauthenticodesignerınfo işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="e0997-112">Axl_authentıcode_sıgner_ınfo yapısı için ayrılan kaynakları serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="e0997-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="e0997-113">Certfreeauthenticodetimestamperınfo işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="e0997-114">Axl_authentıcode_tımestamper_ınfo yapısı için ayrılan kaynakları serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="e0997-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="e0997-115">CertTimestampAuthenticodeLicense işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="e0997-116">Zaman CertCreateAuthenticodeLicense tarafından oluşturulan bir Authenticode XrML lisans Damgalar.</span><span class="sxs-lookup"><span data-stu-id="e0997-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="e0997-117">CertVerifyAuthenticodeLicense işlevi</span><span class="sxs-lookup"><span data-stu-id="e0997-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="e0997-118">Authenticode XrML lisans geçerliliğini doğrular.</span><span class="sxs-lookup"><span data-stu-id="e0997-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="e0997-119">Axl_authentıcode_sıgner_ınfo yapısı</span><span class="sxs-lookup"><span data-stu-id="e0997-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="e0997-120">Authenticode imzalayan bilgilerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e0997-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="e0997-121">Axl_authentıcode_tımestamper_ınfo yapısı</span><span class="sxs-lookup"><span data-stu-id="e0997-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="e0997-122">Authenticode zaman stamper bilgilerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e0997-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0997-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e0997-123">See Also</span></span>  
 [<span data-ttu-id="e0997-124">Yönetilmeyen API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="e0997-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)