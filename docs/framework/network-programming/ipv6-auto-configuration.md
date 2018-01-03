---
title: "IPv6 자동 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b116e3aa88f919b850d6f79754d25ee10ac974f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ipv6-auto-configuration"></a><span data-ttu-id="48517-102">IPv6 자동 구성</span><span class="sxs-lookup"><span data-stu-id="48517-102">IPv6 Auto-Configuration</span></span>
<span data-ttu-id="48517-103">IPv6의 중요한 목표 중 하나는 노드 플러그 앤 플레이를 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48517-103">One important goal for IPv6 is to support node Plug and Play.</span></span> <span data-ttu-id="48517-104">즉, 노드를 IPv6 네트워크에 플러그하여 사용자가 개입하지 않고 자동으로 구성되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-104">That is, it should be possible to plug a node into an IPv6 network and have it automatically configured without any human intervention.</span></span>  
  
## <a name="type-of-auto-configuration"></a><span data-ttu-id="48517-105">자동 구성 형식</span><span class="sxs-lookup"><span data-stu-id="48517-105">Type of Auto-Configuration</span></span>  
 <span data-ttu-id="48517-106">IPv6에서는 다음과 같은 형식의 자동 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-106">IPv6 supports the following types of auto-configuration:</span></span>  
  
-   <span data-ttu-id="48517-107">**상태 저장 자동 구성**.</span><span class="sxs-lookup"><span data-stu-id="48517-107">**Stateful auto-configuration**.</span></span> <span data-ttu-id="48517-108">노드 설치 및 관리를 위해 DHCPv6(Dynamic Host Configuration Protocol for IPv6) 서버가 필요하므로 이러한 형식의 구성에는 일정 수준의 사용자 개입이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-108">This type of configuration requires a certain level of human intervention because it needs a Dynamic Host Configuration Protocol for IPv6 (DHCPv6) server for the installation and administration of the nodes.</span></span> <span data-ttu-id="48517-109">DHCPv6 서버에서는 구성 정보를 제공하는 노드 목록을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-109">The DHCPv6 server keeps a list of nodes to which it supplies configuration information.</span></span> <span data-ttu-id="48517-110">또한 각 주소를 사용하는 기간 및 재할당이 가능한 시기를 서버에서 알 수 있도록 상태 정보도 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-110">It also maintains state information so the server knows how long each address is in use, and when it might be available for reassignment.</span></span>  
  
-   <span data-ttu-id="48517-111">**상태 비저장 자동 구성**.</span><span class="sxs-lookup"><span data-stu-id="48517-111">**Stateless auto-configuration**.</span></span> <span data-ttu-id="48517-112">이 구성 형식은 소규모 조직 및 개인이 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-112">This type of configuration is suitable for small organizations and individuals.</span></span> <span data-ttu-id="48517-113">이 경우 각 호스트에서는 수신된 라우터 알림의 콘텐츠를 통해 해당 주소를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-113">In this case, each host determines its addresses from the contents of received router advertisements.</span></span> <span data-ttu-id="48517-114">IEEE EUI-64 표준을 사용하여 주소의 네트워크 ID 부분을 정의하면 링크에서 호스트 주소가 고유하다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48517-114">Using the IEEE EUI-64 standard to define the network ID portion of the address, it is reasonable to assume the uniqueness of the host address on the link.</span></span>  
  
 <span data-ttu-id="48517-115">주소를 결정하는 방법에 관계없이 노드에서 잠재적인 주소가 로컬 링크에 고유한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-115">Regardless of how the address is determined, the node must verify that its potential address is unique to the local link.</span></span> <span data-ttu-id="48517-116">이 작업은 잠재적 주소에 네트워크 환경 요청 메시지를 전송하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-116">This is done by sending a neighbor solicitation message to the potential address.</span></span> <span data-ttu-id="48517-117">노드에서 응답을 받으면 주소가 이미 사용 중이므로 다른 주소를 판별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-117">If the node receives any response, it knows that the address is already in use and must determine another address.</span></span>  
  
## <a name="ipv6-mobility"></a><span data-ttu-id="48517-118">IPv6 이동성</span><span class="sxs-lookup"><span data-stu-id="48517-118">IPv6 Mobility</span></span>  
 <span data-ttu-id="48517-119">모바일 장치가 확산됨에 따라 새로운 요구 사항이 제기되었습니다. 장치에서 IPv6 인터넷의 위치를 임의로 변경하고 기존 연결은 여전히 유지할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-119">The proliferation of mobile devices has introduced a new requirement: A device must be able to arbitrarily change locations on the IPv6 Internet and still maintain existing connections.</span></span> <span data-ttu-id="48517-120">이 기능을 제공하기 위해 모바일 노드에 언제나 도달할 수 있는 홈 주소가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="48517-120">To provide this functionality, a mobile node is assigned a home address at which it can always be reached.</span></span> <span data-ttu-id="48517-121">모바일 노드가 홈에 있으면 홈 링크에 연결하고 홈 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-121">When the mobile node is at home, it connects to the home link and uses its home address.</span></span> <span data-ttu-id="48517-122">모바일 노드가 항상 홈 외부에 있으면 일반적으로 라우터인 홈 에이전트에서 모바일 노드 및 이 노드와 통신하는 노드 간에 메시지를 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="48517-122">When the mobile node is away from home, a home agent, which is usually a router, relays messages between the mobile node and nodes with which it is communicating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48517-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48517-123">See Also</span></span>  
 [<span data-ttu-id="48517-124">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="48517-124">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="48517-125">소켓</span><span class="sxs-lookup"><span data-stu-id="48517-125">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
