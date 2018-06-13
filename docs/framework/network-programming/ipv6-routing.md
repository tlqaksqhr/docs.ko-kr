---
title: IPv6 라우팅
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c3e2662eb444c70d2376a05e44ac84f472f27384
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397808"
---
# <a name="ipv6-routing"></a><span data-ttu-id="7a8f2-102">IPv6 라우팅</span><span class="sxs-lookup"><span data-stu-id="7a8f2-102">IPv6 Routing</span></span>
<span data-ttu-id="7a8f2-103">유연한 라우팅 메커니즘은 IPv6의 장점입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="7a8f2-104">IPv4 네트워크 ID가 할당된 방식으로 인해 인터넷 백본에 있는 라우터에서 대규모 라우팅 테이블을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="7a8f2-105">이러한 라우터는 인터넷의 모든 노드로 방향이 지정되는 패킷을 전달하기 위해 모든 경로를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="7a8f2-106">주소를 집계하는 기능을 통해 IPv6에서는 유연하게 주소를 지정할 수 있고 라우팅 테이블의 크기가 대폭 감소됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="7a8f2-107">이 새로운 주소 지정 아키텍처에서는 적절하게 메시지를 전달하기 위해 중간 라우터를 통해 네트워크의 로컬 부분만 계속 추적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="7a8f2-108">네트워크 환경 검색</span><span class="sxs-lookup"><span data-stu-id="7a8f2-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="7a8f2-109">네트워크 환경 검색에서 제공하는 일부 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
-   <span data-ttu-id="7a8f2-110">라우터 검색.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-110">Router discovery.</span></span> <span data-ttu-id="7a8f2-111">이 기능을 통해 로컬 라우터를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-111">This allows hosts to identify local routers.</span></span>  
  
-   <span data-ttu-id="7a8f2-112">주소 확인.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-112">Address resolution.</span></span> <span data-ttu-id="7a8f2-113">이 기능을 사용하면 노드에서 올바른 다음 홉 주의 링크-계층 주소를 확인할 수 있습니다(주소 확인 프로토콜 [ARP] 대체).</span><span class="sxs-lookup"><span data-stu-id="7a8f2-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
-   <span data-ttu-id="7a8f2-114">주소 자동 구성.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-114">Address auto-configuration.</span></span> <span data-ttu-id="7a8f2-115">이 기능을 사용하면 호스트에서 사이트-로컬 및 글로벌 주소를 자동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="7a8f2-116">네트워크 환경 검색에서는 다음을 포함하는 ICMPv6(Internet Control Message Protocol for IPv6) 메시지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
-   <span data-ttu-id="7a8f2-117">라우터 알림.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-117">Router advertisement.</span></span> <span data-ttu-id="7a8f2-118">의사(pseudo) 주기적으로 또는 라우터 요청에 대한 응답으로 라우터에서 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="7a8f2-119">IPv6 라우터에서는 라우터 알림을 사용하여 가용성, 주소 접두사 및 다른 매개 변수를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
-   <span data-ttu-id="7a8f2-120">라우터 요청.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-120">Router solicitation.</span></span> <span data-ttu-id="7a8f2-121">링크의 라우터에서 라우터 알림을 즉시 보내도록 요청하기 위해 호스트에서 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
-   <span data-ttu-id="7a8f2-122">네트워크 환경 요청.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-122">Neighbor solicitation.</span></span> <span data-ttu-id="7a8f2-123">주소 확인, 중복 주소 검색 또는 네트워크 환경이 여전히 연결할 수 있는지 확인하기 위해 노드에서 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
-   <span data-ttu-id="7a8f2-124">네트워크 환경 알림.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-124">Neighbor advertisement.</span></span> <span data-ttu-id="7a8f2-125">네트워크 환경 요청에 응답하거나 링크 계층 주소 변경을 네트워크 환경에 알리기 위해 노드에서 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
-   <span data-ttu-id="7a8f2-126">리디렉션.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-126">Redirect.</span></span> <span data-ttu-id="7a8f2-127">전송 노드의 특정 대상으로 더 유용한 다음 홉 주소를 알리기 위해 라우터에서 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8f2-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8f2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a8f2-128">See Also</span></span>  
 [<span data-ttu-id="7a8f2-129">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="7a8f2-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="7a8f2-130">소켓</span><span class="sxs-lookup"><span data-stu-id="7a8f2-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
