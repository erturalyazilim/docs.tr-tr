---
title: "COM Birlikte Çalışması Özel Durumlarını İşleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bc3e01bc8ca463460ede9544d1d5c095c39a59d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="handling-com-interop-exceptions"></a>COM Birlikte Çalışması Özel Durumlarını İşleme
Yönetilen ve yönetilmeyen kod birlikte özel durumları işleme çalışabilirsiniz. Bir yöntem yönetilen kodda bir özel durum oluşturursa, ortak dil çalışma zamanı için bir COM nesnesi HRESULT geçirebilirsiniz. HRESULT hata döndürerek yönetilmeyen kodunda bir yöntem başarısız olursa, çalışma zamanı tarafından yönetilen kod görevinde bir özel durum oluşturur.  
  
 Çalışma zamanı COM birlikte çalışma HRESULT ayrıntılı özel durumlar otomatik olarak eşlenir. Örneğin, E_ACCESSDENIED hale <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY hale <xref:System.OutOfMemoryException>ve benzeri.  
  
 Özel bir sonuç HRESULT ise veya çalışma zamanına bilinmiyorsa, çalışma zamanı genel geçirir <xref:System.Runtime.InteropServices.COMException> istemciye. **ErrorCode** özelliği **COMException** HRESULT değeri içerir.  
  
## <a name="working-with-ierrorinfo"></a>IErrorInfo ile çalışma  
 Bir hata, yönetilen kod için COM geçirildiğinde, çalışma zamanı özel durum nesnesi hata bilgilerle doldurur. IErrorInfo destekleyen ve HRESULTS dönüş COM nesneleri yönetilen kod özel durumlar için bu bilgileri sağlar. Örneğin, çalışma zamanı özel durumun COM hatadan açıklamayı eşlemeleri <xref:System.Exception.Message%2A> özelliği. HRESULT ek hata bilgisi sağlarsa, çalışma zamanı birçok özel durumun özellikleri varsayılan değerlerle doldurur.  
  
 Yönetilmeyen kod içinde bir yöntem başarısız olursa, bir özel durum bir yönetilen kod kesimi geçirilebilir. Konu [HRESULTS ve özel durumları](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) nasıl HRESULTS çalışma zamanı özel durum nesnelere eşleme gösteren bir tablo içeriyor.  

## <a name="see-also"></a>Ayrıca Bkz.
[Özel durumlar](index.md) 
