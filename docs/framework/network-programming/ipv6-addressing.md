---
title: "IPv6 주소 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 01d4fd0fbeeb0f111505fde0f8154c54b2bdcc38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ipv6-addressing"></a><span data-ttu-id="b0294-102">IPv6 주소 지정</span><span class="sxs-lookup"><span data-stu-id="b0294-102">IPv6 Addressing</span></span>
<span data-ttu-id="b0294-103">IPv6(인터넷 프로토콜 버전 6)에서 주소의 길이는 128비트입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-103">In the Internet Protocol version 6 (IPv6), addresses are 128 bits long.</span></span> <span data-ttu-id="b0294-104">주소 공간이 이렇게 큰 하나의 이유는 사용 가능한 주소를 인터넷 토폴로지를 반영하는 라우팅 도메인 계층 구조로 세분화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-104">One reason for such a large address space is to subdivide the available addresses into a hierarchy of routing domains that reflect the Internet's topology.</span></span> <span data-ttu-id="b0294-105">또 다른 이유는 장치를 네트워크에 연결하는 네트워크 어댑터(또는 인터페이스)의 주소를 매핑하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-105">Another reason is to map the addresses of network adapters (or interfaces) that connect devices to the network.</span></span> <span data-ttu-id="b0294-106">IPv6은 최하위 수준인 네트워크 인터페이스 수준에서 주소를 확인하는 고유한 기능과 자동 구성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-106">IPv6 features an inherent capability to resolve addresses at their lowest level, which is at the network interface level, and also has auto-configuration capabilities.</span></span>  
  
## <a name="text-representation"></a><span data-ttu-id="b0294-107">텍스트 표현</span><span class="sxs-lookup"><span data-stu-id="b0294-107">Text Representation</span></span>  
 <span data-ttu-id="b0294-108">IPv6 주소를 텍스트 문자열로 표현하는 데 사용되는 세 가지 기존 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-108">The following are the three conventional forms used to represent the IPv6 addresses as text strings:</span></span>  
  
-   <span data-ttu-id="b0294-109">**콜론-16진수 형식**.</span><span class="sxs-lookup"><span data-stu-id="b0294-109">**Colon-hexadecimal form**.</span></span> <span data-ttu-id="b0294-110">권장되는 형식인 n:n:n:n:n:n:n:n입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-110">This is the preferred form n:n:n:n:n:n:n:n.</span></span> <span data-ttu-id="b0294-111">각 n은 주소를 구성하는 8개의 16비트 요소 중 하나에 대한 16진수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-111">Each n represents the hexadecimal value of one of the eight 16-bit elements of the address.</span></span> <span data-ttu-id="b0294-112">예: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`</span><span class="sxs-lookup"><span data-stu-id="b0294-112">For example: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.</span></span>  
  
-   <span data-ttu-id="b0294-113">**압축된 형식**.</span><span class="sxs-lookup"><span data-stu-id="b0294-113">**Compressed form**.</span></span> <span data-ttu-id="b0294-114">주소 길이 때문에 일반적으로 0으로 구성된 긴 문자열이 있는 주소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-114">Due to the address length, it is common to have addresses containing a long string of zeros.</span></span> <span data-ttu-id="b0294-115">이러한 주소 작성을 간소화하려면 0 블록의 단일 연속 시퀀스를 이중 콜론 기호(::)로 표현하는 압축된 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-115">To simplify writing these addresses, use the compressed form, in which a single contiguous sequence of 0 blocks are represented by a double-colon symbol (::).</span></span> <span data-ttu-id="b0294-116">이 기호는 주소에서 한 번만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-116">This symbol can appear only once in an address.</span></span> <span data-ttu-id="b0294-117">예를 들어 압축된 형식의 멀티캐스트 주소 `FFED:0:0:0:0:BA98:3210:4562`는 `FFED::BA98:3210:4562`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-117">For example, the multicast address `FFED:0:0:0:0:BA98:3210:4562` in compressed form is `FFED::BA98:3210:4562`.</span></span> <span data-ttu-id="b0294-118">압축된 형식의 유니캐스트 주소 `3FFE:FFFF:0:0:8:800:20C4:0`은 `3FFE:FFFF::8:800:20C4:0`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-118">The unicast address `3FFE:FFFF:0:0:8:800:20C4:0` in compressed form is `3FFE:FFFF::8:800:20C4:0`.</span></span> <span data-ttu-id="b0294-119">압축된 형식의 루프백 주소 `0:0:0:0:0:0:0:1`은 `::`1입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-119">The loopback address `0:0:0:0:0:0:0:1` in compressed form is `::`1.</span></span> <span data-ttu-id="b0294-120">압축된 형식의 지정되지 않은 주소 `0:0:0:0:0:0:0:0`은 `::`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-120">The unspecified address `0:0:0:0:0:0:0:0` in compressed form is `::`.</span></span>  
  
-   <span data-ttu-id="b0294-121">**혼합된 형식**.</span><span class="sxs-lookup"><span data-stu-id="b0294-121">**Mixed form**.</span></span> <span data-ttu-id="b0294-122">이 형식은 IPv4 주소와 IPv6 주소를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-122">This form combines IPv4 and IPv6 addresses.</span></span> <span data-ttu-id="b0294-123">이 경우 주소 형식은 n:n:n:n:n:n:d.d.d.d입니다. 여기서 각 n은 6개의 IPv6 높은 순서 16비트 주소 요소의 16진수 값을 나타내고 각 d는 IPv4 주소의 10진수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-123">In this case, the address format is n:n:n:n:n:n:d.d.d.d, where each n represents the hexadecimal values of the six IPv6 high-order 16-bit address elements, and each d represents the decimal value of an IPv4 address.</span></span>  
  
## <a name="address-types"></a><span data-ttu-id="b0294-124">주소 형식</span><span class="sxs-lookup"><span data-stu-id="b0294-124">Address Types</span></span>  
 <span data-ttu-id="b0294-125">주소의 선행 비트는 특정 IPv6 주소 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-125">The leading bits in the address define the specific IPv6 address type.</span></span> <span data-ttu-id="b0294-126">이러한 선행 비트가 포함된 가변 길이 필드를 FP(Format Prefix)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-126">The variable-length field containing these leading bits is called a Format Prefix (FP).</span></span>  
  
 <span data-ttu-id="b0294-127">IPv6 유니캐스트 주소는 두 부분으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-127">An IPv6 unicast address is divided into two parts.</span></span> <span data-ttu-id="b0294-128">첫 번째 부분에는 주소 접두사가 포함되고 두 번째 부분에는 인터페이스 식별자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-128">The first part contains the address prefix, and the second part contains the interface identifier.</span></span> <span data-ttu-id="b0294-129">IPv6 주소/접두사 조합을 표시하는 간결한 방법은 다음과 같습니다. ipv6-address/prefix-length.</span><span class="sxs-lookup"><span data-stu-id="b0294-129">A concise way to express an IPv6 address/prefix combination is as follows: ipv6-address/prefix-length.</span></span>  
  
 <span data-ttu-id="b0294-130">64비트 접두사가 포함된 주소의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-130">The following is an example of an address with a 64-bit prefix.</span></span>  
  
 <span data-ttu-id="b0294-131">`3FFE:FFFF:0:CD30:0:0:0:0/64`.</span><span class="sxs-lookup"><span data-stu-id="b0294-131">`3FFE:FFFF:0:CD30:0:0:0:0/64`.</span></span>  
  
 <span data-ttu-id="b0294-132">이 예의 접두사는 `3FFE:FFFF:0:CD30`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-132">The prefix in this example is `3FFE:FFFF:0:CD30`.</span></span> <span data-ttu-id="b0294-133">주소는 압축된 형식으로 기록될 수도 있습니다(예: `3FFE:FFFF:0:CD30::/64`).</span><span class="sxs-lookup"><span data-stu-id="b0294-133">The address can also be written in a compressed form, as `3FFE:FFFF:0:CD30::/64`.</span></span>  
  
 <span data-ttu-id="b0294-134">IPv6은 다음 주소 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-134">IPv6 defines the following address types:</span></span>  
  
-   <span data-ttu-id="b0294-135">**유니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-135">**Unicast address**.</span></span> <span data-ttu-id="b0294-136">단일 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-136">An identifier for a single interface.</span></span> <span data-ttu-id="b0294-137">이 주소에 전송된 패킷은 식별된 인터페이스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-137">A packet sent to this address is delivered to the identified interface.</span></span> <span data-ttu-id="b0294-138">유니캐스트 주소는 높은 순서 8진수 값으로 멀티캐스트 주소와 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-138">The unicast addresses are distinguished from the multicast addresses by the value of the high-order octet.</span></span> <span data-ttu-id="b0294-139">멀티캐스트 주소의 높은 순서 8진수에는 16진수 값 FF가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-139">The multicast addresses' high-order octet has the hexadecimal value of FF.</span></span> <span data-ttu-id="b0294-140">이 8진수 식별자의 다른 값은 유니캐스트 주소를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-140">Any other value for this octet identifies a unicast address.</span></span> <span data-ttu-id="b0294-141">다양한 형식의 유니캐스트 주소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-141">The following are different types of unicast addresses:</span></span>  
  
    -   <span data-ttu-id="b0294-142">**링크-로컬 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-142">**Link-local addresses**.</span></span> <span data-ttu-id="b0294-143">이러한 주소는 단일 링크에서 사용되고 FE80::*InterfaceID* 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-143">These addresses are used on a single link and have the following format: FE80::*InterfaceID*.</span></span> <span data-ttu-id="b0294-144">링크-로컬 주소는 자동 주소 구성, 네트워크 환경 검색을 위해 또는 라우터가 없는 경우 링크에서 노드 간에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-144">Link-local addresses are used between nodes on a link for auto-address configuration, neighbor discovery, or when no routers are present.</span></span> <span data-ttu-id="b0294-145">링크-로컬 주소는 주로 시작 시 사용되고 시스템이 더 큰 범위의 주소를 아직 획득하지 못한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-145">A link-local address is used primarily at startup and when the system has not yet acquired addresses of larger scope.</span></span>  
  
    -   <span data-ttu-id="b0294-146">**사이트-로컬 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-146">**Site-local addresses**.</span></span> <span data-ttu-id="b0294-147">이러한 주소는 단일 사이트에서 사용되고 FEC0::*SubnetID*:*InterfaceID* 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-147">These addresses are used on a single site and have the following format: FEC0::*SubnetID*:*InterfaceID*.</span></span> <span data-ttu-id="b0294-148">사이트-로컬 주소는 전역 접두사를 사용할 필요 없이 사이트 내에서 주소 지정에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-148">The site-local addresses are used for addressing inside a site without the need for a global prefix.</span></span>  
  
    -   <span data-ttu-id="b0294-149">**전역 IPv6 유니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-149">**Global IPv6 unicast addresses**.</span></span> <span data-ttu-id="b0294-150">이러한 주소는 인터넷에서 사용될 수 있고 010(FP, 3비트) TLA ID(13 bits) Reserved(8비트) NLA ID(24비트) SLA ID(16비트) *InterfaceID*(64비트) 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-150">These addresses can be used across the Internet and have the following format: 010(FP, 3 bits) TLA ID (13 bits) Reserved (8 bits) NLA ID (24 bits) SLA ID (16 bits) *InterfaceID* (64 bits).</span></span>  
  
-   <span data-ttu-id="b0294-151">**멀티캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-151">**Multicast address**.</span></span> <span data-ttu-id="b0294-152">인터페이스 집합의 식별자입니다(일반적으로 서로 다른 노드에 속함).</span><span class="sxs-lookup"><span data-stu-id="b0294-152">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="b0294-153">이 주소에 전송된 패킷은 주소로 식별되는 모든 인터페이스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-153">A packet sent to this address is delivered to all the interfaces identified by the address.</span></span> <span data-ttu-id="b0294-154">멀티캐스트 주소 형식이 IPv4 브로드캐스트 주소보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-154">The multicast address types supersede the IPv4 broadcast addresses.</span></span>  
  
-   <span data-ttu-id="b0294-155">**애니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="b0294-155">**Anycast address**.</span></span> <span data-ttu-id="b0294-156">인터페이스 집합의 식별자입니다(일반적으로 서로 다른 노드에 속함).</span><span class="sxs-lookup"><span data-stu-id="b0294-156">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="b0294-157">이 주소에 전송된 패킷은 주소로 식별되는 하나의 인터페이스에만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-157">A packet sent to this address is delivered to only one interface identified by the address.</span></span> <span data-ttu-id="b0294-158">이 주소는 라우팅 메트릭으로 식별되는 가장 가까운 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-158">This is the nearest interface as identified by routing metrics.</span></span> <span data-ttu-id="b0294-159">애니캐스트 주소는 유니캐스트 주소 공간에서 가져오고 구문상 구별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-159">Anycast addresses are taken from the unicast address space and are not syntactically distinguishable.</span></span> <span data-ttu-id="b0294-160">주소 지정된 인터페이스는 유니캐스트 주소와 애니캐스트 주소를 구성 함수로 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-160">The addressed interface performs the distinction between unicast and anycast addresses as a function of its configuration.</span></span>  
  
 <span data-ttu-id="b0294-161">일반적으로 노드에는 항상 링크-로컬 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-161">In general, a node always has a link-local address.</span></span> <span data-ttu-id="b0294-162">사이트-로컬 주소 및 하나 이상의 전역 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0294-162">It might have a site-local address and one or more global addresses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0294-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0294-163">See Also</span></span>  
 [<span data-ttu-id="b0294-164">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="b0294-164">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="b0294-165">소켓</span><span class="sxs-lookup"><span data-stu-id="b0294-165">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
