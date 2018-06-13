---
title: Reliable Messaging 프로토콜 버전 1.1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496960"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="2537a-102">Reliable Messaging 프로토콜 버전 1.1</span><span class="sxs-lookup"><span data-stu-id="2537a-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="2537a-103">이 항목에서는 WS-RELIABLE Messaging에 대 한 Windows Communication Foundation (WCF) 구현 세부 정보를 다룹니다 HTTP 전송을 사용 하 여 상호 운용에 필요한 2007 년 2 월 (버전 1.1) 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="2537a-104">WCF에는 제약 조건 및 확인 된이 항목에 설명 된 내용과 함께 WS-RELIABLE Messaging 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="2537a-105">부터는 Ws-reliablemessaging 1.1 프로토콜을 구현 하는 참고는 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="2537a-106">WS-RELIABLE Messaging 2007 년 2 월 프로토콜에서 WCF에서 구현 되는 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="2537a-107">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="2537a-108">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="2537a-109">응답자: 개시자의 요청을 받는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="2537a-110">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="2537a-111">접두사</span><span class="sxs-lookup"><span data-stu-id="2537a-111">Prefix</span></span>|<span data-ttu-id="2537a-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2537a-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="2537a-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="2537a-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="2537a-114">netrm</span><span class="sxs-lookup"><span data-stu-id="2537a-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="2537a-115">s</span><span class="sxs-lookup"><span data-stu-id="2537a-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="2537a-116">wsa</span><span class="sxs-lookup"><span data-stu-id="2537a-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="2537a-117">wsse</span><span class="sxs-lookup"><span data-stu-id="2537a-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="2537a-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="2537a-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="2537a-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="2537a-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="2537a-120">wsp</span><span class="sxs-lookup"><span data-stu-id="2537a-120">wsp</span></span>|<span data-ttu-id="2537a-121">(WS-Policy 1.2 또는 WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="2537a-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="2537a-122">메시징</span><span class="sxs-lookup"><span data-stu-id="2537a-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="2537a-123">시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="2537a-123">Sequence Creation</span></span>  
 <span data-ttu-id="2537a-124">WCF 구현 `CreateSequence` 및 `CreateSequenceResponse` 신뢰할 수 있는 메시징 설정 하는 메시지 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="2537a-125">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2537a-126">B1101: WCF 초기자와 동일한 끝점 참조를 사용 하 여 `CreateSequence` 메시지의 `ReplyTo`, `AcksTo` 및 `Offer/Endpoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="2537a-127">R1102: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하도록 동일한 문자열 표현을 포함하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="2537a-128">WCF 응답자 확인의 URI 부분이 `AcksTo`, `ReplyTo` 및 `Endpoint` 시퀀스를 만들기 전에 끝점 참조는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="2537a-129">R1103: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="2537a-130">WCF를 지정 하지 않지만 참조 하는 것으로 가정의 매개 변수는 `AcksTo`, `ReplyTo` 및 `Offer/Endpoint` 끝점 참조 `CreateSequence` 동일 하며에서 참조 매개 변수를 사용 하 여는 `ReplyTo` 에 대 한 끝점 참조 승인 및 역방향 시퀀스 메시지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="2537a-131">B1104: WCF 초기자를 생성 하지 않습니다 선택적 `Expires` 또는 `Offer/Expires` 요소에는 `CreateSequence` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="2537a-132">B1105:에 액세스할 때는 `CreateSequence` 사용 하 여 메시지를 WCF 응답자는 `Expires` 값는 `CreateSequence` 요소도는 `Expires` 값는 `CreateSequenceResponse` 요소.</span><span class="sxs-lookup"><span data-stu-id="2537a-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="2537a-133">WCF 응답자 읽고 무시 그렇지 않은 경우는 `Expires` 및 `Offer/Expires` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="2537a-134">B1106:에 액세스할 때의 `CreateSequenceResponse` 선택적 읽고 메시지를 WCF 초기자 `Expires` 값 하지만 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="2537a-135">B1107: WCF 개시자와 응답자 항상 생성 선택적 `IncompleteSequenceBehavior` 요소에는 `CreateSequence/Offer` 및 `CreateSequenceResponse` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="2537a-136">B1108: WCF에서는는 `DiscardFollowingFirstGap` 및 `NoDiscard` 값에 `IncompleteSequenceBehavior` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="2537a-137">WS-ReliableMessaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="2537a-138">B1109: 경우 `CreateSequence` 포함 한 `Offer` 요소는 한 가지 방법은 WCF 응답 자가 제공 된 시퀀스로 응답 하 여 거부는 `CreateSequenceResponse` 없이 `Accept` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="2537a-139">B1110: 신뢰할 수 있는 메시징 응답자가 제공 된 시퀀스를 거부 하는 경우 WCF 초기자 새로 설정된 된 시퀀스를 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="2537a-140">B1111: 경우 `CreateSequence` 없으면는 `Offer` 요소인 양방향 WCF 응답 자가 제공 된 시퀀스로 응답 하 여 거부는 `CreateSequenceRefused` 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="2537a-141">R1112: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]` 끝점 참조의 `CreateSequenceResponse/Accept/AcksTo` 속성은 `CreateSequence` 메시지 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="2537a-142">R1113: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자에서 응답자로 이동하는 두 시퀀스의 모든 메시지를 같은 끝점 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="2537a-143">WCF는 WS-RELIABLE Messaging을 사용 하 여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="2537a-144">WCF WS-RELIABLE Messaging 구현에서는 단방향, 요청-회신 및 전체에 대 한 신뢰할 수 있는 세션을 제공 이중 메시징 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="2537a-145">`Offer` 및 `CreateSequence`에서 WS-ReliableMessaging `CreateSequenceResponse` 메커니즘을 사용하면 상호 관련된 두 개의 역방향 시퀀스를 설정하고 모든 메시지 끝점에 적합한 세션 프로토콜을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="2537a-146">WCF는 세션 무결성에 대 한 종단 간 보호를 포함 하는 세션에 대 한 보안 보장을 제공 하므로 하 여 동일한 파티를 대상으로 메시지가 동일한 대상에 도달할 수 있도록 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="2537a-147">이렇게 하면 응용 프로그램 메시지에서 "피기백킹"이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="2537a-148">따라서 제약 조건 R1102, R1112, 및 R1113 WCF에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="2537a-149">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="2537a-150">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="2537a-151">시퀀스 닫기</span><span class="sxs-lookup"><span data-stu-id="2537a-151">Closing a Sequence</span></span>  
 <span data-ttu-id="2537a-152">WCF를 사용 하는 `CloseSequence` 및 `CloseSequenceResponse` 신뢰할 수 있는 메시징 소스에서 시작 된 종료에 대 한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="2537a-153">WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않고 및 WCF 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에서 시작 된 종료를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="2537a-154">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2537a-155">B1201: WCF 신뢰할 수 있는 메시징 소스 항상 보냅니다는 `CloseSequence` 시퀀스를 종료 하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="2537a-156">B1202: 신뢰할 수 있는 메시징 소스는 시퀀스 메시지 전체 범위의 승인을 기다린 다음 `CloseSequence` 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="2537a-157">B1203: 시퀀스에 메시지가 있으면 신뢰할 수 있는 메시징 소스에는 항상 선택적 `LastMsgNumber` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="2537a-158">R1204: 신뢰할 수 있는 메시징 대상은 `CloseSequence` 메시지를 보내어 종료를 시작하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="2537a-159">: B1205 수신 된 `CloseSequence` 메시지를 WCF 신뢰할 수 있는 메시징 소스는 시퀀스를 불완전 한 것으로 간주 하 고 오류를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="2537a-160">`CloseSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="2537a-161">시퀀스 종료</span><span class="sxs-lookup"><span data-stu-id="2537a-161">Sequence Termination</span></span>  
 <span data-ttu-id="2537a-162">WCF에서 주로 사용 하는 `TerminateSequence/TerminateSequenceResponse` 핸드셰이크를 완료 한 후의 `CloseSequence/CloseSequenceResponse` 핸드셰이크 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="2537a-163">WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않고 및 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에서 시작 된 종료를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="2537a-164">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2537a-165">B1301: WCF 초기자만 보냅니다는 `TerminateSequence` 성공적으로 완료 한 후의 메시지는 `CloseSequence/CloseSequenceResponse` 핸드셰이크입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="2537a-166">R1302: WCF의 유효성을 검사 하는 `LastMsgNumber` 모든 요소는 일관 된 `CloseSequence` 및 `TerminateSequence` 지정 된 시퀀스에 대 한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="2537a-167">즉, `LastMsgNumber`가 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 없거나, 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 있으며 이러한 메시지에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="2537a-168">B1303: `TerminateSequence` 핸드셰이크 이후 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="2537a-169">신뢰할 수 있는 메시징 소스에 `TerminateSequence` 메시지를 보내기 전의 최종 승인이 있으므로 신뢰할 수 있는 메시징 대상은 시퀀스가 종료되고 리소스를 즉시 회수함을 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="2537a-170">B1304: 받을 때는 `TerminateSequence` 이전에 메시지는 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 사용 하 여 응답 WCF 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="2537a-171">신뢰할 수 있는 메시징 대상이 시퀀스에서 일치하지 않는 부분이 없음을 확인한 경우에는 클라이언트가 최종 승인을 받을 수 있도록 신뢰할 수 있는 메시징 대상이 응용 프로그램 대상에서 지정한 시간 동안 기다린 다음 리소스를 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="2537a-172">그렇지 않은 경우 신뢰할 수 있는 메시징 대상이 리소스를 바로 회수하고 응용 프로그램 대상에 `Faulted` 이벤트를 발생시켜 시퀀스에 오류가 발생하여 종료되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="2537a-173">`TerminateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="2537a-174">시퀀스</span><span class="sxs-lookup"><span data-stu-id="2537a-174">Sequences</span></span>  
 <span data-ttu-id="2537a-175">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="2537a-176">B1401:WCF 생성 하 고 액세스 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="2537a-177">`Sequence` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="2537a-178">승인 요청</span><span class="sxs-lookup"><span data-stu-id="2537a-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="2537a-179">WCF를 사용 하 여는 `AckRequested` 헤더를 연결 유지 메커니즘으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="2537a-180">`AckRequested` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="2537a-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2537a-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="2537a-182">WCF는 Ws-reliable Messaging에 제공 된 시퀀스 승인에 "피기백" 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="2537a-183">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2537a-184">R1601: 두 개의 역방향 시퀀스가 설정 된 경우 사용 하 여는 `Offer` 메커니즘은 `SequenceAcknowledgement` 응용 프로그램 받는 사람된에 게 전송 된 메시지에 헤더를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="2537a-185">원격 끝점에서는 피기백된 `SequenceAcknowledgement` 헤더에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="2537a-186">B1602: WCF 생성 하지 않습니다 `SequenceAcknowledgement` 들어 있는 헤더 `Nack` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="2537a-187">WCF는 각 유효성을 검사 `Nack` 요소 시퀀스 번호를 포함 하지만 그렇지 않은 경우 무시는 `Nack` 요소와 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="2537a-188">`SequenceAcknowledgement` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="2537a-189">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="2537a-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="2537a-190">다음은 WS-RELIABLE Messaging 오류의 WCF 구현에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="2537a-191">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2537a-192">B1701: WCF 생성 하지 않습니다 `MessageNumberRollover` 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="2537a-193">B1702: SOAP 1.2를 통해 서비스 끝점에서 연결 제한에 도달 하 고 새 연결을 처리할 수 없습니다. WCF에서는 오류가 발생 하는 중첩 된 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="2537a-194">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="2537a-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="2537a-195">WS-RELIABLE Messaging에서는 Ws-addressing 때문에 WCF WS-RELIABLE Messaging 구현은 생성 하 고 Ws-addressing 오류를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="2537a-196">이 섹션에서는 WCF에서 명시적으로 생성 하 고는 WS-RELIABLE Messaging 계층에 전송 하는 Ws-addressing 오류를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="2537a-197">B1801:WCF 생성 하 고 전송 된 `Message Addressing Header Required` 다음 중 하나에 오류:</span><span class="sxs-lookup"><span data-stu-id="2537a-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="2537a-198">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="2537a-199">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="2537a-200">`CreateSequenceResponse`, `CloseSequenceResponse` 또는 `TerminateSequenceResponse` 메시지에 `RelatesTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="2537a-201">B1802:WCF 생성 하 고 전송 된 `Endpoint Unavailable` 있는 수신 대기 중인 끝점이 없습니다 나타내기 위해 오류 검사에서 주소 지정 헤더를 기준으로 시퀀스를 처리할 수는 `CreateSequence` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="2537a-202">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="2537a-203">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="2537a-204">WCF는 Ws-addressing의 두 가지 버전을 지원: Ws-addressing 2004/08 [WS-ADDR] 및 W3C Ws-addressing 1.0 Recommendations [WS ADDR 코어] 및 [WS ADDR SOAP].</span><span class="sxs-lookup"><span data-stu-id="2537a-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="2537a-205">WS-ReliableMessaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="2537a-206">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2537a-207">R2101: WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="2537a-208">R2102: 단일 버전의 WS-Addressing은 `Offer` 메커니즘을 사용하여 상호 관련된 한 쌍의 역방향 시퀀스 또는 제공된 WS-ReliableMessaging 시퀀스 전체에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="2537a-209">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-209">Composition with SOAP</span></span>  
 <span data-ttu-id="2537a-210">WCF는 SOAP 1.1 및 SOAP 1.2 Ws-reliable Messaging과 함께 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="2537a-211">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="2537a-212">WCF 보안 전송 (HTTPS), Ws-security를 사용 하 여 구성 및 컴퍼지션 Ws-secure Conversation을 사용한 WS-RELIABLE Messaging 시퀀스에 대 한 보호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="2537a-213">WS-ReliableMessaging 1.1 프로토콜, WS-Security 1.1 및 WS-Secure Conversation 1.3 프로토콜을 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="2537a-214">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2537a-215">R2301: 개별 메시지의 무결성 뿐만 아니라 Ws-reliablemessaging 시퀀스의 무결성과 기밀성을 보호 하려면 WCF에 필요한 Ws-secure Conversation을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="2537a-216">R2302:AWS-WS-RELIABLE Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="2537a-217">R2303: WS-ReliableMessaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="2537a-218">B2304:WS-ReliableMessaging 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="2537a-219">R2305: Ws-secure Conversation, 작성 하는 경우 WCF 응답자를 사용 하려면는 `CreateSequence` 메시지에 포함 된 `wsse:SecurityTokenReference` 요소 및 `wsrm:UsesSequenceSTR` 헤더 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="2537a-220">`UsesSequenceSTR` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="2537a-221">SSL/TLS 세션을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="2537a-222">WCF는 SSL/TLS 세션을 사용 하 여 구성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="2537a-223">B2401: WCF 생성 하지 않습니다는 `wsrm:UsesSequenceSSL` 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="2537a-224">R2402: 신뢰할 수 있는 메시징 개시자 보내면 안는 `CreateSequence` 메시지는 `wsrm:UsesSequenceSSL` WCF 응답자에 대 한 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="2537a-225">WS-Policy를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="2537a-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="2537a-226">WCF는 Ws-policy의 두 가지 버전을 지원: Ws-policy 1.2와 Ws-policy 1.5입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="2537a-227">WS-ReliableMessaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="2537a-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="2537a-228">WS-RELIABLE Messaging Ws-policy Assertion을 사용 하 여 WCF `wsrm:RMAssertion` 에 끝점 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="2537a-229">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2537a-230">B3001: WCF 연결 `wsrmn:RMAssertion` Ws-policy Assertion에 `wsdl:binding` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="2537a-231">WCF에 첨부 파일이 모두 지원 `wsdl:binding` 및 `wsdl:port` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="2537a-232">B3002: WCF 생성 하지 않습니다는 `wsp:Optional` 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="2537a-233">B3003:에 액세스할 때의 `wsrmp:RMAssertion` Ws-policy Assertion WCF 무시는 `wsp:Optional` 태그를 지정 하 고 WS-RM 정책을 필수 항목으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="2537a-234">R3004: WCF SSL/TLS 세션을 갖는 작성 되지 않습니다, 때문에 WCF 받아들이지 않는 정책을 지정 하는 `wsrmp:SequenceTransportSecurity`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="2537a-235">B3005: WCF는 항상 생성는 `wsrmp:DeliveryAssurance` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="2537a-236">B3006: WCF 항상 지정 된 `wsrmp:ExactlyOnce` 배달 보증 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="2537a-237">B3007: WCF 생성 및 WS-RELIABLE Messaging 어설션의 다음과 같은 속성을 읽고 하 고 제공를 제어 WCF에서`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="2537a-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="2537a-238">`RMAssertion`의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="2537a-239">흐름 제어 WS-ReliableMessaging 확장명</span><span class="sxs-lookup"><span data-stu-id="2537a-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="2537a-240">WCF는 WS-RELIABLE Messaging 확장성을 사용 하 여 시퀀스 메시지 흐름을 보다 선택적 추가 더 엄격한 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="2537a-241">흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``boolean` 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-241">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="2537a-242">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2537a-243">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하도록 설정 하는 경우 WCF 생성 한 `netrm:BufferRemaining` 의 요소 확장성 요소는 `SequenceAcknowledgement` 헤더로, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="2537a-244">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하도록 설정 하는 경우에 WCF에서는 않아도 `netrm:BufferRemaining` 요소에는 `SequenceAcknowledgement` 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="2537a-245">B4003: WCF 신뢰할 수 있는 메시징 대상은 사용 하 여 `netrm:BufferRemaining` 새 메시지 것을 나타내기 위해 버퍼링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="2537a-246">B4004:When 신뢰할 수 있는 메시징 흐름 제어를 사용 하면 WCF 신뢰할 수 있는 메시징 소스에 값을 사용 하 여 `netrm:BufferRemaining` 스로틀 메시지 전송에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="2537a-247">B4005: WCF 생성 `netrm:BufferRemaining` 정수 0과 4096 사이의 값 및 0 사이의 정수 값을 읽습니다 및 `xs:int`의 `maxInclusive` 값 214748364 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="2537a-248">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="2537a-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="2537a-249">이 섹션에서는 WS-RELIABLE Messaging이 다른 메시지 교환 패턴에 사용 되는 경우 WCF의 동작을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="2537a-250">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="2537a-251">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="2537a-252">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="2537a-253">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="2537a-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2537a-254">바인딩</span><span class="sxs-lookup"><span data-stu-id="2537a-254">Binding</span></span>  
 <span data-ttu-id="2537a-255">WCF는 HTTP 채널을 통해 한 개의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="2537a-256">WCF는 HTTP 요청을 사용 하 여 시작자에 게 응답자의 모든 메시지를 응답자 및 HTTP 응답에는 시작자 로부터 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2537a-257">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-258">WCF 초기자 전송는 `CreateSequence` 없이 메시지 `Offer` 요소는 HTTP 요청에 것 이라고 예상는 `CreateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2537a-259">WCF 응답자는 시퀀스를 만들고 전송는 `CreateSequenceResponse` 메시지 없이 `Accept` HTTP 응답에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="2537a-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2537a-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="2537a-261">WCF 초기자를 제외한 모든 메시지의 회신에 대 한 승인을 처리는 `CreateSequence` 메시지와 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="2537a-262">WCF 응답자는 항상 독립 실행형 승인을 모든 시퀀스에 대 한 HTTP 응답에 전송 하 고 `AckRequested` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="2537a-263">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="2537a-264">WCF 초기자 전송는 `CloseSequence` 는 HTTP 요청에 메시지 보내기 및 예상는 `CreateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2537a-265">WCF 응답자 전송는 `CloseSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="2537a-266">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-267">WCF 초기자 전송는 `TerminateSequence` 는 HTTP 요청에 메시지 보내기 및 예상는 `TerminateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2537a-268">WCF 응답자 전송는 `TerminateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="2537a-269">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="2537a-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2537a-270">바인딩</span><span class="sxs-lookup"><span data-stu-id="2537a-270">Binding</span></span>  
 <span data-ttu-id="2537a-271">하나를 통해 한 개의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 하는 WCF 인바운드 및 아웃 바운드 HTTP 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2537a-272">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2537a-273">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2537a-274">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-275">WCF 초기자 전송는 `CreateSequence` 없이 메시지 `Offer` 는 HTTP 요청에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2537a-276">WCF 응답자는 시퀀스를 만들고 전송는 `CreateSequenceResponse` 메시지 없이 `Accept` 는 HTTP 요청에 대 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="2537a-277">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="2537a-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2537a-278">바인딩</span><span class="sxs-lookup"><span data-stu-id="2537a-278">Binding</span></span>  
 <span data-ttu-id="2537a-279">WCF에서 시퀀스를 두 개를 사용 하 여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공 인바운드 및 아웃 바운드 HTTP 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2537a-280">이 메시지 교환 패턴은 제한된 방식으로 `Request/Reply`, `Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="2537a-281">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2537a-282">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2537a-283">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-284">WCF 초기자 전송는 `CreateSequence` 메시지는 `Offer` 요소는 HTTP 요청에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2537a-285">WCF 응답자 되도록는 `CreateSequence` 에 `Offer` 요소를 다음 시퀀스를 만들고 전송는 `CreateSequenceResponse` 메시지는 `Accept` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="2537a-286">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="2537a-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="2537a-287">WCF는 개의 전체 이중 세션으로 두 시퀀스를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="2537a-288">한 개의 시퀀스를 오류 처리 하는 오류를 생성 하면 WCF는 원격 끝점이 두 시퀀스를 오류를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="2537a-289">한 개의 시퀀스를 오류 처리 하는 오류를 읽을 때 WCF에는 두 시퀀스 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="2537a-290">WCF 해당 아웃 바운드 시퀀스 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="2537a-291">반대로, WCF에서는 인바운드 시퀀스를 닫고을 계속 해 서 해당 아웃 바운드 시퀀스에서 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="2537a-292">요청-회신 및 단방향의 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="2537a-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2537a-293">바인딩</span><span class="sxs-lookup"><span data-stu-id="2537a-293">Binding</span></span>  
 <span data-ttu-id="2537a-294">HTTP 채널을 통해을 시퀀스 하는 두 개를 사용 하 여 요청-회신 메시지 교환 패턴 및 WCF 단방향 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="2537a-295">WCF는 HTTP 요청을 사용 하 여 시작자에 게 응답자의 모든 메시지를 응답자 및 HTTP 응답에는 시작자 로부터 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2537a-296">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-297">WCF 시작자에서 전송는 `CreateSequence` 메시지는 `Offer` 요소는 HTTP 요청에 것 이라고 예상는 `CreateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2537a-298">WCF 응답자는 시퀀스를 만들고 전송는 `CreateSequenceResponse` 메시지는 `Accept` HTTP 응답에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="2537a-299">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="2537a-299">One-way Message</span></span>  
 <span data-ttu-id="2537a-300">단방향 메시지 교환을 성공적으로 완료 하려면 WCF 초기자 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 독립 실행형 수신 `SequenceAcknowledgement` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="2537a-301">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="2537a-302">WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="2537a-303">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="2537a-303">Two Way Messages</span></span>  
 <span data-ttu-id="2537a-304">양방향 메시지 교환 프로토콜을 성공적으로 완료 하려면 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="2537a-305">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="2537a-306">WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="2537a-307">단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="2537a-308">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="2537a-308">Retrying Replies</span></span>  
 <span data-ttu-id="2537a-309">WCF는 HTTP 요청-회신 상관 관계는 양방향 메시지 교환 프로토콜 상관 관계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="2537a-310">이 때문에 WCF 초기자는 중단 되지 요청 시퀀스 메시지가 승인 되는 요청 시퀀스 메시지 다시 시도 그 대신 때 HTTP 응답의 경우 전달 된 `SequenceAcknowledgement`, 응용 프로그램 회신 또는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="2537a-311">WCF 응답자는 회신 상관 된 요청의 HTTP 응답에 회신을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="2537a-312">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="2537a-313">모든 회신 시퀀스 메시지와 모든 단방향 요청 시퀀스 메시지에 대 한 승인을 받으면 WCF 초기자 전송는 `CloseSequence` 는 HTTP 요청에 요청 시퀀스에 대 한 메시지 보내기 및 예상는 `CloseSequenceResponse` HTTP 응답에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="2537a-314">요청 시퀀스를 닫으면 회신 시퀀스가 암시적으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="2537a-315">즉, WCF 초기자 포함 회신 시퀀스의 최종 `SequenceAcknowledgement` 에 `CloseSequence` 메시지와 회신 시퀀스에 없는 `CloseSequence` exchange 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="2537a-316">WCF 응답자는 승인 했는지 확인 하 고 전송 하는 모든 회신의 `CloseSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="2537a-317">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-318">수신 후는 `CloseSequenceResponse` 메시지를 WCF 초기자 전송는 `TerminateSequence` 는 HTTP 요청에 요청 시퀀스에 대 한 메시지 보내기 및 예상는 `TerminateSequenceResponse` HTTP 응답에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="2537a-319">`CloseSequence` 교환과 마찬가지로 요청 시퀀스를 종료하면 회신 시퀀스가 암시적으로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="2537a-320">즉, WCF 초기자 포함 회신 시퀀스의 최종 `SequenceAcknowledgement` 에 `TerminateSequence` 메시지와 회신 시퀀스에 없는 `TerminateSequence` exchange 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="2537a-321">WCF 응답자 전송는 `TerminateSequenceResponse` HTTP 응답에는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="2537a-322">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="2537a-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2537a-323">바인딩</span><span class="sxs-lookup"><span data-stu-id="2537a-323">Binding</span></span>  
 <span data-ttu-id="2537a-324">WCF에서 시퀀스를 두 개를 사용 하 여 요청-회신 메시지 교환 패턴을 제공 인바운드 및 아웃 바운드 HTTP 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2537a-325">이 메시지 교환 패턴은 제한된 방식으로 `Duplex, Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="2537a-326">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2537a-327">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2537a-328">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="2537a-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2537a-329">WCF 초기자 전송는 `CreateSequence` 메시지는 `Offer` 요소는 HTTP 요청에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2537a-330">WCF 응답자는 `CreateSequence` 에 `Offer` 요소 다음 시퀀스를 만들고 전송는 `CreateSequenceResponse` 메시지는 `Accept` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="2537a-331">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="2537a-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="2537a-332">다음 사항은 모든 상호 관련된 요청 및 회신에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="2537a-333">WCF 하면 모든 응용 프로그램 요청 메시지 약은 `ReplyTo` 끝점 참조 및 `MessageId`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="2537a-334">각 응용 프로그램 요청 메시지와 로컬 끝점 참조를 적용 하는 WCF `ReplyTo`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="2537a-335">로컬 끝점 참조는 개시자에 대한 `CreateSequence` 메시지의 `ReplyTo`와 응답자에 대한 `CreateSequence` 메시지의 `To`입니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="2537a-336">WCF를 사용 하면 해당 들어오는 요청 메시지는 `MessageId` 및 `ReplyTo`합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="2537a-337">WCF를 사용 하면는 `ReplyTo` 앞에서 정의한 끝점 참조 URI 모든 응용 프로그램 요청 메시지의 로컬 끝점 참조와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="2537a-338">WCF를 사용 하면 모든 회신 해야 올바른 `RelatesTo` 및 `To` 헤더 `wsa` 요청/회신 상관 관계 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2537a-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
