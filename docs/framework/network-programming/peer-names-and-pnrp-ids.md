---
title: 피어 이름 및 PNRP ID
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 02e6d65baac0a0eab9bfde545a117d3636239c17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="peer-names-and-pnrp-ids"></a><span data-ttu-id="eeace-102">피어 이름 및 PNRP ID</span><span class="sxs-lookup"><span data-stu-id="eeace-102">Peer Names and PNRP IDs</span></span>
<span data-ttu-id="eeace-103">피어 이름은 통신의 끝점을 나타내며, 컴퓨터, 사용자, 그룹, 서비스 또는 IPv6 주소로 확인될 수 있는 피어와 연결된 모든 항목이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-103">A Peer Name represents an endpoint for communication, which can be a computer, a user, a group, a service, or anything associated with a Peer that can be resolved to an IPv6 address.</span></span> <span data-ttu-id="eeace-104">피어 이름 확인 프로토콜(PNRP)은 클라우드 멤버를 확인하는 데 사용되는 PNRP ID를 만드는 데 통계적으로 고유한 피어 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-104">The Peer Name Resolution Protocol (PNRP) takes the statistically unique Peer Name for the creation of a PNRP ID, which is used to identify cloud members.</span></span>  
  
## <a name="peer-names"></a><span data-ttu-id="eeace-105">피어 이름</span><span class="sxs-lookup"><span data-stu-id="eeace-105">Peer Names</span></span>  
 <span data-ttu-id="eeace-106">피어 이름은 보안되지 않음 또는 보안됨으로 등록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-106">Peer names can be registered as unsecured or secured.</span></span> <span data-ttu-id="eeace-107">보안되지 않은 이름은 단순한 텍스트 문자열로, 스푸핑이 가능하기 때문에 누구나 중복된 이름을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-107">Unsecured names are just text strings that are subject to spoofing, as anyone can register a duplicate unsecured name.</span></span> <span data-ttu-id="eeace-108">보안되지 않은 이름은 개인 네트워크 또는 보호되는 네트워크에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-108">Unsecured names are best used in private or otherwise protected networks.</span></span> <span data-ttu-id="eeace-109">반면 보안되는 이름은 인증서와 디지털 시그니처로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-109">Secured names are protected with a certificate and a digital signature.</span></span> <span data-ttu-id="eeace-110">따라서 원래 게시자만 이 이름에 대한 소유권을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-110">Only the original publisher will be able to prove ownership of a secured name.</span></span>  
  
 <span data-ttu-id="eeace-111">클라우드와 범위를 조합하면 PNRP 활동에 참여하는 피어를 위해 꽤 안전한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-111">The combination of cloud and scope provides a reasonably secure environment for peers that participate in PNRP activity.</span></span> <span data-ttu-id="eeace-112">그러나 보안 피어 이름을 사용해도 네트워킹 응용 프로그램의 전체적인 보안이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-112">However, using a secured peer name does not ensure the overall security of the networking application.</span></span> <span data-ttu-id="eeace-113">응용 프로그램의 보안은 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-113">Security of the application is implementation-dependent.</span></span>  
  
 <span data-ttu-id="eeace-114">보안 피어 이름은 소유자만 등록할 수 있으며 공개 키 암호화를 통해 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-114">Secured peer names are only registered by their owner and are protected with public key cryptography.</span></span> <span data-ttu-id="eeace-115">보안 피어 이름은 대응하는 개인 키가 있는 피어 엔터티가 소유하는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-115">A secured peer name is considered owned by the peer entity having the corresponding private key.</span></span> <span data-ttu-id="eeace-116">소유권은 개인 키를 사용하여 서명되는 인증된 피어 주소(CPA)를 통해 입증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-116">Ownership can be proved via the certified peer address (CPA), which is signed using the private key.</span></span> <span data-ttu-id="eeace-117">악의적인 사용자는 해당 개인 키 없이도 피어 이름의 소유권을 위조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-117">A malicious user cannot forge ownership of a peer name without the corresponding private key.</span></span>  
  
## <a name="pnrp-ids"></a><span data-ttu-id="eeace-118">PNRP ID</span><span class="sxs-lookup"><span data-stu-id="eeace-118">PNRP IDs</span></span>  
 <span data-ttu-id="eeace-119">![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")</span><span class="sxs-lookup"><span data-stu-id="eeace-119">![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")</span></span>  
  
 <span data-ttu-id="eeace-120">PNRP ID는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-120">PNRP IDs are composed of the following:</span></span>  
  
-   <span data-ttu-id="eeace-121">순위가 높은 128비트는 P2P(피어 투 피어) ID라고 하며 끝점에 할당된 피어 이름의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-121">The high-order 128 bits, known as the peer-to-peer (P2P) ID, are a hash of a peer name assigned to the endpoint.</span></span> <span data-ttu-id="eeace-122">피어 이름의 형식은 *Authority.Classifier*입니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-122">The peer name has the following format: *Authority.Classifier*.</span></span> <span data-ttu-id="eeace-123">보안되는 이름의 경우, *Authority*는 16진수 문자 형식의 피어 이름 공개 키의 SHA1(Secure Hash Algorithm 1) 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-123">For secured names, *Authority* is the Secure Hash Algorithm 1 (SHA1) hash of the public key of the peer name in hexadecimal characters.</span></span> <span data-ttu-id="eeace-124">보안되지 않는 이름의 경우 *Authority*는 단일 문자 “0”입니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-124">For unsecured names, the *Authority* is the single character "0".</span></span> <span data-ttu-id="eeace-125">*분류자*는 응용 프로그램을 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-125">*Classifier* is a string that identifies the application.</span></span> <span data-ttu-id="eeace-126">피어 이름 분류자는 `null` 종결자를 포함하여 길이지 149자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-126">No peer name classifier can be greater than 149 characters long, including the `null` terminator.</span></span>  
  
-   <span data-ttu-id="eeace-127">순위가 낮은 128비트는 특정 클라우드에서 동일한 P2P ID의 여러 인스턴스를 식별하도록 생성된 수로 서비스 위치를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-127">The low-order 128 bits are used for the Service Location, which is a generated number that identifies different instances of the same P2P ID in the same cloud.</span></span>  
  
 <span data-ttu-id="eeace-128">이렇게 PNRP ID는 P2P ID와 서비스 위치가 조합된 형식이기 때문에 단일 컴퓨터에서 여러 PNRP ID를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeace-128">This combination of P2P ID and Service Location allows multiple PNRP IDs to be registered from a single computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeace-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeace-129">See Also</span></span>  
 <xref:System.Net.PeerToPeer.PeerName>  
 <xref:System.Net.PeerToPeer>
