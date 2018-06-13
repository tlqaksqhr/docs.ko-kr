---
title: Reliable Messaging 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: f45a0d5e50e9ab8a07a203d2c40ad36ef298a40d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497054"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="d832b-102">Reliable Messaging 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="d832b-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="d832b-103">이 항목에서는 Ws-reliable Messaging에 대 한 Windows Communication Foundation (WCF) 구현 세부 정보를 다룹니다 HTTP 전송을 사용 하 여 상호 운용에 필요한 2005 년 2 월 (버전 1.0) 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="d832b-104">WCF에는 제약 조건 및 확인 된이 항목에 설명 된 내용과 함께 Ws-reliable Messaging 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="d832b-105">WS-ReliableMessaging 버전 1.0 프로토콜은 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 이상에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="d832b-106">Ws-reliable Messaging 2005년 2월 프로토콜에서 WCF에서 구현 되는 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="d832b-107">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="d832b-108">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="d832b-109">응답자: 개시자의 요청을 받은 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="d832b-110">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="d832b-111">접두사</span><span class="sxs-lookup"><span data-stu-id="d832b-111">Prefix</span></span>|<span data-ttu-id="d832b-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d832b-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="d832b-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="d832b-113">wsrm</span></span>|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|<span data-ttu-id="d832b-114">netrm</span><span class="sxs-lookup"><span data-stu-id="d832b-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="d832b-115">s</span><span class="sxs-lookup"><span data-stu-id="d832b-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="d832b-116">wsa</span><span class="sxs-lookup"><span data-stu-id="d832b-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="d832b-117">wsse</span><span class="sxs-lookup"><span data-stu-id="d832b-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a><span data-ttu-id="d832b-118">메시징</span><span class="sxs-lookup"><span data-stu-id="d832b-118">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="d832b-119">시퀀스 설정 메시지</span><span class="sxs-lookup"><span data-stu-id="d832b-119">Sequence Establishment Messages</span></span>  
 <span data-ttu-id="d832b-120">WCF 구현 `CreateSequence` 및 `CreateSequenceResponse` 신뢰할 수 있는 메시지 시퀀스를 설정 하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="d832b-121">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-121">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="d832b-122">B1101: WCF 초기자에서 선택적 Expires 요소를 생성 하지 않습니다는 `CreateSequence` 메시지 또는 경우에는 경우는 `CreateSequence` 메시지에 포함 되어는 `Offer` 요소, 선택적 `Expires` 요소에는 `Offer` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="d832b-123">B1102:에 액세스할 때의 `CreateSequence` 메시지, WCF`Responder` 둘 다 송수신 `Expires` 존재 않지만 해당 값을 사용 하지 않는 경우 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="d832b-124">WS-Reliable Messaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="d832b-125">R1103: `CreateSequence`에 `Offer` 요소가 있는 경우 신뢰할 수 있는 메시징 응답자는 `CreateSequenceResponse` 요소가 포함된 `wsrm:Accept`와 함께 시퀀스 및 응답을 수락하여 상호 관련된 두 개의 역방향 시퀀스를 구성하거나 `CreateSequence` 요청을 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="d832b-126">R1104: 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지는 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="d832b-127">R1105: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="d832b-128">WCF 응답자 확인의 URI 부분이 `AcksTo` 및 `ReplyTo` 시퀀스를 만들기 전에 EPRs는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="d832b-129">R1106: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     <span data-ttu-id="d832b-130">WCF에서는 따르지 않고 가정의 [참조 매개 변수] `AcksTo` 및 `ReplyTo` 에 `CreateSequence` 동일 하다 고 [참조 매개 변수]를 사용 하 여에서 `ReplyTo` 승인 및 역방향 시퀀스 메시지에 대 한 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="d832b-131">R1107: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지를 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="d832b-132">R1108: Offer 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]`의 `wsrm:AcksTo` 요소에 대한 `wsrm:Accept` 끝점 자식 요소의 `CreateSequenceResponse` 속성은 `CreateSequence`의 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="d832b-133">R1109: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자가 보낸 메시지 및 응답자의 메시지 승인을 같은 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     <span data-ttu-id="d832b-134">WCF를 사용 하 여 Ws-reliable Messaging 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="d832b-135">WCF의 Ws-reliable Messaging 구현에서는 단방향, 요청-회신 및 전체에 대 한 신뢰할 수 있는 세션 이중 메시징 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="d832b-136">Ws-reliable Messaging `Offer` 메커니즘 `CreateSequence` / `CreateSequenceResponse` 두 상관 관계가 지정 된 역방향 시퀀스를 설정할 수 있습니다 하 고 모든 메시지 끝점에는 적합 한 세션 프로토콜을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="d832b-137">WCF는 세션 무결성에 대 한 종단 간 보호를 포함 하는 세션에 대 한 보안 보장을 제공 하므로 같은 상대방에 보낼 메시지가 동일한 대상에 도착 하 되도록 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="d832b-138">이렇게 하면 응용 프로그램 메시지에서 피기백킹이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="d832b-139">따라서 제약 조건 R1104, R1105, 및 R1108 WCF에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>  
  
 <span data-ttu-id="d832b-140">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-140">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="d832b-141">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-141">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="d832b-142">Sequence</span><span class="sxs-lookup"><span data-stu-id="d832b-142">Sequence</span></span>  
 <span data-ttu-id="d832b-143">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-143">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="d832b-144">B1201:WCF 생성 하 고 액세스 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="d832b-145">B1202:WCF 사용 하는 본문이 비어 있는 마지막 메시지 동작 URI는 항상 생성의 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-145">B1202:WCF always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="d832b-146">B1203: WCF 수신 하 고 포함 된 시퀀스 헤더가 있는 메시지를 배달 한 `LastMessage` 요소가 동작 URI가 아닌 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="d832b-147">시퀀스 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-147">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="d832b-148">AckRequested 헤더</span><span class="sxs-lookup"><span data-stu-id="d832b-148">AckRequested Header</span></span>  
 <span data-ttu-id="d832b-149">WCF를 사용 하 여 `AckRequested` 헤더를 연결 유지 메커니즘으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="d832b-150">WCF 선택적 생성 하지 않습니다 `MessageNumber` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="d832b-151">포함 된 메시지를 받으면는 `AckRequested` 헤더를 포함 하는 `MessageNumber` 요소인 WCF 무시는 `MessageNumber` 다음 예제에 나와 있는 것 처럼 요소의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="d832b-152">SequenceAcknowledgement 헤더</span><span class="sxs-lookup"><span data-stu-id="d832b-152">SequenceAcknowledgement Header</span></span>  
 <span data-ttu-id="d832b-153">WCF는 Ws-reliable Messaging에 제공 된 시퀀스 승인에 피기백 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="d832b-154">R1401: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `SequenceAcknowledgement` 헤더가 받는 사람에게 전송된 응용 프로그램 메시지에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="d832b-155">B1402: WCF 시퀀스 메시지를 받기 전에 승인을 생성 해야 하는 경우 (예: 충족 하기 위해는 `AckRequested` 메시지), WCF에서는 오류가 발생 하는 `SequenceAcknowledgement` 다음 예제에 나와 있는 것 처럼 범위 0-0에 포함 된 헤더 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="d832b-156">B1403: WCF 생성 하지 않습니다 `SequenceAcknowledgement` 들어 있는 헤더는 `Nack` 요소가 있지만 지원 `Nack` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="d832b-157">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="d832b-157">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="d832b-158">다음은 Ws-reliable Messaging 오류의 WCF 구현에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="d832b-159">B1501: WCF 생성 하지 않습니다 `MessageNumberRollover` 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="d832b-160">B1502:WCF 끝점이 생성 될 수 있습니다 `CreateSequenceRefused` 사양에 설명 된 대로 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="d832b-161">WCF에서는 오류가 발생 하는 추가, 서비스 끝점 B1503:When 연결 제한에 도달 하 고 새 연결을 처리할 수 없습니다 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="d832b-162">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="d832b-162">WS-Addressing Faults</span></span>  
 <span data-ttu-id="d832b-163">Ws-reliable Messaging에서는 Ws-addressing 때문에 WCF Ws-reliable Messaging 구현 Ws-addressing 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="d832b-164">이 섹션에서는 WCF Ws-reliable Messaging 계층에 명시적으로 생성 하는 Ws-addressing 오류를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="d832b-165">다음 중 하나에 B1601:WCF 메시지 주소 지정 헤더가 필요 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="d832b-166">메시지에 `Sequence` 헤더 및 `Action` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-166">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="d832b-167">`CreateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="d832b-168">`CreateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="d832b-169">B1602:WCF 탈퇴 누락 된 메시지 오류를 지원 되지 않는 기능을 생성 한 `Sequence` 헤더에는 `Action` Ws-reliable Messaging 사양에 인식 된 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="d832b-170">끝점에서 사용할 수 없는 끝점의 검사를 기준으로 시퀀스를 처리 하지 않습니다 나타내는 오류를 생성 하는 B1603:WCF는 `CreateSequence` 메시지 주소 지정 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="d832b-171">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="d832b-171">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="d832b-172">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="d832b-172">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="d832b-173">WCF는 Ws-addressing의 두 가지 버전을 지원: Ws-addressing 2004/08 [WS-ADDR] 및 W3C Ws-addressing 1.0 Recommendations [WS ADDR 코어] 및 [WS ADDR SOAP].</span><span class="sxs-lookup"><span data-stu-id="d832b-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="d832b-174">WS-Reliable Messaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="d832b-175">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-175">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="d832b-176">R2101: 두 Ws-addressing 2004/08 및 Ws-addressing 1.0 Ws-reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="d832b-177">지정 된 Ws-reliable Messaging 시퀀스 또는 한 쌍의 역방향 시퀀스를 사용 하 여 상관 관계가 지정 된 전체에서 R2102:A 단일 버전의 Ws-addressing을 사용 해야 합니다는 `wsrm:Offer` 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="d832b-178">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="d832b-178">Composition with SOAP</span></span>  
 <span data-ttu-id="d832b-179">WCF는 SOAP 1.1과 SOAP 1.2 Ws-reliable Messaging과 함께 둘 다의 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="d832b-180">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="d832b-180">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="d832b-181">WCF 보안 전송 (HTTPS), Ws-security를 사용 하 여 구성 및 컴퍼지션 Ws-secure Conversation을 사용한 Ws-reliable Messaging 시퀀스에 대 한 보호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="d832b-182">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-182">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="d832b-183">R2301: 개별 메시지의 무결성 뿐만 아니라 Ws-reliable Messaging 시퀀스의 무결성과 기밀성을 보호 하려면 WCF 필요 Ws-secure Conversation을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="d832b-184">R2302:AWS-Ws-reliable Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="d832b-185">R2303: WS-Reliable Messaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="d832b-186">B2304:WS-신뢰할 수 있는 메시징 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="d832b-187">WCF 소스 생성는 `wsse:SecurityTokenReference` 의 요소 확장성 섹션에 있는 요소는 `CreateSequence` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="d832b-188">R2305:When Ws-secure Conversation으로 구성 된 `CreateSequence` 메시지에 포함 해야 합니다는 `wsse:SecurityTokenReference` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="d832b-189">WS-Reliable Messaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="d832b-189">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="d832b-190">Ws-reliable Messaging Ws-policy Assertion을 사용 하 여 WCF `wsrm:RMAssertion` 에 끝점 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="d832b-191">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-191">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="d832b-192">B3001: WCF 연결 `wsrm:RMAssertion` Ws-policy Assertion에 `wsdl:binding` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="d832b-193">WCF에 첨부 파일이 모두 지원 `wsdl:binding` 및 `wsdl:port` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="d832b-194">B3002: WCF에서는 Ws-reliable Messaging 어설션의 다음과 같은 선택적 속성 및 WCF에에 대 한 제어를 제공`ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="d832b-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="d832b-195">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-195">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="d832b-196">흐름 제어 WS-Reliable Messaging 확장명</span><span class="sxs-lookup"><span data-stu-id="d832b-196">Flow Control WS-Reliable Messaging Extension</span></span>  
 <span data-ttu-id="d832b-197">WCF 확장성 Ws-reliable Messaging을 사용 하 여 시퀀스 메시지 흐름에 대 한 선택적 추가 더 엄격한 제어를 제공.</span><span class="sxs-lookup"><span data-stu-id="d832b-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="d832b-198">흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``bool` 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-198">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="d832b-199">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-199">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="d832b-200">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하도록 설정 하는 경우 WCF 생성 한 `netrm:BufferRemaining` 의 요소 확장성 요소는 `SequenceAcknowledgement` 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="d832b-201">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 WCF에서는 않아도 `netrm:BufferRemaining` 요소에 `SequenceAcknowledgement` 헤더를 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
-   <span data-ttu-id="d832b-202">B4003: WCF가 사용 하 여 `netrm:BufferRemaining` 를 나타내는 새 메시지 신뢰할 수 있는 메시징 대상이 버퍼링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="d832b-203">B4004: WCF 신뢰할 수 있는 메시징 서비스 신뢰할 수 있는 메시징 대상 응용 프로그램이 신속 하 게 메시지를 받을 수 있을 경우 전송할 메시지의 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="d832b-204">신뢰할 수 있는 메시징 대상은 메시지를 버퍼링하고 요소의 값을 0으로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="d832b-205">B4005: WCF 생성 `netrm:BufferRemaining` 정수 0과 4096 사이의 값 및 0 사이의 정수 값을 읽습니다 및 `xs:int`의 `maxInclusive` 값 214748364 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="d832b-206">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="d832b-206">Message Exchange Patterns</span></span>  
 <span data-ttu-id="d832b-207">다른 메시지 교환 패턴에 사용 되는 Ws-reliable Messaging이 섹션에서는 WCF의 동작을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="d832b-208">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="d832b-209">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="d832b-210">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="d832b-211">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="d832b-211">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="d832b-212">바인딩</span><span class="sxs-lookup"><span data-stu-id="d832b-212">Binding</span></span>  
 <span data-ttu-id="d832b-213">WCF는 HTTP 채널을 통해 한 개의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="d832b-214">WCF는 HTTP 요청을 사용 하 여 RMS RMD의 모든 메시지를 HTTP 응답에는 RMS에서 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="d832b-215">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-215">CreateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-216">에서는 발생 하는 WCF 초기자는 `CreateSequence` 제공 하지 않는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="d832b-217">WCF 응답자는 `CreateSequence` 에서 시퀀스를 만들기 전에 없습니다 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="d832b-218">에 회신 하는 WCF 응답자는 `CreateSequence` 로 요청을 `CreateSequenceResponse` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="d832b-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="d832b-219">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="d832b-220">WCF 초기자를 제외한 모든 메시지의 회신에 대 한 승인을 처리는 `CreateSequence` 메시지와 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="d832b-221">WCF 응답자는 항상 독립 실행형 승인을 모두 시퀀스에 대 한 응답에서 생성 및 `AckRequested` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="d832b-222">TerminateSequence 메시지</span><span class="sxs-lookup"><span data-stu-id="d832b-222">TerminateSequence message</span></span>  
 <span data-ttu-id="d832b-223">WCF는 처리 `TerminateSequence` 단방향 작업으로는 빈 본문과 HTTP 202 상태 코드가 HTTP 응답을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="d832b-224">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="d832b-224">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="d832b-225">바인딩</span><span class="sxs-lookup"><span data-stu-id="d832b-225">Binding</span></span>  
 <span data-ttu-id="d832b-226">WCF에는 한 개의 시퀀스를 통해 인바운드 및 아웃 바운드 Http 채널을 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="d832b-227">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d832b-228">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="d832b-229">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-229">CreateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-230">에서는 발생 하는 WCF 초기자는 `CreateSequence` 제공 하지 않는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="d832b-231">WCF 응답자는 `CreateSequence` 에서 시퀀스를 만들기 전에 없습니다 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="d832b-232">WCF 응답자 전송는 `CreateSequenceResponse` 는 HTTP 요청에 대 한 메시지를 통해 처리할 수는 `ReplyTo` 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="d832b-233">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="d832b-233">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="d832b-234">바인딩</span><span class="sxs-lookup"><span data-stu-id="d832b-234">Binding</span></span>  
 <span data-ttu-id="d832b-235">WCF는 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="d832b-236">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d832b-237">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="d832b-238">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-238">CreateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-239">에서는 발생 하는 WCF 초기자는 `CreateSequence` 특정 오퍼와 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="d832b-240">WCF 보안 응답자는 `CreateSequence` 에서 시퀀스를 만들기 전에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="d832b-241">WCF 전송의 `CreateSequenceResponse` 로 주소가 지정 된 HTTP 요청에는 `CreateSequence`의 `ReplyTo` 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="d832b-242">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="d832b-242">Sequence Lifetime</span></span>  
 <span data-ttu-id="d832b-243">WCF 개의 전체 이중 세션으로 두 시퀀스를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-243">WCF treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="d832b-244">한 개의 시퀀스를 오류 처리 하는 오류를 생성 하면 WCF는 원격 끝점이 두 시퀀스를 오류를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="d832b-245">한 개의 시퀀스를 오류 처리 하는 오류를 읽을 때 WCF에는 두 시퀀스 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="d832b-246">WCF 해당 아웃 바운드 시퀀스 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="d832b-247">반대로, WCF에서는 인바운드 시퀀스를 닫고을 계속 해 서 해당 아웃 바운드 시퀀스에서 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="d832b-248">요청-회신, 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="d832b-248">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="d832b-249">바인딩</span><span class="sxs-lookup"><span data-stu-id="d832b-249">Binding</span></span>  
 <span data-ttu-id="d832b-250">HTTP 채널을 통해을 시퀀스 하는 두 개를 사용 하 여 요청-회신 메시지 교환 패턴 및 WCF 단방향 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="d832b-251">WCF는 HTTP 요청을 사용 하 여 요청 시퀀스 메시지를 전송 하 고 회신 시퀀스의 메시지를 전송 하는 HTTP 응답을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="d832b-252">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-252">CreateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-253">에서는 발생 하는 WCF 초기자는 `CreateSequence` 특정 오퍼와 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="d832b-254">WCF 보안 응답자는 `CreateSequence` 에서 시퀀스를 만들기 전에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="d832b-255">에 회신 하는 WCF 응답자는 `CreateSequence` 로 요청을 `CreateSequenceResponse` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="d832b-256">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="d832b-256">One-way Message</span></span>  
 <span data-ttu-id="d832b-257">단방향 메시지 교환 프로토콜을 성공적으로 완료 하려면 WCF 초기자 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 독립 실행형 수신 `SequenceAcknowledgement` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="d832b-258">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="d832b-259">WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="d832b-260">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="d832b-260">Two Way Messages</span></span>  
 <span data-ttu-id="d832b-261">양방향 메시지 교환 프로토콜을 성공적으로 완료 하려면 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="d832b-262">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="d832b-263">WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="d832b-264">단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="d832b-265">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="d832b-265">Retrying Replies</span></span>  
 <span data-ttu-id="d832b-266">WCF는 HTTP 요청-회신 상관 관계는 양방향 메시지 교환 프로토콜 상관 관계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="d832b-267">이 때문에 WCF 초기자를 중지 하지 않습니다 요청 시퀀스 메시지가 승인 되 하지만 HTTP 응답은 승인, 사용자 메시지 또는 오류를 전달 하는 경우에 않고 요청 시퀀스 메시지 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="d832b-268">WCF 응답자는 회신 상관 된 요청의 HTTP 요청 레그에서 회신을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="d832b-269">LastMessage 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-269">LastMessage Exchange</span></span>  
 <span data-ttu-id="d832b-270">WCF 초기자는 생성 하 고 HTTP 요청 레그에서 본문이 빈 마지막 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="d832b-271">WCF는 응답이 필요 하지만 실제 응답 메시지를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="d832b-272">요청 시퀀스의 본문이 비어 있는 마지막 메시지에 회신 시퀀스의 본문이 비어 있는 마지막 메시지와 함께 WCF 응답자 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="d832b-273">WCF 응답자는는 동작 URI가 아닌 마지막 메시지를 받으면 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, 마지막 메시지를 WCF 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-273">If the WCF Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, WCF replies with a last message.</span></span> <span data-ttu-id="d832b-274">양방향 메시지 교환 프로토콜의 경우 마지막 메시지에 응용 프로그램 메시지가 포함되어 있으며, 단방향 메시지 교환 프로토콜의 경우 마지막 메시지는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="d832b-275">WCF 응답자는 회신 시퀀스의 본문이 비어 있는 마지막 메시지에 대 한 승인이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="d832b-276">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-276">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-277">WCF 초기자 생성 하 고이 전송 요청 시퀀스의 모든 요청이 유효한 회신을 받은 경우 `TerminateSequence` HTTP 요청 레그에서 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="d832b-278">WCF는 응답이 필요 하지만 실제 응답 메시지를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="d832b-279">요청 시퀀스에 회신 하는 WCF 응답자 `TerminateSequence` 회신 시퀀스의 메시지 `TerminateSequence` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="d832b-280">정상적인 종료 시퀀스에서 두 `TerminateSequence` 메시지 모두에 전체 범위의 `SequenceAcknowledgement`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="d832b-281">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="d832b-281">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="d832b-282">바인딩</span><span class="sxs-lookup"><span data-stu-id="d832b-282">Binding</span></span>  
 <span data-ttu-id="d832b-283">WCF에는 두 시퀀스를 통해 인바운드 및 아웃 바운드 HTTP 채널을 사용 하 여 요청-회신 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="d832b-284">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d832b-285">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="d832b-286">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="d832b-286">CreateSequence Exchange</span></span>  
 <span data-ttu-id="d832b-287">에서는 발생 하는 WCF 초기자는 `CreateSequence` 특정 오퍼와 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="d832b-288">WCF 보안 응답자는 `CreateSequence` 에서 시퀀스를 만들기 전에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="d832b-289">WCF 전송의 `CreateSequenceResponse` 로 주소가 지정 된 HTTP 요청에는 `CreateSequence`의 `ReplyTo` 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="d832b-290">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="d832b-290">Request/Reply Correlation</span></span>  
 <span data-ttu-id="d832b-291">WCF 초기자 하면 모든 응용 프로그램 요청 메시지 약은 `MessageId` 및 `ReplyTo` 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="d832b-292">WCF 초기자 적용 되는 `CreateSequence` 메시지의 `ReplyTo` 각 응용 프로그램 요청 메시지에서 끝점 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="d832b-293">WCF 응답자 필요는 들어오는 요청 메시지는 `MessageId` 및 `ReplyTo`합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="d832b-294">WCF 응답자 되도록 둘 다의 끝점 참조의 URI는 `CreateSequence` 하 고 모든 응용 프로그램 요청 메시지 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d832b-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
