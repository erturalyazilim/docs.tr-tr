---
title: "System.Net.PeerToPeer.Collaboration Namespace hakkında"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 696b1d3dd7312b52c28f11f64f007c29fb8a94b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a><span data-ttu-id="fddc6-102">System.Net.PeerToPeer.Collaboration Namespace hakkında</span><span class="sxs-lookup"><span data-stu-id="fddc6-102">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>
<span data-ttu-id="fddc6-103"><xref:System.Net.PeerToPeer.Collaboration> Ad alanı, sınıflar ve eşler arası işbirliği altyapısı kullanarak eş işbirliği etkinlikleri uygulamak için kullanılan API'ler sağlar.</span><span class="sxs-lookup"><span data-stu-id="fddc6-103">The <xref:System.Net.PeerToPeer.Collaboration> namespace provides classes and APIs that are used to implement peer collaboration activities using the Peer-to-Peer Collaboration Infrastructure.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="fddc6-104">Sınıflar</span><span class="sxs-lookup"><span data-stu-id="fddc6-104">Classes</span></span>  
 <span data-ttu-id="fddc6-105">Bir eşler arası işbirliği etkinlik uygulamasında kullanılan ana sınıfları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="fddc6-105">The main classes used in the implementation of a Peer-to-Peer Collaboration activity are:</span></span>  
  
-   <span data-ttu-id="fddc6-106"><xref:System.Net.PeerToPeer.Collaboration.ContactManager>, Eş kişileri depolamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fddc6-106">The <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, which can be used to store peer contacts.</span></span>  
  
-   <span data-ttu-id="fddc6-107"><xref:System.Net.PeerToPeer.Collaboration.PeerApplication> , Oyun, sohbet istemcisi veya konferans çözüm gibi işbirliği yapmak üzere.</span><span class="sxs-lookup"><span data-stu-id="fddc6-107">The <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> in which to collaborate, such as a game, chat client, or conferencing solution.</span></span>  
  
-   <span data-ttu-id="fddc6-108">Bir etkinlik işbirliği eşler.</span><span class="sxs-lookup"><span data-stu-id="fddc6-108">The peers that will be collaborating in an activity.</span></span>  <span data-ttu-id="fddc6-109">Bu eşlerden olarak temsil edilebilir <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, veya <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="fddc6-109">These peers can be represented as <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, or <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> objects.</span></span>  
  
-   <span data-ttu-id="fddc6-110">Statik <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sınıfının kendisini hangi uygulamaların kullanılabilir olduğunu belirtir ve hangi eşlerin katılmasını bunları.</span><span class="sxs-lookup"><span data-stu-id="fddc6-110">The static <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> class itself, which specifies which applications are available and which peers are participating in them.</span></span>  
  
 <span data-ttu-id="fddc6-111"><xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> Yöntemleri işbirliği oturumunu eşlere davet etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fddc6-111">The <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> methods are used to invite peers to a collaboration session.</span></span>  <span data-ttu-id="fddc6-112">Bir arama eş başka bir eşler arası uygulama, nesne veya iletişim durumu bilgilerini sinyal güncelleştirmeleri işbirliği oturumla bağlı olaylar için abone olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fddc6-112">A calling peer can subscribe to another peer for events that signal updates to application, object, or presence information affiliated with the collaboration session.</span></span> <span data-ttu-id="fddc6-113">Varlığı sınıflar belirtin olup bir <xref:System.Net.PeerToPeer.Collaboration.Peer> işbirliği için kullanılabilir ve <xref:System.Net.PeerToPeer.Collaboration.PeerScope> sınıfı bir eş için ne kadar katılım izin verildiğini belirtmek için kullanılır: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (Genel) <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (alt ağ) veya <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span><span class="sxs-lookup"><span data-stu-id="fddc6-113">Presence classes specify whether a <xref:System.Net.PeerToPeer.Collaboration.Peer> is available for collaboration, and the <xref:System.Net.PeerToPeer.Collaboration.PeerScope> class is used to specify how much participation is allowed for a peer:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) or <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span></span>  
  
 <span data-ttu-id="fddc6-114">İşbirliği oturumunu dört adımdan oluşur:</span><span class="sxs-lookup"><span data-stu-id="fddc6-114">A collaboration session is comprised of four steps:</span></span>  
  
-   <span data-ttu-id="fddc6-115">Bulma.</span><span class="sxs-lookup"><span data-stu-id="fddc6-115">Discovery.</span></span> <span data-ttu-id="fddc6-116">Bul veya uygulamalar, eşlerdeki ve iletişim durumu bilgilerini yayımlayın.</span><span class="sxs-lookup"><span data-stu-id="fddc6-116">Discover or publish applications, peers, and presence information.</span></span>  <span data-ttu-id="fddc6-117">Örneğin, aynı oyunlar yüklü olan diğer kişiler yerel alt ağda bulun.</span><span class="sxs-lookup"><span data-stu-id="fddc6-117">For instance, find other people on the local subnet that have the same games installed.</span></span>  
  
-   <span data-ttu-id="fddc6-118">Davet.</span><span class="sxs-lookup"><span data-stu-id="fddc6-118">Invitation.</span></span> <span data-ttu-id="fddc6-119">Gönderme ve Başlat veya katılmak uzak peer(s) için güvenli davetlerini kabul <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> oturumları.</span><span class="sxs-lookup"><span data-stu-id="fddc6-119">Send and accept secure invitations for remote peer(s) to start or join <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sessions.</span></span>  
  
-   <span data-ttu-id="fddc6-120">Yönetim başvurun.</span><span class="sxs-lookup"><span data-stu-id="fddc6-120">Contact Management.</span></span> <span data-ttu-id="fddc6-121">Bir kişiye olarak keşfedilen eş eklemek bir <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span><span class="sxs-lookup"><span data-stu-id="fddc6-121">Add discovered peers as a contact to a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span></span>  
  
-   <span data-ttu-id="fddc6-122">İletişim.</span><span class="sxs-lookup"><span data-stu-id="fddc6-122">Communication.</span></span> <span data-ttu-id="fddc6-123">İletişimi kurulduğunda kullanmak <xref:System.Net> API'leri, <xref:System.Net.PeerToPeer> API ya da çok taraflı iletişimler için Windows Communication Foundation eş kanalı sınıfları.</span><span class="sxs-lookup"><span data-stu-id="fddc6-123">When communication is established, use the <xref:System.Net> APIs, the <xref:System.Net.PeerToPeer> API, or the Windows Communication Foundation Peer Channel classes for multiparty communications.</span></span>  
  
 <span data-ttu-id="fddc6-124">Örneğin, ana bilgisayar eş işbirliği oturumu başlatır ve yararlanan <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> uzaktaki bir eş ve yerel eşlerine birini konak eş Contact Manager'a ekleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="fddc6-124">For example, the host peer starts a collaboration session, and utilizes the <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> method to add a remote peer and one of its local peers to the Contact Manager of the host peer.</span></span>  <span data-ttu-id="fddc6-125">Üç kullanıcı daha sonra kendi özel işbirliği oturumunda almayacak.</span><span class="sxs-lookup"><span data-stu-id="fddc6-125">The three users will then participate in their own private collaboration session.</span></span>  
  
 <span data-ttu-id="fddc6-126">Tipik P2P uygulamalar: konferans aramaları işbirliği not alma ya da whiteboarding, sunucusuz sohbet uygulamalar, etkileşimli reklamlar ve çevrimiçi oyunlar oturumları için.</span><span class="sxs-lookup"><span data-stu-id="fddc6-126">Typical P2P applications are: conference calls for collaborative note-taking or whiteboarding, serverless chat applications, interactive advertisements, and online gaming sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fddc6-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fddc6-127">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Collaboration>