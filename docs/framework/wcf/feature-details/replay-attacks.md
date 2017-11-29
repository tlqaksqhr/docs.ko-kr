---
title: "재생 공격"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 81bca4572b6c4845674c63284f93c86fe5925bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="replay-attacks"></a><span data-ttu-id="3ef05-102">재생 공격</span><span class="sxs-lookup"><span data-stu-id="3ef05-102">Replay Attacks</span></span>
<span data-ttu-id="3ef05-103">A *재생 공격* 는 공격자가 두 당사자 간에 메시지 스트림을 복사 하 고 하나 이상의 당사자에 게 스트림을 재생 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-103">A *replay attack* occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="3ef05-104">완화되지 않은 경우 공격을 받기 쉬운 컴퓨터는 스트림을 올바른 메시지로 처리하여 항목에 대한 중복 주문과 같은 잘못된 결과의 범위에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-104">Unless mitigated, the computers subject to the attack process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a><span data-ttu-id="3ef05-105">바인딩이 반사 공격을 받기 쉬운 경우</span><span class="sxs-lookup"><span data-stu-id="3ef05-105">Bindings May Be Subject to Reflection Attacks</span></span>  
 <span data-ttu-id="3ef05-106">*반사 공격* 회신으로 수신기에서 온 경우 메시지를 보낸 사람에 게 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-106">*Reflection attacks* are replays of messages back to a sender as if they came from the receiver as the reply.</span></span> <span data-ttu-id="3ef05-107">표준 *재생 검색* 에 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메커니즘 처리 하지 않는 자동으로이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-107">The standard *replay detection* in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mechanism does not automatically handle this.</span></span>  
  
 <span data-ttu-id="3ef05-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모델이 서명된 메시지 ID를 요청 메시지에 추가하고 응답 메시지에 서명된 `relates-to` 헤더가 있어야 하므로 반사 공격은 기본적으로 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-108">Reflection attacks are mitigated by default because the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service model adds a signed message ID to request messages and expects a signed `relates-to` header on response messages.</span></span> <span data-ttu-id="3ef05-109">따라서 요청 메시지를 응답으로 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-109">Consequently, the request message cannot be replayed as a response.</span></span> <span data-ttu-id="3ef05-110">보안 RM(신뢰할 수 있는 메시지) 시나리오에서 반사 공격은 다음과 같은 이유로 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-110">In secure reliable message (RM) scenarios, reflection attacks are mitigated because:</span></span>  
  
-   <span data-ttu-id="3ef05-111">시퀀스 만들기 및 시퀀스 만들기 응답 메시지 스키마는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-111">The create sequence and create sequence response message schemas are different.</span></span>  
  
-   <span data-ttu-id="3ef05-112">단면 시퀀스의 경우 클라이언트가 보내는 시퀀스 메시지는 클라이언트가 그러한 메시지를 인식할 수 없으므로 재생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-112">For simplex sequences, sequence messages the client sends cannot be replayed back to it because the client cannot understand such messages.</span></span>  
  
-   <span data-ttu-id="3ef05-113">이중 시퀀스의 경우 두 시퀀스 ID는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-113">For duplex sequences, the two sequence IDs must be unique.</span></span> <span data-ttu-id="3ef05-114">따라서 나가는 시퀀스 메시지를 들어오는 시퀀스 메시지로 재생할 수 없습니다(모든 시퀀스 헤더 및 본문도 서명됨).</span><span class="sxs-lookup"><span data-stu-id="3ef05-114">Thus, an outgoing sequence message cannot be replayed back as an incoming sequence message (all sequence headers and bodies are signed, too).</span></span>  
  
 <span data-ttu-id="3ef05-115">반사 공격을 받기 쉬운 바인딩은 WS-Addressing이 없는 바인딩 즉, WS-Addressing이 사용되지 않는 바인딩을 사용자 지정하고 대칭 키 기반 보안을 사용하는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-115">The only bindings that are susceptible to reflection attacks are those without WS-Addressing: custom bindings that have WS-Addressing disabled and use the symmetric key-based security.</span></span> <span data-ttu-id="3ef05-116"><xref:System.ServiceModel.BasicHttpBinding>은 기본적으로 WS-Addressing을 사용하지 않지만, 이 공격에 노출될 수 있는 방식으로는 대칭 키 기반 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-116">The <xref:System.ServiceModel.BasicHttpBinding> does not use WS-Addressing by default, but it does not use symmetric key-based security in a way that allows it to be vulnerable to this attack.</span></span>  
  
 <span data-ttu-id="3ef05-117">사용자 지정 바인딩을 완화하는 것은 보안 컨텍스트를 설정하지 않거나 WS-Addressing 헤더를 요청하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-117">The mitigation for custom bindings is to not establish security context or to require WS-Addressing headers.</span></span>  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a><span data-ttu-id="3ef05-118">웹 팜: 공격자가 여러 노드에 요청 재생</span><span class="sxs-lookup"><span data-stu-id="3ef05-118">Web Farm: Attacker Replays Request to Multiple Nodes</span></span>  
 <span data-ttu-id="3ef05-119">클라이언트는 웹 팜에 구현된 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-119">A client uses a service that is implemented on a Web farm.</span></span> <span data-ttu-id="3ef05-120">공격자는 팜의 한 노드로 보내진 요청을 팜의 다른 노드에 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-120">An attacker replays a request that was sent to one node in the farm to another node in the farm.</span></span> <span data-ttu-id="3ef05-121">또한, 서비스를 다시 시작하는 경우 재생 캐시가 플러시되어 공격자가 요청을 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-121">In addition, if a service is restarted, the replay cache is flushed, allowing an attacker to replay the request.</span></span> <span data-ttu-id="3ef05-122">캐시에 이전에 사용된 메시지 서명 값이 있고 캐시가 재생되지 않으므로 그러한 서명은 한 번만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-122">(The cache contains used, previously seen message signature values and prevents replays so those signatures can be used only once.</span></span> <span data-ttu-id="3ef05-123">재생 캐시는 웹 팜에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-123">Replay caches are not shared across a Web farm.)</span></span>  
  
 <span data-ttu-id="3ef05-124">완화 방안은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-124">Mitigations include:</span></span>  
  
-   <span data-ttu-id="3ef05-125">상태 저장 보안 컨텍스트 토큰(보안 대화 사용 또는 사용 안 함)과 함께 메시지 모드 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-125">Use message mode security with stateful security context tokens (with or without secure conversation enabled).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="3ef05-126">[하는 방법: 보안 컨텍스트를 만들어 보안 세션에 대 한 토큰](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-126"> [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
-   <span data-ttu-id="3ef05-127">전송 수준 보안을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef05-127">Configure the service to use transport-level security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef05-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ef05-128">See Also</span></span>  
 [<span data-ttu-id="3ef05-129">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3ef05-129">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="3ef05-130">정보 공개 문제점</span><span class="sxs-lookup"><span data-stu-id="3ef05-130">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="3ef05-131">권한 상승 문제점</span><span class="sxs-lookup"><span data-stu-id="3ef05-131">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="3ef05-132">서비스 거부</span><span class="sxs-lookup"><span data-stu-id="3ef05-132">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="3ef05-133">변조</span><span class="sxs-lookup"><span data-stu-id="3ef05-133">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [<span data-ttu-id="3ef05-134">지원 되지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="3ef05-134">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
