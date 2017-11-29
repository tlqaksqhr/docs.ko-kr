---
title: "System.Net.PeerToPeer.Collaboration 네임스페이스 정보"
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
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a><span data-ttu-id="fb106-102">System.Net.PeerToPeer.Collaboration 네임스페이스 정보</span><span class="sxs-lookup"><span data-stu-id="fb106-102">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>
<span data-ttu-id="fb106-103"><xref:System.Net.PeerToPeer.Collaboration> 네임스페이스는 피어 투 피어 공동 작업 인프라를 사용하여 피어 공동 작업 활동을 구현하는 데 사용되는 클래스 및 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-103">The <xref:System.Net.PeerToPeer.Collaboration> namespace provides classes and APIs that are used to implement peer collaboration activities using the Peer-to-Peer Collaboration Infrastructure.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="fb106-104">클래스</span><span class="sxs-lookup"><span data-stu-id="fb106-104">Classes</span></span>  
 <span data-ttu-id="fb106-105">피어 투 피어 공동 작업 구현에 사용되는 기본 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-105">The main classes used in the implementation of a Peer-to-Peer Collaboration activity are:</span></span>  
  
-   <span data-ttu-id="fb106-106"><xref:System.Net.PeerToPeer.Collaboration.ContactManager> - 피어 연락처를 저장하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-106">The <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, which can be used to store peer contacts.</span></span>  
  
-   <span data-ttu-id="fb106-107"><xref:System.Net.PeerToPeer.Collaboration.PeerApplication> - 게임, 채팅 클라이언트, 회의 솔루션 등 공동 작업하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-107">The <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> in which to collaborate, such as a game, chat client, or conferencing solution.</span></span>  
  
-   <span data-ttu-id="fb106-108">활동에서 공동 작업할 피어.</span><span class="sxs-lookup"><span data-stu-id="fb106-108">The peers that will be collaborating in an activity.</span></span>  <span data-ttu-id="fb106-109">이러한 피어는 <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> 또는 <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> 개체로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-109">These peers can be represented as <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, or <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> objects.</span></span>  
  
-   <span data-ttu-id="fb106-110">정적 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 클래스 자체 - 사용할 수 있는 응용 프로그램 및 참여하는 피어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-110">The static <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> class itself, which specifies which applications are available and which peers are participating in them.</span></span>  
  
 <span data-ttu-id="fb106-111"><xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> 메서드는 공동 작업 세션에 피어를 초대하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-111">The <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> methods are used to invite peers to a collaboration session.</span></span>  <span data-ttu-id="fb106-112">호출하는 피어는 공동 작업 세션과 연결된 응용 프로그램, 개체 또는 현재 상태 정보에 대한 업데이트를 알리는 이벤트를 위해 다른 피어를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-112">A calling peer can subscribe to another peer for events that signal updates to application, object, or presence information affiliated with the collaboration session.</span></span> <span data-ttu-id="fb106-113">현재 상태 클래스는 <xref:System.Net.PeerToPeer.Collaboration.Peer>를 공동 작업에 사용할 수 있는지 여부를 지정하고, <xref:System.Net.PeerToPeer.Collaboration.PeerScope> 클래스는 피어에 허용되는 참여 정도를 <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet>(전역), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>(서브넷) 또는 <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None> 등으로 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-113">Presence classes specify whether a <xref:System.Net.PeerToPeer.Collaboration.Peer> is available for collaboration, and the <xref:System.Net.PeerToPeer.Collaboration.PeerScope> class is used to specify how much participation is allowed for a peer:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) or <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span></span>  
  
 <span data-ttu-id="fb106-114">공동 작업 세션은 다음 네 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-114">A collaboration session is comprised of four steps:</span></span>  
  
-   <span data-ttu-id="fb106-115">검색.</span><span class="sxs-lookup"><span data-stu-id="fb106-115">Discovery.</span></span> <span data-ttu-id="fb106-116">응용 프로그램, 피어 및 현재 상태 정보를 검색하거나 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-116">Discover or publish applications, peers, and presence information.</span></span>  <span data-ttu-id="fb106-117">예를 들어 동일한 게임이 설치되어 있는 로컬 서브넷에서 다른 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-117">For instance, find other people on the local subnet that have the same games installed.</span></span>  
  
-   <span data-ttu-id="fb106-118">초대.</span><span class="sxs-lookup"><span data-stu-id="fb106-118">Invitation.</span></span> <span data-ttu-id="fb106-119">원격 피어에게 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 세션을 시작하거나 참여하라는 보안 초대를 보내고 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-119">Send and accept secure invitations for remote peer(s) to start or join <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sessions.</span></span>  
  
-   <span data-ttu-id="fb106-120">연락처 관리.</span><span class="sxs-lookup"><span data-stu-id="fb106-120">Contact Management.</span></span> <span data-ttu-id="fb106-121">검색된 피어를 <xref:System.Net.PeerToPeer.Collaboration.ContactManager>에 연락처로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-121">Add discovered peers as a contact to a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span></span>  
  
-   <span data-ttu-id="fb106-122">통신.</span><span class="sxs-lookup"><span data-stu-id="fb106-122">Communication.</span></span> <span data-ttu-id="fb106-123">통신이 설정되면 <xref:System.Net> API, <xref:System.Net.PeerToPeer> API 또는 Windows Communication Foundation 피어 채널 클래스를 다자간 통신에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-123">When communication is established, use the <xref:System.Net> APIs, the <xref:System.Net.PeerToPeer> API, or the Windows Communication Foundation Peer Channel classes for multiparty communications.</span></span>  
  
 <span data-ttu-id="fb106-124">예를 들어 호스트 피어는 공동 작업 세션을 시작하고 <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> 메서드를 활용하여 원격 피어 및 로컬 피어 중 하나를 호스트 피어의 연락처 관리자에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-124">For example, the host peer starts a collaboration session, and utilizes the <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> method to add a remote peer and one of its local peers to the Contact Manager of the host peer.</span></span>  <span data-ttu-id="fb106-125">그런 다음 세 명의 사용자가 개인 공동 작업 세션에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-125">The three users will then participate in their own private collaboration session.</span></span>  
  
 <span data-ttu-id="fb106-126">일반적인 P2P 응용 프로그램은 공동 작업 기록 또는 화이트보드 작성을 위한 전화 회의, 서버가 없는 채팅 응용 프로그램, 대화형 보급 알림, 온라인 게임 세션 등입니다.</span><span class="sxs-lookup"><span data-stu-id="fb106-126">Typical P2P applications are: conference calls for collaborative note-taking or whiteboarding, serverless chat applications, interactive advertisements, and online gaming sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb106-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb106-127">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Collaboration>
