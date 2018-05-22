---
title: PNRP 클라우드
ms.date: 03/30/2017
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ef3f4fd2f7333c5a78024edf7eb536e9254c0293
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pnrp-clouds"></a><span data-ttu-id="d6662-102">PNRP 클라우드</span><span class="sxs-lookup"><span data-stu-id="d6662-102">PNRP Clouds</span></span>
<span data-ttu-id="d6662-103">PNRP “클라우드”는 네트워크를 통해 서로 통신할 수 있는 노드 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-103">A PNRP "cloud" represents a set of nodes that can communicate with each other through the network.</span></span> <span data-ttu-id="d6662-104">“클라우드”라는 용어는 “피어 메시” 및 “피어 투 피어 그래프”와 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-104">The term "cloud" is synonymous with "peer mesh" and "peer-to-peer graph".</span></span>  
  
 <span data-ttu-id="d6662-105">노드 간 통신은 한 클라우드에서 다른 클라우드로 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-105">Communication between nodes should never cross from one cloud to another.</span></span> <span data-ttu-id="d6662-106"><xref:System.Net.PeerToPeer.Cloud> 인스턴스는 대소문자를 구분하는 이름으로 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-106">A <xref:System.Net.PeerToPeer.Cloud> instance is uniquely identified by its name, which is case-sensitive.</span></span> <span data-ttu-id="d6662-107">단일 피어 또는 노드는 두 개 이상의 클라우드에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-107">A single peer or node may be connected to more than one cloud.</span></span>  
  
 <span data-ttu-id="d6662-108">클라우드는 네트워크 인터페이스와 매우 밀접하게 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-108">Clouds are tied very closely to network interfaces.</span></span>  <span data-ttu-id="d6662-109">두 개의 네트워크 카드가 여러 다른 서브넷에 연결되어 있는 다중 홈 컴퓨터에서는 세 개의 클라우드가 반환됩니다. 즉, 인터페이스별 링크 로컬 주소당 하나씩 반환되고 단일 글로벌 범위 클라우드용으로 하나가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-109">On a multi-homed machine with two network cards attached to different subnets, three clouds will be returned: one for each of the link local addresses per interface, and a single global scope cloud.</span></span>  
  
 <span data-ttu-id="d6662-110">PNRP에서는 3개의 클라우드 “범위”를 사용합니다. 여기서 범위는 서로 찾을 수 있는 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-110">PNRP uses three cloud "scopes", in which a scope is a grouping of computers that are able to find each other:</span></span>  
  
-   <span data-ttu-id="d6662-111">글로벌 클라우드는 글로벌 IPv6 주소 범위 및 글로벌 주소에 해당하며 전체 IPv6 인터넷상의 모든 컴퓨터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-111">The global cloud corresponds to the global IPv6 address scope and global addresses and represents all the computers on the entire IPv6 Internet.</span></span> <span data-ttu-id="d6662-112">글로벌 클라우드는 하나만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-112">There is only a single global cloud.</span></span>  
  
-   <span data-ttu-id="d6662-113">링크-로컬 클라우드는 링크 로컬 IPv6 주소 범위 및 링크-로컬 주소에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-113">The link-local cloud corresponds to the link-local IPv6 address scope and link-local addresses.</span></span> <span data-ttu-id="d6662-114">링크-로컬 클라우드는 특정 링크에 사용되는데 일반적으로 이러한 링크는 로컬로 연결된 서브넷과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-114">A link-local cloud is for a specific link, which is typically the same as the locally attached subnet.</span></span> <span data-ttu-id="d6662-115">링크 로컬 클라우드의 경우 여러 개가 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-115">There can be multiple link-local clouds.</span></span>  
  
 <span data-ttu-id="d6662-116">세 번째로 사이트별 클라우드가 있는데 이는 사이트 IPv6 주소 범위 및 사이트 로컬 주소에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-116">A third cloud, the site-specific cloud, corresponds to the site IPv6 address scope and site-local addresses.</span></span> <span data-ttu-id="d6662-117">이 클라우드는 더 이상 사용되지 않지만 PNRP에서는 아직 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-117">This cloud has been deprecated, although it is still supported in PNRP.</span></span>  
  
## <a name="clouds"></a><span data-ttu-id="d6662-118">클라우드</span><span class="sxs-lookup"><span data-stu-id="d6662-118">Clouds</span></span>  
 <span data-ttu-id="d6662-119">PNRP 클라우드는 <xref:System.Net.PeerToPeer.Cloud> 클래스의 인스턴스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-119">PNRP clouds are represented by instances of the <xref:System.Net.PeerToPeer.Cloud> class.</span></span> <span data-ttu-id="d6662-120">피어를 사용하는 클라우드 그룹은 열거형 <xref:System.Net.PeerToPeer.CloudCollection> 클래스의 인스턴스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-120">Groups of clouds used a peer are represented by instances of the enumerable <xref:System.Net.PeerToPeer.CloudCollection> class.</span></span> <span data-ttu-id="d6662-121">현재 피어에 알려진 PNRP 클라우드 컬렉션은 정적 <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A> 메서드를 호출하여 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-121">Collections of PNRP clouds known to the current peer can be obtained by calling the static <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A> method.</span></span>  
  
 <span data-ttu-id="d6662-122">개별 클라우드에는 고유한 이름이 있으며 256자 유니코드 문자열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-122">Individual clouds have unique names, represented as a 256 character Unicode string.</span></span> <span data-ttu-id="d6662-123">이러한 이름을 위에 언급된 범위와 함께 사용하여 클라우드 클래스의 고유한 인스턴스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-123">These names, along with the above-mentioned scope, are used to construct unique instances of the Cloud class.</span></span> <span data-ttu-id="d6662-124">이러한 인스턴스는 직렬화할 수 있으며 영구적으로 사용하기 위해 재구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-124">These instances can be serialized and reconstructed for persistent usage.</span></span>  
  
 <span data-ttu-id="d6662-125">클라우드 인스턴스를 만들거나 가져오고 나면 피어 이름을 등록하여 알려진 피어의 메시를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6662-125">Once a Cloud instance is created or obtained, peer names can be registered with it to create a mesh of known peers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6662-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6662-126">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Cloud>  
 [<span data-ttu-id="d6662-127">피어 이름 확인 프로토콜</span><span class="sxs-lookup"><span data-stu-id="d6662-127">Peer Name Resolution Protocol</span></span>](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)
