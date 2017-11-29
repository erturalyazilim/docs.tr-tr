---
title: "Nasıl Yapılır: Bekleme Tanıtıcıları İçeren İptal İsteklerini Dinleme"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="e20db-102">Nasıl Yapılır: Bekleme Tanıtıcıları İçeren İptal İsteklerini Dinleme</span><span class="sxs-lookup"><span data-stu-id="e20db-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="e20db-103">Bir olay bildirilmesini bekleyen sırada bir yöntem engellenirse, bu iptal belirteci değerini denetleyin ve zamanında yanıt.</span><span class="sxs-lookup"><span data-stu-id="e20db-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="e20db-104">İlk örnek gibi olaylar ile çalışırken bu sorunu çözmek gösterilmiştir <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> yerel olarak desteklemeyen birleşik iptal framework.</span><span class="sxs-lookup"><span data-stu-id="e20db-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="e20db-105">İkinci örnek kullanır daha kolay bir yaklaşım gösterir <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, iptal birleşik hangi desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="e20db-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e20db-106">"Sadece kendi kodumu" etkinleştirildiğinde, Visual Studio bazı durumlarda, özel durum oluşturur satır başı ve "özel durum kullanıcı kodu tarafından işlenmiyor." diyen bir hata iletisi görüntülenir</span><span class="sxs-lookup"><span data-stu-id="e20db-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="e20db-107">Bu hata zararsız kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="e20db-107">This error is benign.</span></span> <span data-ttu-id="e20db-108">Buradan devam etmek için F5 tuşuna basın ve aşağıdaki örneklerde gösterildiği özel durum işleme davranışı bakın.</span><span class="sxs-lookup"><span data-stu-id="e20db-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="e20db-109">Visual Studio ilk hatada kesilmesini önlemek için yalnızca altında "Sadece kendi kodumu" onay kutusunun işaretini **Araçlar, seçenekleri, hata ayıklama, genel**.</span><span class="sxs-lookup"><span data-stu-id="e20db-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e20db-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="e20db-110">Example</span></span>  
 <span data-ttu-id="e20db-111">Aşağıdaki örnek kullanan bir <xref:System.Threading.ManualResetEvent> birleştirilmiş iptal desteklemeyen bekleme tanıtıcıları engelini kaldırma göstermek için.</span><span class="sxs-lookup"><span data-stu-id="e20db-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="e20db-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="e20db-112">Example</span></span>  
 <span data-ttu-id="e20db-113">Aşağıdaki örnek kullanan bir <xref:System.Threading.ManualResetEventSlim> koordinasyon engelini kaldırma göstermek için destek temelleri iptal birleşik.</span><span class="sxs-lookup"><span data-stu-id="e20db-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="e20db-114">Diğer basit koordinasyon temelleri ile aynı yaklaşımı gibi kullanılabilir <xref:System.Threading.Semaphore> `Slim` ve <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="e20db-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="e20db-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e20db-115">See Also</span></span>  
 [<span data-ttu-id="e20db-116">Yönetilen iş parçacıklarında iptal</span><span class="sxs-lookup"><span data-stu-id="e20db-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)