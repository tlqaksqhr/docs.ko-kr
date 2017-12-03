---
title: "Reliable Messaging 프로토콜 버전 1.1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 586e26825bd01947706bb26061ef1b8879fecb4c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="7d096-102">Reliable Messaging 프로토콜 버전 1.1</span><span class="sxs-lookup"><span data-stu-id="7d096-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="7d096-103">이 항목에서는 HTTP 전송을 사용하여 상호 운용에 필요한 WS-ReliableMessaging February 2007(버전 1.1) 프로토콜의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-104">는 이 항목에서 설명한 제약 조건 및 확인된 내용과 함께 WS-ReliableMessaging 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-104"> follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="7d096-105">부터는 Ws-reliablemessaging 1.1 프로토콜을 구현 하는 참고는 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="7d096-106">WS-ReliableMessaging February 2007 프로토콜은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="7d096-107">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="7d096-108">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="7d096-109">응답자: 개시자의 요청을 받는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="7d096-110">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="7d096-111">접두사</span><span class="sxs-lookup"><span data-stu-id="7d096-111">Prefix</span></span>|<span data-ttu-id="7d096-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7d096-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="7d096-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="7d096-113">wsrm</span></span>|<span data-ttu-id="7d096-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="7d096-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="7d096-115">netrm</span><span class="sxs-lookup"><span data-stu-id="7d096-115">netrm</span></span>|<span data-ttu-id="7d096-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="7d096-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="7d096-117">초</span><span class="sxs-lookup"><span data-stu-id="7d096-117">s</span></span>|<span data-ttu-id="7d096-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="7d096-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="7d096-119">wsa</span><span class="sxs-lookup"><span data-stu-id="7d096-119">wsa</span></span>|<span data-ttu-id="7d096-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="7d096-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="7d096-121">wsse</span><span class="sxs-lookup"><span data-stu-id="7d096-121">wsse</span></span>|<span data-ttu-id="7d096-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="7d096-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="7d096-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="7d096-123">wsrmp</span></span>|<span data-ttu-id="7d096-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="7d096-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="7d096-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="7d096-125">netrmp</span></span>|<span data-ttu-id="7d096-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="7d096-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="7d096-127">wsp</span><span class="sxs-lookup"><span data-stu-id="7d096-127">wsp</span></span>|<span data-ttu-id="7d096-128">(WS-Policy 1.2 또는 WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="7d096-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="7d096-129">메시징</span><span class="sxs-lookup"><span data-stu-id="7d096-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="7d096-130">시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="7d096-130">Sequence Creation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-131">는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현하여 신뢰할 수 있는 메시징 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-131"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="7d096-132">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="7d096-133">B1101: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지의 `ReplyTo`, `AcksTo` 및 `Offer/Endpoint`와 동일한 끝점 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="7d096-134">R1102: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하도록 동일한 문자열 표현을 포함하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="7d096-135">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `AcksTo`, `ReplyTo` 및 `Endpoint` 끝점 참조의 URI 부분이 동일한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="7d096-136">R1103: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-137">는 `AcksTo`에 대한 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조의 참조 매개 변수를 동일한 것으로 지정하지 않지만 동일하다고 가정하며, 승인 및 역방향 시퀀스 메시지에 `ReplyTo` 끝점 참조의 참조 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-137"> does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="7d096-138">B1104: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `Expires` 메시지에 선택적 `Offer/Expires` 또는 `CreateSequence` 요소를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="7d096-139">B1105: `CreateSequence` 메시지에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `Expires` 요소의 `CreateSequence` 값을 `Expires` 요소의 `CreateSequenceResponse` 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="7d096-140">그렇지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `Expires` 및 `Offer/Expires` 값을 읽고 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="7d096-141">B1106: `CreateSequenceResponse` 메시지에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 선택적 `Expires` 값을 읽지만 사용하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="7d096-142">B1107: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자와 응답자는 항상 `IncompleteSequenceBehavior` 및 `CreateSequence/Offer` 요소에 선택적 `CreateSequenceResponse` 요소를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="7d096-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `DiscardFollowingFirstGap` 요소에 `NoDiscard` 및 `IncompleteSequenceBehavior` 값만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="7d096-144">WS-ReliableMessaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="7d096-145">B1109: `CreateSequence`에 `Offer` 요소가 포함된 경우 단방향 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceResponse` 요소를 사용하지 않고 `Accept`로 응답하여 제공된 시퀀스를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="7d096-146">B1110: 신뢰할 수 있는 메시징 응답자가 제공된 시퀀스를 거부하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 새로 설정된 시퀀스를 오류 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="7d096-147">B1111: `CreateSequence`에 `Offer` 요소가 포함되지 않은 경우 양방향 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceRefused` 오류로 응답하여 제공된 시퀀스를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="7d096-148">R1112: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]` 끝점 참조의 `CreateSequenceResponse/Accept/AcksTo` 속성은 `CreateSequence` 메시지 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="7d096-149">R1113: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자에서 응답자로 이동하는 두 시퀀스의 모든 메시지를 같은 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-150">는 WS-ReliableMessaging을 사용하여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-150"> uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="7d096-151">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging 구현에서는 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="7d096-152">`Offer` 및 `CreateSequence`에서 WS-ReliableMessaging `CreateSequenceResponse` 메커니즘을 사용하면 상호 관련된 두 개의 역방향 시퀀스를 설정하고 모든 메시지 끝점에 적합한 세션 프로토콜을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="7d096-153">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 세션 무결성을 위한 종단 간 보호를 포함하여 세션에 대한 보안 보장을 제공하므로 같은 상대방에 보낼 메시지가 동일한 대상에 도달하는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="7d096-154">이렇게 하면 응용 프로그램 메시지에서 "피기백킹"이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="7d096-155">따라서 R1102, R1112, 및 R1113 제약 조건에 적용 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="7d096-156">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-156">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>  
    <wsa:ReplyTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>   
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>  
      </wsrm:AcksTo>  
      <wsrm:Offer>  
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>  
        <wsrm:Endpoint>  
          <wsa:Address>http://Business456.com/clientA</wsa:Address>  
        </wsrm:Endpoint>  
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      </wsrm:Offer>  
    </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="7d096-157">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      <wsrm:Accept>  
        <wsrm:AcksTo>  
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>  
        </wsrm:AcksTo>  
      </wsrm:Accept>  
    </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="closing-a-sequence"></a><span data-ttu-id="7d096-158">시퀀스 닫기</span><span class="sxs-lookup"><span data-stu-id="7d096-158">Closing a Sequence</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-159">는 신뢰할 수 있는 메시징 소스에 의해 시작된 종료에 `CloseSequence` 및 `CloseSequenceResponse` 메시지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-159"> uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="7d096-160">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 종료를 시작하지 않고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에 의해 시작된 종료를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="7d096-161">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="7d096-162">B1201: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 항상 `CloseSequence` 메시지를 보내어 시퀀스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="7d096-163">B1202: 신뢰할 수 있는 메시징 소스는 시퀀스 메시지 전체 범위의 승인을 기다린 다음 `CloseSequence` 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="7d096-164">B1203: 시퀀스에 메시지가 있으면 신뢰할 수 있는 메시징 소스에는 항상 선택적 `LastMsgNumber` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="7d096-165">R1204: 신뢰할 수 있는 메시징 대상은 `CloseSequence` 메시지를 보내어 종료를 시작하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="7d096-166">B1205: `CloseSequence` 메시지를 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 시퀀스가 완료되지 않았다고 간주하고 오류를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="7d096-167">`CloseSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-167">An example of a `CloseSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
    </wsrm:CloseSequence>  
  </s:Body>  
</s:Envelope>  
Example CloseSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:CloseSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence-termination"></a><span data-ttu-id="7d096-168">시퀀스 종료</span><span class="sxs-lookup"><span data-stu-id="7d096-168">Sequence Termination</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-169">는 `TerminateSequence/TerminateSequenceResponse` 핸드셰이크를 완료한 후 주로 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-169"> primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="7d096-170">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 종료를 시작하지 않고 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에 의해 시작된 종료를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="7d096-171">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="7d096-172">B1301: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `TerminateSequence` 핸드셰이크가 완료된 후 `CloseSequence/CloseSequenceResponse` 메시지만 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="7d096-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `LastMsgNumber` 요소가 제공된 시퀀스의 모든 `CloseSequence` 및 `TerminateSequence` 메시지에서 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="7d096-174">즉, `LastMsgNumber`가 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 없거나, 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 있으며 이러한 메시지에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="7d096-175">B1303: `TerminateSequence` 핸드셰이크 이후 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="7d096-176">신뢰할 수 있는 메시징 소스에 `TerminateSequence` 메시지를 보내기 전의 최종 승인이 있으므로 신뢰할 수 있는 메시징 대상은 시퀀스가 종료되고 리소스를 즉시 회수함을 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="7d096-177">B1304: `TerminateSequence` 핸드셰이크 이전에 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="7d096-178">신뢰할 수 있는 메시징 대상이 시퀀스에서 일치하지 않는 부분이 없음을 확인한 경우에는 클라이언트가 최종 승인을 받을 수 있도록 신뢰할 수 있는 메시징 대상이 응용 프로그램 대상에서 지정한 시간 동안 기다린 다음 리소스를 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="7d096-179">그렇지 않은 경우 신뢰할 수 있는 메시징 대상이 리소스를 바로 회수하고 응용 프로그램 대상에 `Faulted` 이벤트를 발생시켜 시퀀스에 오류가 발생하여 종료되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="7d096-180">`TerminateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-180">An example of a `TerminateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
      </wsrm:TerminateSequence>  
  </s:Body>  
</s:Envelope>  
Example TerminateSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:TerminateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequences"></a><span data-ttu-id="7d096-181">시퀀스</span><span class="sxs-lookup"><span data-stu-id="7d096-181">Sequences</span></span>  
 <span data-ttu-id="7d096-182">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="7d096-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 액세스 하는 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="7d096-184">`Sequence` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="7d096-185">승인 요청</span><span class="sxs-lookup"><span data-stu-id="7d096-185">Request Acknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-186">는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-186"> uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="7d096-187">`AckRequested` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="7d096-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="7d096-188">SequenceAcknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-189">는 WS-Reliable Messaging에 제공된 시퀀스 승인에 "피기백" 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-189"> uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="7d096-190">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="7d096-191">R1601: 두 개의 역방향 시퀀스가 설정 된 경우 사용 하 여는 `Offer` 메커니즘은 `SequenceAcknowledgement` 응용 프로그램 받는 사람된에 게 전송 된 메시지에 헤더를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="7d096-192">원격 끝점에서는 피기백된 `SequenceAcknowledgement` 헤더에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="7d096-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `SequenceAcknowledgement` 요소가 포함된 `Nack` 헤더를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-194">는 각 `Nack` 요소에 시퀀스 번호가 포함되어 있는지 확인하지만, 그렇지 않은 경우에는 `Nack` 요소와 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="7d096-195">`SequenceAcknowledgement` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="7d096-196">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="7d096-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="7d096-197">다음은 WS-ReliableMessaging 오류의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현에 적용되는 제약 조건 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="7d096-198">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="7d096-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하지 않습니다 `MessageNumberRollover` 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="7d096-200">B1702: SOAP 1.2를 통해 서비스 끝점이 해당 연결 제한에 도달하여 새 연결을 처리할 수 없는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제처럼 중첩된 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>  
  </s:Header>  
  <s:Body>  
    <s:Fault>  
      <s:Code>  
        <s:Value>s:Receiver</s:Value>  
        <s:Subcode>  
          <s:Value>wsrm:CreateSequenceRefused</s:Value>  
          <s:Subcode>  
            <s:Value>netrm:ConnectionLimitReached</s:Value>  
          </s:Subcode>  
        </s:Subcode>  
      </s:Code>  
      <s:Reason>  
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>  
      </s:Reason>  
    </s:Fault>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="7d096-201">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="7d096-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="7d096-202">WS-ReliableMessaging에서는 WS-Addressing을 사용하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-ReliableMessaging을 구현하는 경우에는 WS-Addressing 오류를 생성하고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="7d096-203">이 단원에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 WS-ReliableMessaging 계층에서 명시적으로 생성하고 전송하는 WS-Addressing 오류에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="7d096-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 전송 된 `Message Addressing Header Required` 다음 중 하나에 오류:</span><span class="sxs-lookup"><span data-stu-id="7d096-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="7d096-205">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="7d096-206">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="7d096-207">`CreateSequenceResponse`, `CloseSequenceResponse` 또는 `TerminateSequenceResponse` 메시지에 `RelatesTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="7d096-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 전송 된 `Endpoint Unavailable` 있는 수신 대기 중인 끝점이 없습니다 나타내기 위해 오류 검사에서 주소 지정 헤더를 기준으로 시퀀스를 처리할 수는 `CreateSequence` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="7d096-209">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="7d096-210">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-211">는 WS-Addressing의 두 개 버전, WS-Addressing 2004/08 [WS-ADDR]과 W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] 및 [WS-ADDR-SOAP]를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="7d096-212">WS-ReliableMessaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="7d096-213">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="7d096-214">R2101: WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="7d096-215">R2102: 단일 버전의 WS-Addressing은 `Offer` 메커니즘을 사용하여 상호 관련된 한 쌍의 역방향 시퀀스 또는 제공된 WS-ReliableMessaging 시퀀스 전체에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="7d096-216">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-217">는 WS-Reliable Messaging과 함께 SOAP 1.1 및 SOAP 1.2 모두 사용하는 것을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="7d096-218">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-219">는 보안 전송(HTTPS), WS-Security를 사용한 구성 및 WS-Secure Conversation을 사용한 구성을 통해 WS-ReliableMessaging 시퀀스를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-219"> provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="7d096-220">WS-ReliableMessaging 1.1 프로토콜, WS-Security 1.1 및 WS-Secure Conversation 1.3 프로토콜을 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="7d096-221">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="7d096-222">R2301: 개별 메시지의 무결성과 기밀성뿐만 아니라 WS-ReliableMessaging 시퀀스의 무결성을 보호하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-Secure Conversation을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="7d096-223">R2302:AWS-WS-RELIABLE Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="7d096-224">R2303: WS-ReliableMessaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="7d096-225">B2304:WS-ReliableMessaging 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="7d096-226">R2305: WS-Secure Conversation을 사용하여 구성된 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지에 `wsse:SecurityTokenReference` 요소와 `wsrm:UsesSequenceSTR` 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="7d096-227">`UsesSequenceSTR` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="7d096-228">SSL/TLS 세션을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-229">는 SSL/TLS 세션을 사용한 구성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="7d096-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrm:UsesSequenceSSL` 헤더를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="7d096-231">R2402: 신뢰할 수 있는 메시징 개시자는 `CreateSequence` 응답자에게 `wsrm:UsesSequenceSSL` 헤더가 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 보내면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="7d096-232">WS-Policy를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="7d096-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-233">는 WS-Policy의 두 개 버전, WS-Policy 1.2와 WS-Policy 1.5를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="7d096-234">WS-ReliableMessaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="7d096-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-235">는 WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion`을 사용하여 끝점 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-235"> uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="7d096-236">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="7d096-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrmn:RMAssertion` WS-Policy Assertion을 `wsdl:binding` 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-238">는 `wsdl:binding` 및 `wsdl:port` 요소에 대한 두 개 첨부 파일을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="7d096-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsp:Optional` 태그를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="7d096-240">B3003: `wsrmp:RMAssertion` WS-Policy Assertion에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsp:Optional` 태그를 무시하고 WS-RM 정책을 필수 항목으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="7d096-241">R3004: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 SSL/TLS 세션을 사용하여 구성되지 않으므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrmp:SequenceTransportSecurity`를 지정하는 정책을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="7d096-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 항상 `wsrmp:DeliveryAssurance` 요소를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="7d096-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 항상 `wsrmp:ExactlyOnce` 배달 보증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="7d096-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-ReliableMessaging 어설션의 다음과 같은 속성을 생성하고 읽으며 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`에서 이러한 속성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="7d096-245">`RMAssertion`의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-245">An example of a `RMAssertion`.</span></span>  
  
    ```xml  
    <wsrmp:RMAssertion>  
      <wsp:Policy>  
        <wsrmp:SequenceSTR/>  
        <wsrmp:DeliveryAssurance>  
          <wsp:Policy>  
            <wsrmp:ExactlyOnce/>  
            <wsrmp:InOrder/>  
          </wsp:Policy>  
        </wsrmp:DeliveryAssurance>  
      </wsp:Policy>  
      <netrmp:InactivityTimeout Milliseconds="600000"/>  
      <netrmp:AcknowledgementInterval Milliseconds="200"/>  
    </wsrmp:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="7d096-246">흐름 제어 WS-ReliableMessaging 확장</span><span class="sxs-lookup"><span data-stu-id="7d096-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-247">는 WS-ReliableMessaging 확장성을 사용하여 선택적으로 시퀀스 메시지 흐름을 보다 엄격하게 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="7d096-248">흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``boolean` 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="7d096-249">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="7d096-250">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `netrm:BufferRemaining` 헤더의 요소 확장성에 `SequenceAcknowledgement` 요소를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="7d096-251">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용하는 경우에도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `netrm:BufferRemaining` 헤더에 `SequenceAcknowledgement` 요소가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="7d096-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 `netrm:BufferRemaining`을 사용하여 버퍼링할 수 있는 새 메시지 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="7d096-253">B4004:When 신뢰할 수 있는 메시징 흐름 제어를 사용 하도록 설정 된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 의 값을 사용 하는 신뢰할 수 있는 메시징 소스 `netrm:BufferRemaining` 스로틀 메시지 전송에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="7d096-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 0과 4096 사이의 `netrm:BufferRemaining` 정수 값을 생성하고 0과 `xs:int`의 `maxInclusive` 값 214748364 사이의 정수 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="7d096-255">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="7d096-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="7d096-256">이 단원에서는 WS-ReliableMessaging이 다른 메시지 교환 패턴에 사용되는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="7d096-257">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="7d096-258">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="7d096-259">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="7d096-260">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="7d096-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="7d096-261">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d096-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-262">는 각각 한 개의 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-263">는 HTTP 요청을 사용하여 개시자의 모든 메시지를 응답자에게 전송하고 HTTP 응답을 사용하여 응답자의 모든 메시지를 개시자에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="7d096-264">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-265">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 없는 `Offer` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7d096-266">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 응답에 `CreateSequenceResponse` 요소가 없는 `Accept` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="7d096-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="7d096-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="7d096-268">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지와 오류 메시지를 제외한 모든 메시지의 회신에 대한 승인을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="7d096-269">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 항상 HTTP 응답에 대한 독립 실행형 승인을 모든 시퀀스 및 `AckRequested` 메시지에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="7d096-270">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="7d096-271">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CloseSequence` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7d096-272">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `CloseSequenceResponse` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="7d096-273">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `TerminateSequence` 메시지를 전송하고 HTTP 응답에 `TerminateSequenceResponse` 메시지를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7d096-275">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `TerminateSequenceResponse` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="7d096-276">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="7d096-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="7d096-277">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d096-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-278">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-279">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7d096-280">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="7d096-281">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-282">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 없는 `Offer` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7d096-283">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 요청에 `CreateSequenceResponse` 요소가 없는 `Accept` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="7d096-284">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="7d096-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="7d096-285">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d096-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-286">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="7d096-287">이 메시지 교환 패턴은 제한된 방식으로 `Request/Reply`, `Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-288">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7d096-289">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="7d096-290">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-291">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7d096-292">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인한 다음 시퀀스를 만들고 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="7d096-293">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="7d096-293">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-294">는 두 개의 시퀀스를 한 개의 전체 이중 세션으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-294"> treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="7d096-295">한 개의 시퀀스를 오류 처리하는 오류를 생성하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 원격 끝점이 두 시퀀스를 오류 처리한다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="7d096-296">한 개의 시퀀스를 오류 처리하는 오류를 읽으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 시퀀스를 오류 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-297">에서는 해당 아웃바운드 시퀀스를 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="7d096-298">반대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인바운드 시퀀스를 닫고 해당 아웃바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="7d096-299">요청-회신 및 단방향의 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="7d096-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="7d096-300">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d096-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-301">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 단방향 및 요청-회신 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-302">는 HTTP 요청을 사용하여 개시자의 모든 메시지를 응답자에게 전송하고 HTTP 응답을 사용하여 응답자의 모든 메시지를 개시자에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="7d096-303">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-304">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7d096-305">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 응답에 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="7d096-306">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="7d096-306">One-way Message</span></span>  
 <span data-ttu-id="7d096-307">단방향 메시지 교환을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 요청 시퀀스 메시지를 전송하고 HTTP 응답에 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="7d096-308">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="7d096-309">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="7d096-310">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="7d096-310">Two Way Messages</span></span>  
 <span data-ttu-id="7d096-311">양방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="7d096-312">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="7d096-313">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="7d096-314">단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="7d096-315">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="7d096-315">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-316">는 양방향 메시지 교환 프로토콜 상관 관계에 HTTP 요청-회신 상관 관계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-316"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="7d096-317">따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 응답에 `SequenceAcknowledgement`, 응용 프로그램 회신 또는 오류가 포함되지 않고 요청 시퀀스 메시지가 승인되는 경우 요청 시퀀스 메시지 다시 시도를 중지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="7d096-318">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신이 상호 관련된 요청의 HTTP 응답에 회신을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="7d096-319">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="7d096-320">모든 단방향 요청 시퀀스 메시지에 대한 모든 회신 시퀀스 메시지와 승인을 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에서 요청 시퀀스에 대한 `CloseSequence` 메시지를 전송하고 HTTP 응답에 `CloseSequenceResponse`를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="7d096-321">요청 시퀀스를 닫으면 회신 시퀀스가 암시적으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="7d096-322">즉, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자에 `SequenceAcknowledgement` 메시지에 대한 회신 시퀀스의 최종 `CloseSequence`가 포함되고 회신 시퀀스에 `CloseSequence` 교환이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="7d096-323">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 모든 회신에 승인했는지 확인하고 HTTP 응답에 `CloseSequenceResponse` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="7d096-324">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-325">`CloseSequenceResponse` 메시지를 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에서 요청 시퀀스에 대한 `TerminateSequence` 메시지를 전송하고 HTTP 응답에 `TerminateSequenceResponse`를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="7d096-326">`CloseSequence` 교환과 마찬가지로 요청 시퀀스를 종료하면 회신 시퀀스가 암시적으로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="7d096-327">즉, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자에 `SequenceAcknowledgement` 메시지에 대한 회신 시퀀스의 최종 `TerminateSequence`가 포함되고 회신 시퀀스에 `TerminateSequence` 교환이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="7d096-328">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `TerminateSequenceResponse` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="7d096-329">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="7d096-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="7d096-330">바인딩</span><span class="sxs-lookup"><span data-stu-id="7d096-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-331">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 요청-회신 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="7d096-332">이 메시지 교환 패턴은 제한된 방식으로 `Duplex, Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-333">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7d096-334">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="7d096-335">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="7d096-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="7d096-336">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7d096-337">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인한 다음 시퀀스를 만들고 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="7d096-338">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="7d096-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="7d096-339">다음 사항은 모든 상호 관련된 요청 및 회신에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-340">는 모든 응용 프로그램 요청 메시지에 `ReplyTo` 끝점 참조 및 `MessageId`가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-341">는 로컬 끝점 참조를 각 응용 프로그램 요청 메시지의 `ReplyTo`로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="7d096-342">로컬 끝점 참조는 개시자에 대한 `CreateSequence` 메시지의 `ReplyTo`와 응답자에 대한 `CreateSequence` 메시지의 `To`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-343">는 들어오는 요청 메시지에 `MessageId` 및 `ReplyTo`가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-344">는 모든 응용 프로그램 요청 메시지의 `ReplyTo` 끝점 참조 URI가 앞에서 정의된 대로 로컬 끝점 참조와 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d096-345">는 모든 회신에 올바른 `RelatesTo` 및 `To` 헤더와 `wsa` 요청/회신 상관 관계 규칙이 차례로 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d096-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
