---
title: "피어 채널 시나리오"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4f989c46deff9c38e4737e48e077bf07240fa98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="peer-channel-scenarios"></a><span data-ttu-id="d70bf-102">피어 채널 시나리오</span><span class="sxs-lookup"><span data-stu-id="d70bf-102">Peer Channel Scenarios</span></span>
<span data-ttu-id="d70bf-103">피어 채널 API는 다음과 같은 개발 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-103">The Peer Channel APIs support the following development scenarios.</span></span>  
  
## <a name="publicationsubscription-messaging"></a><span data-ttu-id="d70bf-104">게시/구독 메시징</span><span class="sxs-lookup"><span data-stu-id="d70bf-104">Publication/Subscription Messaging</span></span>  
 <span data-ttu-id="d70bf-105">게시/구독 응용 프로그램(예: 주식 시세 표시기, 뉴스 헤드라인 게시자, 스포츠 득점판, 일기 예보)을 빌드하는 회사는 서버가 없는 응용 프로그램에 피어 채널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-105">Companies that build publication/subscription applications (for example, stock tickers, and publishers of news headlines, sports scores, and weather reports) can use Peer Channel to server-less applications.</span></span> <span data-ttu-id="d70bf-106">예를 들어 사용자는 일반 메시(또는 클라이언트 그룹)에 참가하여 최신 스포츠 득점판을 가져오며 서버 로드를 늘리지 않고 많은 양의 최신 게임 데이터를 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-106">For example, users can obtain the latest sports scores by joining a common mesh (or group of clients) and propagate the large amount of up-to-date game data without increasing the server load.</span></span> <span data-ttu-id="d70bf-107">이렇게 하면 데이터 공급자가 서버 기반 기술에 대한 투자를 늘리지 않고 더 높은 서비스 품질을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-107">This helps the data provider to give higher quality of service without substantially increasing the investment in server-based technologies.</span></span>  
  
## <a name="collaboration"></a><span data-ttu-id="d70bf-108">공동 작업</span><span class="sxs-lookup"><span data-stu-id="d70bf-108">Collaboration</span></span>  
 <span data-ttu-id="d70bf-109">ISV(Independent Software Vendor)는 피어 투 피어 동작에 참가하기 위해 사용자가 긴밀한 그룹을 만들 수 있게 하는 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-109">Independent software vendors (ISVs) can create applications that let people create tight groups for participation in peer-to-peer activities.</span></span> <span data-ttu-id="d70bf-110">예를 들어 공동 작업 프로젝트에 참가하는 팀, 친구 간의 사진 공유, 파티 계획 활동 등이 여기에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-110">For example, this can include teams working on collaborative projects, picture-sharing between friends, party-planning activities, and more.</span></span> <span data-ttu-id="d70bf-111">일반적으로 이러한 활동에는 항상 서버가 필요합니다. 그러나 피어 채널은 일반적인 서버 클라이언트 모델에서 쉽게 구현되지 않는 오프라인 액세스 시나리오를 가능하게 하여 보다 비용 효과적으로 이 작업을 수행하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-111">Traditionally, these activities always involve servers; however, Peer Channel provides a way of doing this in a more cost-efficient way by enabling offline access scenarios that are not as easily implemented under a traditional server-client model.</span></span>  
  
## <a name="distributed-processing-and-compute-clusters"></a><span data-ttu-id="d70bf-112">분산 처리 및 계산 클러스터</span><span class="sxs-lookup"><span data-stu-id="d70bf-112">Distributed Processing and Compute Clusters</span></span>  
 <span data-ttu-id="d70bf-113">계산 클러스터와 분산 처리는 일반적으로 금융/날씨 모델링, 인간 DNA 디코딩 등의 대규모 계산에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-113">Compute clusters and distributed processing are typically used for large-scale computations, such as financial/weather modeling and decoding human DNA.</span></span> <span data-ttu-id="d70bf-114">이렇게 하려면 대체로 서버가 계산 클러스터에 참가하는 모든 클라이언트에 개별적으로 작업을 할당하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-114">Typically, this is done by having servers individually assign tasks to all clients participating in the computation cluster.</span></span> <span data-ttu-id="d70bf-115">이러한 서버에 추가 요구가 있을 수도 있습니다. 예를 들어 특정 지속 기간 내에 모든 작업을 완료해야 할 수 있으며, 이로 인해 각 작업에 둘 이상의 컴퓨터가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-115">These servers may also have additional demands; for example, all tasks may need to be completed within a certain duration, requiring more than one machine for each task.</span></span> <span data-ttu-id="d70bf-116">또한 작업을 실행하는 클라이언트의 작동이 중단될 경우 다른 클라이언트가 이 작업을 맡아서 수행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-116">Additionally, if any client running a task goes down, another client must be able to take over that task and perform work on it.</span></span> <span data-ttu-id="d70bf-117">마찬가지로 일관성 있는 결과를 보장하기 위해 둘 이상의 클라이언트가 동일한 작업을 실행하여 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-117">Likewise, more than one client may have to run the same task to ensure consistent results.</span></span> <span data-ttu-id="d70bf-118">서버에서 이러한 형식의 클라이언트 코디네이션을 실행할 수 있는 경우에도 작업을 받는 클라이언트가 독립적으로 작업과 관련된 서버 요구 사항을 확인하고 계산 메시를 사용하여 해당 작업을 완료하는 방법을 확인하는 피어 투 피어 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-118">Although servers can run this type of client coordination, you can create a peer-to-peer solution where the clients receiving a task independently determine the server requirements around the task and use a compute mesh to determine how to complete that task.</span></span>  
  
## <a name="gaming"></a><span data-ttu-id="d70bf-119">게임</span><span class="sxs-lookup"><span data-stu-id="d70bf-119">Gaming</span></span>  
 <span data-ttu-id="d70bf-120">응용 프로그램 개발자는 피어 채널을 사용하여 중앙 서버 대신 피어 투 피어 메커니즘에 의해 게임이 다른 플레이어에게 전송되고 동기화되는 서버가 없는 게임 버전을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-120">Using Peer Channel, application developers can create server-less versions of their games where game moves get transmitted to and synchronized with other players by a peer-to-peer mechanism rather than through a central server.</span></span> <span data-ttu-id="d70bf-121">소규모 ISV의 경우 이 기능은 중앙 서버의 배포, 유지 관리 및 공급과 관련된 운영비를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-121">For small ISVs, this helps remove operational costs associated with deploying, maintaining, and servicing central servers.</span></span> <span data-ttu-id="d70bf-122">피어 투 피어 아키텍처를 사용하여 작성된 게임은 인터넷을 통해 또는 유무선 로컬 네트워크에서 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-122">Games written using a peer-to-peer architecture can be played across the Internet, or in wired or wireless local networks.</span></span> <span data-ttu-id="d70bf-123">피어 투 피어 네트워크를 사용하여 로비, 게임 내 채팅 등의 보조 게임 활동을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70bf-123">Secondary gaming activities, such as lobby and in-game chat can be developed using a peer-to-peer network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70bf-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d70bf-124">See Also</span></span>  
 [<span data-ttu-id="d70bf-125">피어 채널 개념</span><span class="sxs-lookup"><span data-stu-id="d70bf-125">Peer Channel Concepts</span></span>](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
