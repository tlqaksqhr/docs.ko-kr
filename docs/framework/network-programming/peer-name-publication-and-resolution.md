---
title: "피어 이름 게시 및 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 76201cc1b84e2bbcee35768781f3bae1ac38e14b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="peer-name-publication-and-resolution"></a><span data-ttu-id="abd63-102">피어 이름 게시 및 확인</span><span class="sxs-lookup"><span data-stu-id="abd63-102">Peer Name Publication and Resolution</span></span>
## <a name="publishing-a-peer-name"></a><span data-ttu-id="abd63-103">피어 이름 게시</span><span class="sxs-lookup"><span data-stu-id="abd63-103">Publishing a Peer Name</span></span>  
 <span data-ttu-id="abd63-104">새 PNRP ID를 게시하기 위해 피어에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-104">To publish a new PNRP ID, a peer performs the following:</span></span>  
  
-   <span data-ttu-id="abd63-105">캐시 내에서 인접해 있는 피어(캐시의 최하위 수준에 PNRP ID가 등록된 피어)에 PNRP 게시 메시지를 보내 자신의 캐시를 시드합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-105">Sends PNRP publication messages to its cache neighbors (the peers that have registered PNRP IDs in the lowest level of the cache) to seed their caches.</span></span>  
  
-   <span data-ttu-id="abd63-106">클라우드에서 인접해 있지 않은 임의 노드를 선택하고 PNRP 이름 확인 요청을 보내 해당 노드의 P2P ID를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-106">Chooses random nodes in the cloud that are not its neighbors and sends them PNRP name resolution requests for its own P2P ID.</span></span> <span data-ttu-id="abd63-107">그 결과 수행되는 끝점 확인 프로세스에서 클라우드에서 게시하는 피어의 PNRP ID를 가진 임의 노드의 캐시를 시드합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-107">The resulting endpoint determination process seeds the caches of random nodes in the cloud with the PNRP ID of the publishing peer.</span></span>  
  
-  
  
 <span data-ttu-id="abd63-108">PNRP 버전 2 노드에서는 다른 P2P ID만 확인하는 경우 PNRP ID를 게시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-108">PNRP version 2 nodes do not publish PNRP IDs if they are only resolving other P2P IDs.</span></span> <span data-ttu-id="abd63-109">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 레지스트리 값(REG_DWORD 종류)은 피어에서 PNRP를 이름 확인에만 사용하고 이름 게시에는 사용하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-109">The HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 registry value (REG_DWORD type) specifies that peers only use PNRP for name resolution, never for name publication.</span></span> <span data-ttu-id="abd63-110">이 레지스트리 값은 그룹 정책을 통해 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-110">This registry value can also be configured through Group Policy.</span></span>  
  
## <a name="resolving-a-peer-name"></a><span data-ttu-id="abd63-111">피어 이름 확인</span><span class="sxs-lookup"><span data-stu-id="abd63-111">Resolving a Peer Name</span></span>  
 <span data-ttu-id="abd63-112">PNRP 네트워크 또는 클라우드에서 다른 피어를 찾는 것은 다음 두 단계로 구성된 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-112">Locating other peers in a PNRP network or cloud is a process comprised of two phases:</span></span>  
  
1.  <span data-ttu-id="abd63-113">끝점 확인</span><span class="sxs-lookup"><span data-stu-id="abd63-113">Endpoint Determination</span></span>  
  
2.  <span data-ttu-id="abd63-114">PNRP ID 확인</span><span class="sxs-lookup"><span data-stu-id="abd63-114">PNRP ID Resolution</span></span>  
  
 <span data-ttu-id="abd63-115">끝점 확인 단계에서 다른 컴퓨터에 있는 서비스의 PNRP ID를 확인하려는 피어가 해당 원격 피어의 IPv6 주소를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-115">In the endpoint determination phase, a peer that is attempting to resolve the PNRP ID of a service on another computer determines the IPv6 address of that remote peer.</span></span>  <span data-ttu-id="abd63-116">원격 피어는 게시된 피어이거나 서비스 또는 컴퓨터의 PNRP ID와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-116">The remote peer is the one that published, or is associated with, the PNRP ID of the computer or service.</span></span>  
  
 <span data-ttu-id="abd63-117">원격 끝점이 PNRP 클라우드에 등록되었음을 확인한 다음 PNRP ID 확인 단계의 요청 피어에서 원하는 서비스의 PNRP ID를 위해 해당 피어 끝점에 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-117">After confirming that the remote endpoint has been registered into the PNRP cloud, the requesting peer in the PNRP ID resolution phase sends a request to that peer endpoint for the PNRP ID of the desired service.</span></span> <span data-ttu-id="abd63-118">끝점에서는 요청하는 피어에서 나중에 통신하는 데 사용할 수 있도록 서비스의 PNRP ID뿐만 아니라 설명 및 최대 4킬로바이트의 추가 정보가 포함된 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-118">The endpoint sends a reply confirming the PNRP ID of the service, a comment, and up to 4 kilobytes of additional information that the requesting peer can use for future communication.</span></span> <span data-ttu-id="abd63-119">예를 들어 원하는 끝점이 게임 서버인 경우 이러한 추가 피어 이름 레코드 데이터에는 게임, 플레이 레벨, 현재 플레이어 수 등의 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-119">For example, if the desired endpoint is a gaming server, the additional peer name record data can contain information about the game, the level of play, and the current number of players.</span></span>  
  
 <span data-ttu-id="abd63-120">끝점을 확인하는 단계에서 PNRP는 반복 프로세스를 사용하여 PNRP ID를 게시한 노드를 찾습니다. 이 프로세스에서 확인 작업을 수행하는 노드는 대상 PNRP ID에 인접한 여러 노드를 연결하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-120">In the endpoint determination phase, PNRP uses an iterative process for locating the node that published the PNRP ID, in which the node performing the resolution is responsible for contacting nodes that are successively closer to the target PNRP ID.</span></span>  
  
 <span data-ttu-id="abd63-121">PNRP에서 이름 확인 작업을 수행하려면 피어가 자체 캐시를 조사하여 대상 PNRP ID와 일치하는 항목을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-121">To perform name resolution in PNRP, the peer examines the entries in its own cache for an entry that matches the target PNRP ID.</span></span> <span data-ttu-id="abd63-122">이러한 항목이 발견되면 피어는 해당 피어에 PNRP 요청 메시지를 보내고 응답을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-122">If found, the peer sends a PNRP Request message to the peer and waits for a response.</span></span> <span data-ttu-id="abd63-123">해당 PNRP ID와 일치하는 항목이 없으면 피어는 PNRP ID가 대상 PNRP ID에 가장 근접한 항목에 해당하는 피어에 PNRP 요청 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-123">If an entry for the PNRP ID is not found, the peer sends a PNRP Request message to the peer that corresponds to the entry that has a PNRP ID that most closely matches the target PNRP ID.</span></span> <span data-ttu-id="abd63-124">PNRP 요청 메시지를 받은 노드는 자체 캐시를 조사하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-124">The node that receives the PNRP Request message examines its own cache and does the following:</span></span>  
  
-   <span data-ttu-id="abd63-125">PNRP ID가 있으면 요청받은 끝점 피어가 요청한 피어에 직접 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-125">If the PNRP ID is found, the requested endpoint peer replies directly to the requesting peer.</span></span>  
  
-   <span data-ttu-id="abd63-126">해당 PNRP ID가 없고 캐시에 대상 PNRP ID에 근접한 PNRP ID가 있으면 요청받은 피어가 요청한 피어에 대상 PNRP ID에 더 근접한 PNRP ID를 가진 항목에 해당하는 피어의 IPv6 주소가 포함된 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-126">If the PNRP ID is not found and a PNRP ID in the cache is closer to the target PNRP ID, the requested peer sends a response to the requesting peer containing the IPv6 address of the peer that represents the entry with a PNRP ID that more closely matches the target PNRP ID.</span></span> <span data-ttu-id="abd63-127">응답에서 IP 주소를 사용하면 요청 노드가 다른 PNRP 요청 메시지를 IPv6 주소에 전송하여 캐시를 검사하거나 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-127">Using the IP address in the response, the requesting node sends another PNRP Request message to the IPv6 address to respond or examine its cache.</span></span>  
  
-   <span data-ttu-id="abd63-128">해당 PNRP ID가 없고 캐시에 대상 PNRP ID에 근접한 PNRP ID도 없으면 요청받은 피어가 요청한 피어에 이러한 상황을 알리는 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-128">If the PNRP ID is not found and there is no PNRP ID in its cache that is closer to the target PNRP ID, the requested peer sends the requesting peer a response that indicates this condition.</span></span> <span data-ttu-id="abd63-129">그러면 요청한 피어는 다음으로 가장 근접한 PNRP ID를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-129">The requesting peer then chooses the next-closest PNRP ID.</span></span>  
  
-  
  
 <span data-ttu-id="abd63-130">요청한 피어는 이 프로세스를 연속적으로 반복하여 PNRP ID를 등록한 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-130">The requesting peer continues this process with successive iterations, eventually locating the node that registered the PNRP ID.</span></span>  
  
 <span data-ttu-id="abd63-131"><xref:System.Net.PeerToPeer> 네임스페이스에서 끝점을 포함하는 <xref:System.Net.PeerToPeer.PeerName> 레코드 및 이와 통신하는 PNRP 클라우드 또는 메시 간에는 다대다 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-131">Within the <xref:System.Net.PeerToPeer> namespace, there is a many-to-many relationship between the <xref:System.Net.PeerToPeer.PeerName> records that contain endpoints and PNRP clouds or meshes in which they communicate.</span></span> <span data-ttu-id="abd63-132">중복 항목 또는 오래된 항목이 있거나 피어 이름이 같은 노드가 여러 개인 경우 PNRP 노드에서는 <xref:System.Net.PeerToPeer.PeerNameResolver> 클래스를 사용하여 최신 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-132">When there are duplicate or stale entries, or multiple nodes with the same peer name, PNRP nodes can obtain current information using the <xref:System.Net.PeerToPeer.PeerNameResolver> class.</span></span> <span data-ttu-id="abd63-133"><xref:System.Net.PeerToPeer.PeerNameResolver> 메서드에서는 단일 피어 이름을 사용하여 큐브 뷰를 하나의 피어 대 여러 피어 이름 레코드 및 마찬가지로 한 피어 대 여러 클라우드로 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-133">The <xref:System.Net.PeerToPeer.PeerNameResolver> methods use a single peer name to simplify the perspective to one peer-to-many peer name records and the same one peer to many clouds.</span></span> <span data-ttu-id="abd63-134">관계형 테이블 조인을 사용한 쿼리와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-134">This is similar to a query performed using a relational-table join.</span></span> <span data-ttu-id="abd63-135">성공적으로 완료되면 확인자 개체에서 지정된 피어 이름에 대해 <xref:System.Net.PeerToPeer.PeerNameRecordCollection>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-135">Upon successful completion, the Resolver object returns a <xref:System.Net.PeerToPeer.PeerNameRecordCollection> for the specified peer name.</span></span>  <span data-ttu-id="abd63-136">예를 들어 피어 이름은 컬렉션의 모든 피어 이름 레코드에 표시되며 클라우드별로 순서가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-136">For example, a peer name would occur in all the peer name records in the collection, ordered by cloud.</span></span> <span data-ttu-id="abd63-137">PNRP 기반 응용 프로그램에서 요청할 수 있는 지원 데이터가 있는 피어 이름의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="abd63-137">These are the instances of the peer name whose supporting data may be requested by a PNRP-based application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd63-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abd63-138">See Also</span></span>  
 <xref:System.Net.PeerToPeer>
