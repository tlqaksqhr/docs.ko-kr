---
title: 피어 투 피어 공동 작업
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a933c81105399a9411fcb749a06e47bf769cf532
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="peer-to-peer-collaboration"></a><span data-ttu-id="8a0f2-102">피어 투 피어 공동 작업</span><span class="sxs-lookup"><span data-stu-id="8a0f2-102">Peer-to-Peer Collaboration</span></span>
<span data-ttu-id="8a0f2-103">피어 투 피어 네트워킹은 인터넷의 에지에서 클라이언트 기반 컴퓨팅 작업 이상을 수행하는 비교적 강력한 컴퓨터(개인용 컴퓨터)를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-103">Peer-to-peer networking is the utilization of the relatively powerful computers (personal computers) that exist at the edge of the Internet for more than just client-based computing tasks.</span></span> <span data-ttu-id="8a0f2-104">최신 개인용 컴퓨터(PC)에는 매우 빠른 프로세서, 광대한 메모리 및 대형 하드 디스크가 있으며, 이러한 리소스는 이메일과 웹 검색 등의 일반적인 컴퓨팅 작업을 수행할 때 완전히 이용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-104">The modern personal computer (PC) has a very fast processor, vast memory, and a large hard disk, none of which are being fully utilized when performing common computing tasks such as email and Web browsing.</span></span> <span data-ttu-id="8a0f2-105">최신 PC는 여러 형식의 응용 프로그램을 위한 서버(피어) 및 클라이언트로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-105">The modern PC can easily act as both a client and server (a peer) for many types of applications.</span></span>  
  
-   <span data-ttu-id="8a0f2-106">피어 투 피어 공동 작업 인프라는 Windows Vista 이상 플랫폼에서 주변 사람 찾기 서비스를 활용하는 Microsoft Windows 피어 투 피어 인프라의 간단한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-106">The Peer-to-Peer Collaboration Infrastructure is a simplified implementation of the Microsoft Windows Peer-to-Peer Infrastructure that leverages the People Near Me service in Windows Vista and later platforms.</span></span> <span data-ttu-id="8a0f2-107">인터넷 끝점과 연락처의 서비스도 제공할 수 있지만, 주변 사람 찾기 서비스가 작동하는 서브넷에서 피어 지원 응용 프로그램용으로 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-107">It is best used for peer-enabled applications within a subnet for which the People Near Me service operates, although it can service internet endpoints or contacts as well.</span></span> <span data-ttu-id="8a0f2-108">연락처 끝점, 가용성 및 현재 상태를 확인하기 위해 Live Messenger 및 기타 Live 인식 응용 프로그램에서 사용하는 일반적인 연락처 관리자를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-108">It incorporates the common Contact Manager that is used by Live Messenger and other Live-aware applications to determine contact endpoints, availability, and presence.</span></span>  
  
-  
  
## <a name="collaboration-applications"></a><span data-ttu-id="8a0f2-109">공동 작업 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8a0f2-109">Collaboration Applications</span></span>  
 <span data-ttu-id="8a0f2-110">일반적인 피어 투 피어 공동 작업 응용 프로그램은 다음 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-110">A typical peer-to-peer collaboration application is comprised of the following steps:</span></span>  
  
-   <span data-ttu-id="8a0f2-111">피어는 공동 작업 세션을 호스트하려는 피어의 ID를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-111">Peer determines the identity of a peer who is interested in hosting a collaboration session</span></span>  
  
-   <span data-ttu-id="8a0f2-112">세션을 호스트하기 위한 요청을 보내면 호스트 피어가 공동 작업 활동을 관리하도록 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-112">A request to host a session is sent, somehow, and the host peer agrees to manage collaboration activity.</span></span>  
  
-   <span data-ttu-id="8a0f2-113">호스트에서 서브넷의 연락처(요청자 포함)를 세션에 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-113">The host invites contacts on the subnet (including the requestor) to a session.</span></span>  
  
-   <span data-ttu-id="8a0f2-114">공동 작업하려는 모든 피어가 해당 연락처 관리자에 호스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-114">All peers who want to collaborate may add the host to their contact managers.</span></span>  
  
-   <span data-ttu-id="8a0f2-115">대부분의 피어는 승인 또는 거부 여부에 상관없이 시기적절하게 호스트 피어에게 초대에 대한 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-115">Most peers will send invitation responses, whether accepted or declined, back to the host peer in a timely fashion.</span></span>  
  
-   <span data-ttu-id="8a0f2-116">공동 작업하려는 모든 피어는 호스트 피어에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-116">All peers who want to collaborate will subscribe to the host peer.</span></span>  
  
-   <span data-ttu-id="8a0f2-117">피어가 초기 공동 작업을 수행하는 동안 호스트 피어가 연락처 관리자에 원격 피어를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-117">While the peers are performing their initial collaboration activity, the host peer may add remote peers to its contact manager.</span></span> <span data-ttu-id="8a0f2-118">또한 승인, 거부 및 응답하지 않은 사람을 판별하기 위해 모든 초대 응답도 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-118">It also processes all invitation responses to determine who has accepted, who has declined, and who has not answered.</span></span>  <span data-ttu-id="8a0f2-119">응답하지 않은 사람에 대한 초대는 취소하거나 다른 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-119">It may cancel invitations to those who have not answered, or perform some other activity.</span></span>  
  
-   <span data-ttu-id="8a0f2-120">이때 호스트 피어는 초대된 모든 피어와 공동 작업 세션을 시작하거나 응용 프로그램을 공동 작업 인프라에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-120">At this point, the host peer can start a collaboration session with all invited peers, or register an application with the collaboration infrastructure.</span></span>  <span data-ttu-id="8a0f2-121">P2P 응용 프로그램에서는 피어 투 피어 공동 작업 인프라와 <xref:System.Net.PeerToPeer.Collaboration> 네임스페이스를 사용하여 게임, 게시판, 회의 및 기타 서버가 없는 현재 상태 응용 프로그램의 통신을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-121">P2P applications use the Peer-to-Peer Collaboration Infrastructure and the <xref:System.Net.PeerToPeer.Collaboration> namespace to coordinate communications for games, bulletin boards, conferencing, and other serverless presence applications.</span></span>  
  
-  
  
## <a name="peer-to-peer-networking-security"></a><span data-ttu-id="8a0f2-122">피어 투 피어 네트워킹 보안</span><span class="sxs-lookup"><span data-stu-id="8a0f2-122">Peer-to-Peer Networking Security</span></span>  
 <span data-ttu-id="8a0f2-123">Active Directory 도메인에서 도메인 컨트롤러는 Kerberos를 사용하여 인증 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-123">In an Active Directory domain, domain controllers provide authentication services using Kerberos.</span></span> <span data-ttu-id="8a0f2-124">서버 없는 피어 환경에서 피어는 자체 인증을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-124">In a serverless peer environment, the peers must provide their own authentication.</span></span> <span data-ttu-id="8a0f2-125">피어 투 피어 네트워킹의 경우 노드는 CA 역할을 수행할 수 있으므로, 각 피어의 신뢰할 수 있는 루트 저장소에서 루트 인증서의 요구 사항을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-125">For Peer-to-Peer Networking, any node can act as a CA, removing the requirement of a root certificate in each peer's trusted root store.</span></span> <span data-ttu-id="8a0f2-126">인증은 X.509 인증서 형식의 자체 서명된 인증서를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-126">Authentication is provided using self-signed certificates, formatted as X.509 certificates.</span></span> <span data-ttu-id="8a0f2-127">이러한 인증서는 공개 키/개인 키 쌍을 생성하고 개인 키를 사용하여 서명된 인증서를 생성하는 각 피어가 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-127">These are certificates that are created by each peer, which generates the public key/private key pair and the certificate that is signed using the private key.</span></span> <span data-ttu-id="8a0f2-128">자체 서명된 인증서는 피어 엔터티에 대한 정보를 제공하고 인증을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-128">The self-signed certificate is used for authentication and to provide information about the peer entity.</span></span> <span data-ttu-id="8a0f2-129">X.509 인증과 마찬가지로 피어 네트워킹 인증은 신뢰할 수 있는 공개 키로 다시 추적되는 일련의 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0f2-129">Like X.509 authentication, peer networking authentication relies upon a chain of certificates tracing back to a public key that is trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0f2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a0f2-130">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Collaboration>  
 [<span data-ttu-id="8a0f2-131">System.Net.PeerToPeer.Collaboration 네임스페이스 정보</span><span class="sxs-lookup"><span data-stu-id="8a0f2-131">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)
