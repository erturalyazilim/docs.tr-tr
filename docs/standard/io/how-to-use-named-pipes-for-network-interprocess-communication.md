---
title: "Nasıl yapılır: Ağ İşlemler Arası İletişimi için Adlandırılmış Kanallar Kullanma"
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
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="dec66-102">Nasıl yapılır: Ağ İşlemler Arası İletişimi için Adlandırılmış Kanallar Kullanma</span><span class="sxs-lookup"><span data-stu-id="dec66-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="dec66-103">Adlandırılmış kanallar, bir kanal sunucusu ve bir veya daha fazla kanal istemcisi arasındaki işlemler arası iletişimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="dec66-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="dec66-104">Bunlar, yerel bir bilgisayarda işlemler arası iletişim sağlayan anonim kanallardan daha fazla işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="dec66-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="dec66-105">Adlandırılmış kanallar, bağlantı işlemlerinin uzak sunucularda kendi izin setlerini kullanmasını sağlayan bir ağ ve birden çok sunucu örneği, ileti tabanlı iletişim ve istemci kimliğine bürünme üzerinden tam çift yönlü iletişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="dec66-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="dec66-106">Adlandırılmış kanalları uygulamak için <xref:System.IO.Pipes.NamedPipeServerStream> ve <xref:System.IO.Pipes.NamedPipeClientStream> sınıflarını kullanın.</span><span class="sxs-lookup"><span data-stu-id="dec66-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dec66-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="dec66-107">Example</span></span>  
 <span data-ttu-id="dec66-108">Aşağıdaki örnek, <xref:System.IO.Pipes.NamedPipeServerStream> sınıfını kullanarak adlandırılmış bir kanalın nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="dec66-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="dec66-109">Bu örnekte, sunucu işlemi dört iş parçacığı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="dec66-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="dec66-110">Her bir iş parçacığı bir istemci bağlantısını kabul edebilir.</span><span class="sxs-lookup"><span data-stu-id="dec66-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="dec66-111">Daha sonra bağlı istemci işlemi sunucuya bir dosya adı sağlar.</span><span class="sxs-lookup"><span data-stu-id="dec66-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="dec66-112">Eğer istemci yeterli izinlere sahipse, sunucu işlemi dosyayı açar ve dosya içeriğini istemciye geri gönderir.</span><span class="sxs-lookup"><span data-stu-id="dec66-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="dec66-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="dec66-113">Example</span></span>  
 <span data-ttu-id="dec66-114">Aşağıdaki örnekte <xref:System.IO.Pipes.NamedPipeClientStream> sınıfını kullanan istemci işlemi gösterilir.</span><span class="sxs-lookup"><span data-stu-id="dec66-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="dec66-115">İstemci sunucu işlemine bağlanır ve sunucuya bir dosya adı gönderir.</span><span class="sxs-lookup"><span data-stu-id="dec66-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="dec66-116">Örnek kimliğe bürünme kullanır, bu nedenle istemci uygulamasını çalıştıran kimliğin dosyaya erişim izni olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="dec66-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="dec66-117">Ardından sunucu, dosyanın içeriğini istemciye geri gönderir.</span><span class="sxs-lookup"><span data-stu-id="dec66-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="dec66-118">Dosya içerikleri daha sonra konsolda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dec66-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="dec66-119">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="dec66-119">Robust Programming</span></span>  
 <span data-ttu-id="dec66-120">Bu örnekte istemci ve sunucu işlemlerinin aynı bilgisayarda çalışması amaçlanmıştır, bu nedenle <xref:System.IO.Pipes.NamedPipeClientStream> nesnesine sağlanan sunucu adı `"."`'dir.</span><span class="sxs-lookup"><span data-stu-id="dec66-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="dec66-121">Eğer istemci ve sunucu işlemleri ayrı bilgisayarlarda olsaydı `"."`, sunucu işlemini çalıştıran bilgisayarın ağ adı yerine geçecekti.</span><span class="sxs-lookup"><span data-stu-id="dec66-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec66-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dec66-122">See Also</span></span>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [<span data-ttu-id="dec66-123">Kanallar</span><span class="sxs-lookup"><span data-stu-id="dec66-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="dec66-124">Nasıl yapılır: yerel işlemler arası iletişim için anonim kanallar kullanma</span><span class="sxs-lookup"><span data-stu-id="dec66-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)