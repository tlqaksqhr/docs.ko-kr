---
title: "Reliable Messaging 프로토콜 버전 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a32c16067446459817e9943c2d729a67373a0333
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="9866e-102">Reliable Messaging 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="9866e-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="9866e-103">이 항목에서는 HTTP 전송을 사용하여 상호 운용에 필요한 WS-ReliableMessaging February 2005(버전 1.0) 프로토콜의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-104">는 이 항목에서 설명한 제약 조건 및 확인된 내용과 함께 WS-Reliable Messaging 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-104"> follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="9866e-105">WS-ReliableMessaging 버전 1.0 프로토콜은 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 이상에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="9866e-106">WS-Reliable Messaging February 2005 프로토콜은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="9866e-107">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="9866e-108">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="9866e-109">응답자: 개시자의 요청을 받은 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="9866e-110">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="9866e-111">접두사</span><span class="sxs-lookup"><span data-stu-id="9866e-111">Prefix</span></span>|<span data-ttu-id="9866e-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9866e-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="9866e-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="9866e-113">wsrm</span></span>|<span data-ttu-id="9866e-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="9866e-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="9866e-115">netrm</span><span class="sxs-lookup"><span data-stu-id="9866e-115">netrm</span></span>|<span data-ttu-id="9866e-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="9866e-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="9866e-117">s</span><span class="sxs-lookup"><span data-stu-id="9866e-117">s</span></span>|<span data-ttu-id="9866e-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="9866e-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="9866e-119">wsa</span><span class="sxs-lookup"><span data-stu-id="9866e-119">wsa</span></span>|<span data-ttu-id="9866e-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="9866e-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="9866e-121">wsse</span><span class="sxs-lookup"><span data-stu-id="9866e-121">wsse</span></span>|<span data-ttu-id="9866e-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="9866e-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="9866e-123">메시징</span><span class="sxs-lookup"><span data-stu-id="9866e-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="9866e-124">시퀀스 설정 메시지</span><span class="sxs-lookup"><span data-stu-id="9866e-124">Sequence Establishment Messages</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-125">는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현하여 신뢰할 수 있는 메시지 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-125"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="9866e-126">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9866e-127">B1101: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 `CreateSequence` 메시지에서 선택적 Expires 요소를 생성하지 않거나 `CreateSequence` 메시지에 `Offer` 요소가 포함된 경우 `Expires` 요소에서 선택적 `Offer` 요소를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="9866e-128">B1102:에 액세스할 때는 `CreateSequence` 메시지는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `Responder` 둘 다 받을 `Expires` 존재 않지만 해당 값을 사용 하지 않는 경우 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="9866e-129">WS-Reliable Messaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="9866e-130">R1103: `CreateSequence`에 `Offer` 요소가 있는 경우 신뢰할 수 있는 메시징 응답자는 `CreateSequenceResponse` 요소가 포함된 `wsrm:Accept`와 함께 시퀀스 및 응답을 수락하여 상호 관련된 두 개의 역방향 시퀀스를 구성하거나 `CreateSequence` 요청을 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="9866e-131">R1104: 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지는 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="9866e-132">R1105: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="9866e-133">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `AcksTo` 및 `ReplyTo` EPR(끝점 참조)의 URI 부분이 동일한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="9866e-134">R1106: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-135">는 `AcksTo`에 대한 `ReplyTo` 및 `CreateSequence`의 [참조 매개 변수]를 동일한 것으로 지정하지 않지만 동일하다고 가정하며, 승인 및 역방향 시퀀스 메시지에 `ReplyTo` 끝점 참조의 [참조 매개 변수]를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-135"> does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="9866e-136">R1107: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지를 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="9866e-137">R1108: Offer 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]`의 `wsrm:AcksTo` 요소에 대한 `wsrm:Accept` 끝점 자식 요소의 `CreateSequenceResponse` 속성은 `CreateSequence`의 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="9866e-138">R1109: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자가 보낸 메시지 및 응답자의 메시지 승인을 같은 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-139">는 WS-Reliable Messaging을 사용하여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-139"> uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-140"> WS-Reliable Messaging 구현에서는 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-140">'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="9866e-141">Ws-reliable Messaging `Offer` 메커니즘 `CreateSequence` / `CreateSequenceResponse` 두 상관 관계가 지정 된 역방향 시퀀스를 설정할 수 있습니다 하 고 모든 메시지 끝점에는 적합 한 세션 프로토콜을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="9866e-142">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 세션 무결성을 위한 종단 간 보호를 포함하여 세션에 대한 보안 보장을 제공하므로 같은 상대방에 보낼 메시지가 동일한 대상에 도달하는지 확인하는 것이 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="9866e-143">이렇게 하면 응용 프로그램 메시지에서 피기백킹이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="9866e-144">따라서 제약 조건 R1104, R1105, 및 R1108은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="9866e-145">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-145">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence  
    </a:Action>  
    <a:ReplyTo>  
      <a:Address>          
         http://Business456.com/clientA        
      </a:Address>  
    </a:ReplyTo>  
    <a:MessageID>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:MessageID>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
       <wsa:Address>  
         http://Business456.com/clientA  
       </wsa:Address>  
     </wsrm:AcksTo>  
     <wsrm:Offer>  
      <wsrm:Identifier>  
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496  
      </wsrm:Identifier>  
     </wsrm:Offer>  
   </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="9866e-146">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse  
    </a:Action>  
    <a:RelatesTo>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:RelatesTo>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
   <wsrm:CreateSequenceResponse>  
    <Identifier>  
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386  
    </Identifier>  
    <Accept>  
    <AcksTo>  
      <a:Address>  
        http://BusinessABC.com/serviceA  
      </a:Address>  
    </AcksTo>  
    </Accept>  
   </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence"></a><span data-ttu-id="9866e-147">Sequence</span><span class="sxs-lookup"><span data-stu-id="9866e-147">Sequence</span></span>  
 <span data-ttu-id="9866e-148">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="9866e-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 액세스 하는 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="9866e-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 항상 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage의 동작 URI와 본문이 비어 있는 마지막 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="9866e-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 동작 URI가 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage가 아닌 한 `LastMessage` 요소가 포함된 시퀀스 헤더가 있는 메시지를 수신하고 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="9866e-152">시퀀스 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-152">An example of a Sequence Header.</span></span>  
  
```xml  
<wsrm:Sequence>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
  <wsrm:MessageNumber>  
    10  
  </wsrm:MessageNumber>  
  <wsrm:LastMessage/>  
 </wsrm:Sequence>  
```  
  
### <a name="ackrequested-header"></a><span data-ttu-id="9866e-153">AckRequested 헤더</span><span class="sxs-lookup"><span data-stu-id="9866e-153">AckRequested Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-154">는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-154"> uses `AckRequested` Header as a keep-alive mechanism.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-155">는 선택적 `MessageNumber` 요소를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-155"> does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="9866e-156">`AckRequested` 요소가 포함된 `MessageNumber` 헤더가 있는 메시지를 수신하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `MessageNumber` 요소의 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="9866e-157">SequenceAcknowledgement 헤더</span><span class="sxs-lookup"><span data-stu-id="9866e-157">SequenceAcknowledgement Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-158">는 WS-Reliable Messaging에 제공된 시퀀스 승인에 피기백 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-158"> uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="9866e-159">R1401: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `SequenceAcknowledgement` 헤더가 받는 사람에게 전송된 응용 프로그램 메시지에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="9866e-160">B1402: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 시퀀스 메시지를 받기 전에 승인을 생성해야 하는 경우(예를 들어, `AckRequested` 메시지를 충족해야 하는 경우) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 0-0 범위가 포함된 `SequenceAcknowledgement` 헤더를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="9866e-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `SequenceAcknowledgement` 요소가 포함된 `Nack` 헤더를 생성하지 않지만 `Nack` 요소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="9866e-162">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="9866e-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="9866e-163">다음은 WS-Reliable Messaging 오류의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현에 적용되는 제약 조건 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="9866e-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `MessageNumberRollover` 오류를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="9866e-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점이 생성 될 수 있습니다 `CreateSequenceRefused` 사양에 설명 된 대로 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="9866e-166">B1503:When 서비스 끝점에서 연결 제한에 도달 하 고 새 연결을 처리할 수 없습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추가 생성 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
    ```xml  
    <s:Envelope>  
      <s:Header>  
        <wsa:Action>  
          http://schemas.xmlsoap.org/ws/2005/08/addressing/fault  
        </wsa:Action>  
      </s:Header>  
      <s:Body>  
        <s:Fault>  
          <s:Code>  
            <s:Value>  
              s:Receiver  
            </s:Value>  
            <s:Subcode>  
              <s:Value>  
                wsrm:CreateSequenceRefused  
              </s:Value>  
              <s:Subcode>  
                <s:Value>  
                  netrm:ConnectionLimitReached  
                </s:Value>  
              </s:Subcode>  
            </s:Subcode>  
          </s:Code>  
          <s:Reason>  
            <s:Text xml:lang="en">  
              [Reason]  
            </s:Text>  
          </s:Reason>  
        </s:Fault>  
      </s:Body>  
    </s:Envelope>  
    ```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="9866e-167">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="9866e-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="9866e-168">WS-Reliable Messaging에서는 WS-Addressing을 사용하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-Reliable Messaging을 구현하는 경우에는 WS-Addressing 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="9866e-169">이 단원에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 WS-Reliable Messaging 계층에 명시적으로 생성하는 WS-Addressing 오류에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="9866e-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 다음 중 하나에 메시지 주소 지정 헤더가 필요 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="9866e-171">메시지에 `Sequence` 헤더 및 `Action` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="9866e-172">`CreateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="9866e-173">`CreateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="9866e-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 누락 된 메시지에 대 한 응답이 아닌 지원 되지 않는 기능 오류를 생성 한 `Sequence` 헤더에는 `Action` Ws-reliable Messaging 사양에 인식 된 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="9866e-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점에서 사용할 수 없는 끝점의 검사를 기준으로 시퀀스를 처리 하지 않습니다 나타내는 오류를 생성 된 `CreateSequence` 메시지 주소 지정 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="9866e-176">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="9866e-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="9866e-177">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="9866e-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-178">는 WS-Addressing의 두 개 버전, WS-Addressing 2004/08 [WS-ADDR]과 W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] 및 [WS-ADDR-SOAP]를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="9866e-179">WS-Reliable Messaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="9866e-180">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9866e-181">R2101: 두 Ws-addressing 2004/08 및 Ws-addressing 1.0 Ws-reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="9866e-182">지정 된 Ws-reliable Messaging 시퀀스 또는 한 쌍의 역방향 시퀀스를 사용 하 여 상관 관계가 지정 된 전체에서 R2102:A 단일 버전의 Ws-addressing을 사용 해야 합니다는 `wsrm:Offer` 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="9866e-183">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="9866e-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-184">는 WS-Reliable Messaging과 함께 SOAP 1.1 및 SOAP 1.2를 모두 사용할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="9866e-185">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="9866e-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-186">는 보안 전송(HTTPS), WS-Security를 사용한 구성 및 WS-Secure Conversation을 사용한 구성을 통해 WS-Reliable Messaging 시퀀스를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="9866e-187">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9866e-188">R2301: 개별 메시지의 무결성 뿐만 아니라 Ws-reliable Messaging 시퀀스의 무결성과 기밀성을 보호 하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Ws-secure Conversation을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="9866e-189">R2302:AWS-Ws-reliable Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="9866e-190">R2303: WS-Reliable Messaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="9866e-191">B2304:WS-신뢰할 수 있는 메시징 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="9866e-192">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소스는 `wsse:SecurityTokenReference` 메시지의 요소 확장성 섹션에 `CreateSequence` 요소를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="9866e-193">R2305:When Ws-secure Conversation으로 구성 된 `CreateSequence` 메시지에 포함 해야 합니다는 `wsse:SecurityTokenReference` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="9866e-194">WS-Reliable Messaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="9866e-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-195">는 WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion`을 사용하여 끝점 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-195"> uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="9866e-196">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9866e-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrm:RMAssertion` WS-Policy Assertion을 `wsdl:binding` 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-198">는 `wsdl:binding` 및 `wsdl:port` 요소에 대한 두 개 첨부 파일을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="9866e-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Ws-reliable Messaging 어설션의 다음과 같은 선택적 속성을 지원 하 고를 제어에 제공 된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="9866e-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="9866e-200">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="9866e-201">흐름 제어 WS-Reliable Messaging 확장</span><span class="sxs-lookup"><span data-stu-id="9866e-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-202">는 WS-Reliable Messaging 확장성을 사용하여 선택적으로 시퀀스 메시지 흐름을 보다 엄격하게 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="9866e-203">흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``bool` 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="9866e-204">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9866e-205">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `netrm:BufferRemaining` 헤더의 요소 확장성에 `SequenceAcknowledgement` 요소를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="9866e-206">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `netrm:BufferRemaining` 요소를 `SequenceAcknowledgement` 헤더에 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        http://fabrikam123.com/abc  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>  
        8  
      </netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="9866e-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `netrm:BufferRemaining`을 사용하여 신뢰할 수 메시징 대상이 버퍼링할 수 있는 새 메시지 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="9866e-208">B4004:는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 서비스 신뢰할 수 있는 메시징 대상 응용 프로그램이 신속 하 게 메시지를 받을 수 있을 경우 전송할 메시지의 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="9866e-209">신뢰할 수 있는 메시징 대상은 메시지를 버퍼링하고 요소의 값을 0으로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="9866e-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 0과 4096 사이의 `netrm:BufferRemaining` 정수 값을 생성하고 0과 `xs:int`의 `maxInclusive` 값 214748364 사이의 정수 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="9866e-211">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="9866e-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="9866e-212">이 단원에서는 WS-Reliable Messaging이 다른 메시지 교환 패턴에 사용되는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="9866e-213">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="9866e-214">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="9866e-215">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="9866e-216">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="9866e-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9866e-217">바인딩</span><span class="sxs-lookup"><span data-stu-id="9866e-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-218">는 각각 한 개의 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-219">는 HTTP 요청을 사용하여 RMS의 모든 메시지를 RMD에게 전송하고 HTTP 응답을 사용하여 RMD의 모든 메시지를 RMS에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-219"> uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9866e-220">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-221">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하지 않는 `CreateSequence` 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="9866e-222">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="9866e-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지를 통해 `CreateSequenceResponse` 요청에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="9866e-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="9866e-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="9866e-225">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지와 오류 메시지를 제외한 모든 메시지의 회신에 대한 승인을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="9866e-226">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 항상 시퀀스 및 `AckRequested` 메시지 모두에 대한 응답으로 독립 실행형 승인을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="9866e-227">TerminateSequence 메시지</span><span class="sxs-lookup"><span data-stu-id="9866e-227">TerminateSequence message</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-228">는 `TerminateSequence`를 단방향 작업으로 처리합니다. 즉, HTTP 응답에는 비어 있는 본문과 HTTP 202 상태 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-228"> treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="9866e-229">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="9866e-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9866e-230">바인딩</span><span class="sxs-lookup"><span data-stu-id="9866e-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-231">는 각각 한 개의 인바운드 및 아웃바운드 Http 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-232">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9866e-233">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9866e-234">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-235">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하지 않는 `CreateSequence` 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="9866e-236">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="9866e-237">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceResponse` 끝점 참조를 사용하여 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="9866e-238">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="9866e-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9866e-239">바인딩</span><span class="sxs-lookup"><span data-stu-id="9866e-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-240">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-241">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9866e-242">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9866e-243">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-244">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="9866e-245">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-246">는 `CreateSequenceResponse`의 `CreateSequence` 끝점 참조로 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="9866e-247">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="9866e-247">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-248">는 두 개의 시퀀스를 한 개의 전체 이중 세션으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-248"> treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="9866e-249">한 개의 시퀀스를 오류 처리하는 오류를 생성하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 원격 끝점이 두 시퀀스를 오류 처리한다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="9866e-250">한 개의 시퀀스를 오류 처리하는 오류를 읽으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 시퀀스를 오류 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-251">에서는 해당 아웃바운드 시퀀스를 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="9866e-252">반대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인바운드 시퀀스를 닫고 해당 아웃바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="9866e-253">요청-회신, 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="9866e-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9866e-254">바인딩</span><span class="sxs-lookup"><span data-stu-id="9866e-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-255">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 단방향 및 요청-회신 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-256">는 HTTP 요청을 사용하여 요청 시퀀스의 메시지를 전송하고 HTTP 응답을 사용하여 회신 시퀀스의 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9866e-257">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-258">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="9866e-259">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="9866e-260">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지를 통해 `CreateSequenceResponse` 요청에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="9866e-261">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="9866e-261">One-way Message</span></span>  
 <span data-ttu-id="9866e-262">단방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="9866e-263">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="9866e-264">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="9866e-265">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="9866e-265">Two Way Messages</span></span>  
 <span data-ttu-id="9866e-266">양방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="9866e-267">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="9866e-268">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="9866e-269">단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="9866e-270">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="9866e-270">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-271">는 양방향 메시지 교환 프로토콜 상관 관계에 HTTP 요청-회신 상관 관계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-271"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="9866e-272">따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 응답에 승인, 사용자 메시지 또는 오류가 포함되지 않고 요청 시퀀스 메시지가 승인되는 경우 요청 시퀀스 메시지 다시 시도를 중지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="9866e-273">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신과 상호 관련된 요청의 HTTP 요청 레그에서 회신을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="9866e-274">LastMessage 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="9866e-275">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청 레그에서 본문이 비어 있는 마지막 메시지를 생성하여 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-276">는 응답이 필요하지만 실제 응답 메시지를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="9866e-277">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 본문이 비어 있는 마지막 메시지를 사용하여 요청 시퀀스의 본문이 비어 있는 마지막 메시지에 대해 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="9866e-278">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자가 동작 URI가 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage가 아닌 마지막 메시지를 수신할 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 마지막 메시지를 사용하여 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="9866e-279">양방향 메시지 교환 프로토콜의 경우 마지막 메시지에 응용 프로그램 메시지가 포함되어 있으며, 단방향 메시지 교환 프로토콜의 경우 마지막 메시지는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="9866e-280">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 본문이 비어 있는 마지막 메시지에 대한 승인이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="9866e-281">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-282">모든 요청이 유효한 회신을 수신하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청 레그에 요청 시퀀스의 `TerminateSequence` 메시지를 생성하고 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-283">는 응답이 필요하지만 실제 응답 메시지를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="9866e-284">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 `TerminateSequence` 메시지를 사용하여 요청 시퀀스의 `TerminateSequence` 메시지에 대해 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="9866e-285">정상적인 종료 시퀀스에서 두 `TerminateSequence` 메시지 모두에 전체 범위의 `SequenceAcknowledgement`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="9866e-286">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="9866e-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9866e-287">바인딩</span><span class="sxs-lookup"><span data-stu-id="9866e-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-288">는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 요청-회신 메시지 교환 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-289">는 HTTP 요청을 사용하여 모든 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9866e-290">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9866e-291">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="9866e-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9866e-292">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="9866e-293">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9866e-294">는 `CreateSequenceResponse`의 `CreateSequence` 끝점 참조로 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="9866e-295">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="9866e-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="9866e-296">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 모든 응용 프로그램 요청 메시지에 `MessageId` 및 `ReplyTo` 끝점 참조가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="9866e-297">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 각 응용 프로그램 요청 메시지에 `CreateSequence` 메시지의 `ReplyTo` 끝점 참조를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="9866e-298">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자의 경우 들어오는 요청 메시지에 `MessageId` 및 `ReplyTo`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="9866e-299">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 및 모든 응용 프로그램 요청 메시지의 끝점 참조 URI가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9866e-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
