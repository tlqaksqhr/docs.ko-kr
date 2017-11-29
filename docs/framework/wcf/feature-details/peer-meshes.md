---
title: "피어 메시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ca3d934564447018f44a423c36f26454588db4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="peer-meshes"></a><span data-ttu-id="54b92-102">피어 메시</span><span class="sxs-lookup"><span data-stu-id="54b92-102">Peer Meshes</span></span>
<span data-ttu-id="54b92-103">A *메시* 은 서로 통신할 수 있는 고유한 메시 ID로 식별 되 고 피어 노드의 명명된 된 컬렉션 (상호 연결 된 그래프)</span><span class="sxs-lookup"><span data-stu-id="54b92-103">A *mesh* is a named collection (an interconnected graph) of peer nodes that can communicate among themselves and that are identified by a unique mesh ID.</span></span> <span data-ttu-id="54b92-104">각 노드는 다른 여러 노드에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-104">Each node is connected to multiple other nodes.</span></span> <span data-ttu-id="54b92-105">잘 연결된 메시에서는 모든 두 노드 간에 경로가 있으며 메시의 가장 바깥쪽 가장자리에 있는 노드 사이에 홉 수가 상대적으로 적습니다. 또한 일부 노드 또는 연결이 끊어지는 경우에도 메시가 연결된 상태로 유지됩니다. 메시의 활성 노드는 다른 피어가 찾을 수 있도록 해당 메시 ID를 사용하여 끝점 정보를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-105">In a well-connected mesh, there is a path between any two nodes, with relatively few hops between the nodes on the furthest edges of the mesh, and the mesh will remain connected even if some nodes or connections drop out. Active nodes in the mesh publish their endpoint information with a corresponding mesh ID so that other peers can find them.</span></span>  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a><span data-ttu-id="54b92-106">피어 채널을 사용하여 만든 메시의 특징</span><span class="sxs-lookup"><span data-stu-id="54b92-106">Characteristics of a Mesh Created Using Peer Channel</span></span>  
  
#### <a name="uniquely-identified"></a><span data-ttu-id="54b92-107">고유한 식별</span><span class="sxs-lookup"><span data-stu-id="54b92-107">Uniquely Identified</span></span>  
  
-   <span data-ttu-id="54b92-108">고유 ID로 각 메시가 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-108">A unique ID identifies each mesh.</span></span> <span data-ttu-id="54b92-109">메시 이름(또는 메시 ID)은 DNS(Domain Name System) 호스트 이름과 동일한 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-109">The name of the mesh (or mesh ID) is in the same format as a Domain Name System (DNS) host name.</span></span> <span data-ttu-id="54b92-110">따라서 이 메시 ID는 사용되는 확인자 범위 내에서 의도된 응용 프로그램 클라이언트에 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-110">As such, this mesh ID must be unique for the intended client of the application within the scope of the resolver being used.</span></span> <span data-ttu-id="54b92-111">"MyFamilysPeers" 또는 "KevinsPokerTable" 같은 일반 이름은 다른 사용자 이름과 충돌하기 쉽고 의도하지 않은 피어 끝점 정보를 반환할 수 있으므로 개인 정보 보호 문제가 발생하거나 연결 대기 시간이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-111">A common name such as "MyFamilysPeers" or "KevinsPokerTable," may easily collide with other user names and may return unintended peer endpoint information, which could result in privacy issues or increase connection latency.</span></span> <span data-ttu-id="54b92-112">이러한 문제를 방지하는 한 가지 방법은 메시의 애칭에 고유 ID를 후위 형식으로 추가하는 것입니다(예: "KevinsPokerTable90210").</span><span class="sxs-lookup"><span data-stu-id="54b92-112">One way to avoid these issues may be to add a unique ID as a postfix to the nickname for the mesh (for example, "KevinsPokerTable90210").</span></span>  
  
#### <a name="message-flooding"></a><span data-ttu-id="54b92-113">메시지 플러딩</span><span class="sxs-lookup"><span data-stu-id="54b92-113">Message Flooding</span></span>  
  
-   <span data-ttu-id="54b92-114">메시를 사용하면 하나 이상의 발신자에서 동일한 메시의 다른 모든 피어 노드로 메시지를 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-114">The mesh allows messages to be propagated from one or more senders to all other peer nodes in the same mesh.</span></span> <span data-ttu-id="54b92-115">피어 노드에서 플러딩한 메시지는 `http://schemas.microsoft.com/net/2006/05/peer`의 네임스페이스에서 지정된 헤더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-115">Messages flooded by peer nodes use headers specified in the namespace at `http://schemas.microsoft.com/net/2006/05/peer`.</span></span>  
  
#### <a name="optimized-connections"></a><span data-ttu-id="54b92-116">최적화된 연결</span><span class="sxs-lookup"><span data-stu-id="54b92-116">Optimized Connections</span></span>  
  
-   <span data-ttu-id="54b92-117">피어 채널 메시는 노드가 참가하고 벗어날 때 이에 맞게 자동으로 조정되어 모든 노드가 파티션(서로 격리되는 노드 그룹)을 만들지 않고 양호한 연결 상태를 유지하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-117">A Peer Channel mesh automatically adjusts when nodes join and leave, ensuring that all nodes have good connectivity with little chance of creating partitions (groups of nodes isolated from each other).</span></span> <span data-ttu-id="54b92-118">또한 메시의 연결은 발신자에서 수신자로의 메시지 대기 시간을 가능한 한 줄이기 위해 현재 트래픽 패턴을 기반으로 동적으로 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-118">Connections in the mesh are also dynamically optimized based on current traffic patterns so that message latency from sender to receiver is as small as possible.</span></span>  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a><span data-ttu-id="54b92-119">피어 채널에서 제공하지 않는 일반적인 네트워크 기능</span><span class="sxs-lookup"><span data-stu-id="54b92-119">Popular Network Features That Peer Channel Does Not Provide</span></span>  
 <span data-ttu-id="54b92-120">피어 채널에서 제공하지 않는 일반적인 네트워크 기능을 알아두는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-120">It is important to be aware of popular network features that Peer Channel does not provide.</span></span> <span data-ttu-id="54b92-121">모두 피어 채널에서 구현될 수 있는 이러한 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-121">These features, which may all be built on top of Peer Channel, include the following:</span></span>  
  
-   <span data-ttu-id="54b92-122">**메시지 정렬:** 단일 소스에서 시작 된 메시지가 소스에서 전송 된 순서에서 다른 모든 당사자 동일한 순서로 도착 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-122">**Message ordering:** Messages originating from a single source may not arrive at all other parties in the same order or in the order that the source sent.</span></span> <span data-ttu-id="54b92-123">메시지가 특정 순서대로 배달되어야 하는 응용 프로그램은 모든 메시지와 함께 일정하게 증가하는 ID를 포함하는 등의 방법으로 이 순서를 응용 프로그램에 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-123">Applications that require messages be delivered in a certain order must build it into their applications (for example, by including a monotonically increasing ID with all messages).</span></span>  
  
-   <span data-ttu-id="54b92-124">**신뢰할 수 있는 메시징:** 피어 채널은 모든 피어의 메시지 수신을 보장 하는 메커니즘을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-124">**Reliable messaging:** Peer Channel does not include a mechanism to ensure message reception by all peers.</span></span> <span data-ttu-id="54b92-125">메시지 배달을 보장하려면 피어 채널에 안정성 계층을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b92-125">To guarantee message delivery, you must write a reliability layer on top of Peer Channel.</span></span>
