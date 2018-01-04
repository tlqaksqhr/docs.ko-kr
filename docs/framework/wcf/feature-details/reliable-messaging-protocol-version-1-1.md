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
ms.workload: dotnet
ms.openlocfilehash: 67df8b539109d7e4dafcbc42ad7679643767021a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-11"></a>Reliable Messaging 프로토콜 버전 1.1
이 항목에서는 HTTP 전송을 사용하여 상호 운용에 필요한 WS-ReliableMessaging February 2007(버전 1.1) 프로토콜의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구현 정보에 대해 설명합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 이 항목에서 설명한 제약 조건 및 확인된 내용과 함께 WS-ReliableMessaging 사양을 따릅니다. 부터는 Ws-reliablemessaging 1.1 프로토콜을 구현 하는 참고는 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]합니다.  
  
 WS-ReliableMessaging February 2007 프로토콜은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현됩니다.  
  
 편의상 이 항목에서는 다음 역할을 사용합니다.  
  
-   개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.  
  
-   응답자: 개시자의 요청을 받는 서비스입니다.  
  
 이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.  
  
|접두사|네임스페이스|  
|-|-|  
|wsrm|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|wsrmp|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|netrmp|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|wsp|(WS-Policy 1.2 또는 WS-Policy 1.5)|  
  
## <a name="messaging"></a>메시징  
  
### <a name="sequence-creation"></a>시퀀스 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현하여 신뢰할 수 있는 메시징 시퀀스를 설정합니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   B1101: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지의 `ReplyTo`, `AcksTo` 및 `Offer/Endpoint`와 동일한 끝점 참조를 사용합니다.  
  
-   R1102: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하도록 동일한 문자열 표현을 포함하는 주소 값이 있어야 합니다.  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `AcksTo`, `ReplyTo` 및 `Endpoint` 끝점 참조의 URI 부분이 동일한지 확인합니다.  
  
-   R1103: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `AcksTo`에 대한 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 끝점 참조의 참조 매개 변수를 동일한 것으로 지정하지 않지만 동일하다고 가정하며, 승인 및 역방향 시퀀스 메시지에 `ReplyTo` 끝점 참조의 참조 매개 변수를 사용합니다.  
  
-   B1104: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `Expires` 메시지에 선택적 `Offer/Expires` 또는 `CreateSequence` 요소를 생성하지 않습니다.  
  
-   B1105: `CreateSequence` 메시지에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `Expires` 요소의 `CreateSequence` 값을 `Expires` 요소의 `CreateSequenceResponse` 값으로 사용합니다. 그렇지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `Expires` 및 `Offer/Expires` 값을 읽고 무시합니다.  
  
-   B1106: `CreateSequenceResponse` 메시지에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 선택적 `Expires` 값을 읽지만 사용하지는 않습니다.  
  
-   B1107: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자와 응답자는 항상 `IncompleteSequenceBehavior` 및 `CreateSequence/Offer` 요소에 선택적 `CreateSequenceResponse` 요소를 생성합니다.  
  
-   B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `DiscardFollowingFirstGap` 요소에 `NoDiscard` 및 `IncompleteSequenceBehavior` 값만 사용합니다.  
  
    -   WS-ReliableMessaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.  
  
-   B1109: `CreateSequence`에 `Offer` 요소가 포함된 경우 단방향 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceResponse` 요소를 사용하지 않고 `Accept`로 응답하여 제공된 시퀀스를 거부합니다.  
  
-   B1110: 신뢰할 수 있는 메시징 응답자가 제공된 시퀀스를 거부하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 새로 설정된 시퀀스를 오류 처리합니다.  
  
-   B1111: `CreateSequence`에 `Offer` 요소가 포함되지 않은 경우 양방향 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceRefused` 오류로 응답하여 제공된 시퀀스를 거부합니다.  
  
-   R1112: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]` 끝점 참조의 `CreateSequenceResponse/Accept/AcksTo` 속성은 `CreateSequence` 메시지 바이트별 대상 URI와 일치해야 합니다.  
  
-   R1113: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자에서 응답자로 이동하는 두 시퀀스의 모든 메시지를 같은 끝점 참조로 보내야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-ReliableMessaging을 사용하여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging 구현에서는 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공합니다. `Offer` 및 `CreateSequence`에서 WS-ReliableMessaging `CreateSequenceResponse` 메커니즘을 사용하면 상호 관련된 두 개의 역방향 시퀀스를 설정하고 모든 메시지 끝점에 적합한 세션 프로토콜을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 세션 무결성을 위한 종단 간 보호를 포함하여 세션에 대한 보안 보장을 제공하므로 같은 상대방에 보낼 메시지가 동일한 대상에 도달하는지 확인하는 것이 좋습니다. 이렇게 하면 응용 프로그램 메시지에서 "피기백킹"이라고 하는 시퀀스 승인을 사용할 수 있습니다. 따라서 R1102, R1112, 및 R1113 제약 조건에 적용 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]합니다.  
  
 `CreateSequence` 메시지의 예입니다.  
  
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
  
 `CreateSequenceResponse` 메시지의 예입니다.  
  
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
  
### <a name="closing-a-sequence"></a>시퀀스 닫기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 신뢰할 수 있는 메시징 소스에 의해 시작된 종료에 `CloseSequence` 및 `CloseSequenceResponse` 메시지를 사용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 종료를 시작하지 않고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에 의해 시작된 종료를 지원하지 않습니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   B1201: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 항상 `CloseSequence` 메시지를 보내어 시퀀스를 종료합니다.  
  
-   B1202: 신뢰할 수 있는 메시징 소스는 시퀀스 메시지 전체 범위의 승인을 기다린 다음 `CloseSequence` 메시지를 보냅니다.  
  
-   B1203: 시퀀스에 메시지가 있으면 신뢰할 수 있는 메시징 소스에는 항상 선택적 `LastMsgNumber` 요소가 포함됩니다.  
  
-   R1204: 신뢰할 수 있는 메시징 대상은 `CloseSequence` 메시지를 보내어 종료를 시작하면 안 됩니다.  
  
-   B1205: `CloseSequence` 메시지를 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 소스는 시퀀스가 완료되지 않았다고 간주하고 오류를 보냅니다.  
  
 `CloseSequence` 메시지의 예입니다.  
  
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
  
### <a name="sequence-termination"></a>시퀀스 종료  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `TerminateSequence/TerminateSequenceResponse` 핸드셰이크를 완료한 후 주로 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 사용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 종료를 시작하지 않고 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상에 의해 시작된 종료를 지원하지 않습니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   B1301: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `TerminateSequence` 핸드셰이크가 완료된 후 `CloseSequence/CloseSequenceResponse` 메시지만 보냅니다.  
  
-   R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `LastMsgNumber` 요소가 제공된 시퀀스의 모든 `CloseSequence` 및 `TerminateSequence` 메시지에서 일치하는지 확인합니다. 즉, `LastMsgNumber`가 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 없거나, 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 있으며 이러한 메시지에서 동일합니다.  
  
-   B1303: `TerminateSequence` 핸드셰이크 이후 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다. 신뢰할 수 있는 메시징 소스에 `TerminateSequence` 메시지를 보내기 전의 최종 승인이 있으므로 신뢰할 수 있는 메시징 대상은 시퀀스가 종료되고 리소스를 즉시 회수함을 인식하고 있습니다.  
  
-   B1304: `TerminateSequence` 핸드셰이크 이전에 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다. 신뢰할 수 있는 메시징 대상이 시퀀스에서 일치하지 않는 부분이 없음을 확인한 경우에는 클라이언트가 최종 승인을 받을 수 있도록 신뢰할 수 있는 메시징 대상이 응용 프로그램 대상에서 지정한 시간 동안 기다린 다음 리소스를 회수합니다. 그렇지 않은 경우 신뢰할 수 있는 메시징 대상이 리소스를 바로 회수하고 응용 프로그램 대상에 `Faulted` 이벤트를 발생시켜 시퀀스에 오류가 발생하여 종료되었음을 알려 줍니다.  
  
 `TerminateSequence` 메시지의 예입니다.  
  
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
  
### <a name="sequences"></a>시퀀스  
 다음은 시퀀스에 적용되는 제약 조건의 목록입니다.  
  
-   B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 액세스 하는 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.  
  
 `Sequence` 헤더의 예입니다.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>승인 요청  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용합니다.  
  
 `AckRequested` 헤더의 예입니다.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging에 제공된 시퀀스 승인에 "피기백" 메커니즘을 사용합니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   R1601: 두 개의 역방향 시퀀스가 설정 된 경우 사용 하 여는 `Offer` 메커니즘은 `SequenceAcknowledgement` 응용 프로그램 받는 사람된에 게 전송 된 메시지에 헤더를 포함 될 수 있습니다. 원격 끝점에서는 피기백된 `SequenceAcknowledgement` 헤더에 액세스할 수 있어야 합니다.  
  
-   B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `SequenceAcknowledgement` 요소가 포함된 `Nack` 헤더를 생성하지 않습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각 `Nack` 요소에 시퀀스 번호가 포함되어 있는지 확인하지만, 그렇지 않은 경우에는 `Nack` 요소와 값을 무시합니다.  
  
 `SequenceAcknowledgement` 헤더의 예입니다.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging 오류  
 다음은 WS-ReliableMessaging 오류의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현에 적용되는 제약 조건 목록입니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하지 않습니다 `MessageNumberRollover` 오류입니다.  
  
-   B1702: SOAP 1.2를 통해 서비스 끝점이 해당 연결 제한에 도달하여 새 연결을 처리할 수 없는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제처럼 중첩된 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`를 생성합니다.  
  
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
  
### <a name="ws-addressing-faults"></a>WS-Addressing 오류  
 WS-ReliableMessaging에서는 WS-Addressing을 사용하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-ReliableMessaging을 구현하는 경우에는 WS-Addressing 오류를 생성하고 전송할 수 있습니다. 이 단원에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 WS-ReliableMessaging 계층에서 명시적으로 생성하고 전송하는 WS-Addressing 오류에 대해 설명합니다.  
  
-   B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 전송 된 `Message Addressing Header Required` 다음 중 하나에 오류:  
  
    -   `CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `MessageId` 헤더가 없습니다.  
  
    -   `CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.  
  
    -   `CreateSequenceResponse`, `CloseSequenceResponse` 또는 `TerminateSequenceResponse` 메시지에 `RelatesTo` 헤더가 없습니다.  
  
-   B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 전송 된 `Endpoint Unavailable` 있는 수신 대기 중인 끝점이 없습니다 나타내기 위해 오류 검사에서 주소 지정 헤더를 기준으로 시퀀스를 처리할 수는 `CreateSequence` 메시지입니다.  
  
## <a name="protocol-composition"></a>프로토콜 구성  
  
### <a name="composition-with-ws-addressing"></a>WS-Addressing을 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Addressing의 두 개 버전, WS-Addressing 2004/08 [WS-ADDR]과 W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] 및 [WS-ADDR-SOAP]를 지원합니다.  
  
 WS-ReliableMessaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   R2101: WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.  
  
-   R2102: 단일 버전의 WS-Addressing은 `Offer` 메커니즘을 사용하여 상호 관련된 한 쌍의 역방향 시퀀스 또는 제공된 WS-ReliableMessaging 시퀀스 전체에서 사용할 수 있어야 합니다.  
  
### <a name="composition-with-soap"></a>SOAP를 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging과 함께 SOAP 1.1 및 SOAP 1.2 모두 사용하는 것을 지원합니다.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>WS-Security 및 WS-SecureConversation을 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 보안 전송(HTTPS), WS-Security를 사용한 구성 및 WS-Secure Conversation을 사용한 구성을 통해 WS-ReliableMessaging 시퀀스를 보호합니다. WS-ReliableMessaging 1.1 프로토콜, WS-Security 1.1 및 WS-Secure Conversation 1.3 프로토콜을 함께 사용해야 합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   R2301: 개별 메시지의 무결성과 기밀성뿐만 아니라 WS-ReliableMessaging 시퀀스의 무결성을 보호하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-Secure Conversation을 사용해야 합니다.  
  
-   R2302:AWS-WS-RELIABLE Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.  
  
-   R2303: WS-ReliableMessaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.  
  
-   B2304:WS-ReliableMessaging 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.  
  
-   R2305: WS-Secure Conversation을 사용하여 구성된 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지에 `wsse:SecurityTokenReference` 요소와 `wsrm:UsesSequenceSTR` 헤더를 포함해야 합니다.  
  
 `UsesSequenceSTR` 헤더의 예입니다.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>SSL/TLS 세션을 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 SSL/TLS 세션을 사용한 구성을 지원하지 않습니다.  
  
-   B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrm:UsesSequenceSSL` 헤더를 생성하지 않습니다.  
  
-   R2402: 신뢰할 수 있는 메시징 개시자는 `CreateSequence` 응답자에게 `wsrm:UsesSequenceSSL` 헤더가 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 보내면 안 됩니다.  
  
### <a name="composition-with-ws-policy"></a>WS-Policy를 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Policy의 두 개 버전, WS-Policy 1.2와 WS-Policy 1.5를 지원합니다.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>WS-ReliableMessaging WS-Policy Assertion  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion`을 사용하여 끝점 기능을 설명합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrmn:RMAssertion` WS-Policy Assertion을 `wsdl:binding` 요소에 연결합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsdl:binding` 및 `wsdl:port` 요소에 대한 두 개 첨부 파일을 모두 지원합니다.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsp:Optional` 태그를 생성하지 않습니다.  
  
-   B3003: `wsrmp:RMAssertion` WS-Policy Assertion에 액세스할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsp:Optional` 태그를 무시하고 WS-RM 정책을 필수 항목으로 처리합니다.  
  
-   R3004: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 SSL/TLS 세션을 사용하여 구성되지 않으므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrmp:SequenceTransportSecurity`를 지정하는 정책을 허용하지 않습니다.  
  
-   B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 항상 `wsrmp:DeliveryAssurance` 요소를 생성합니다.  
  
-   B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 항상 `wsrmp:ExactlyOnce` 배달 보증을 지정합니다.  
  
-   B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 및 WS-RELIABLE Messaging 어설션의 다음과 같은 속성을 읽고,에서 제어를 제공는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableSessionBindingElement`:  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     `RMAssertion`의 예입니다.  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a>흐름 제어 WS-ReliableMessaging 확장  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-ReliableMessaging 확장성을 사용하여 선택적으로 시퀀스 메시지 흐름을 보다 엄격하게 제어합니다.  
  
 흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``boolean` 속성을 `true`합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `netrm:BufferRemaining` 헤더의 요소 확장성에 `SequenceAcknowledgement` 요소를 생성합니다.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용하는 경우에도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `netrm:BufferRemaining` 헤더에 `SequenceAcknowledgement` 요소가 필요하지 않습니다.  
  
-   B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 대상은 `netrm:BufferRemaining`을 사용하여 버퍼링할 수 있는 새 메시지 수를 나타냅니다.  
  
-   B4004:When 신뢰할 수 있는 메시징 흐름 제어를 사용 하도록 설정 된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 의 값을 사용 하는 신뢰할 수 있는 메시징 소스 `netrm:BufferRemaining` 스로틀 메시지 전송에 있습니다.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 0과 4096 사이의 `netrm:BufferRemaining` 정수 값을 생성하고 0과 `xs:int`의 `maxInclusive` 값 214748364 사이의 정수 값을 읽습니다.  
  
## <a name="message-exchange-patterns"></a>메시지 교환 패턴  
 이 단원에서는 WS-ReliableMessaging이 다른 메시지 교환 패턴에 사용되는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동작을 설명합니다. 각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.  
  
-   주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.  
  
-   주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.  
  
### <a name="one-way-non-addressable-initiator"></a>주소를 지정할 수 없는 단방향 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 개시자의 모든 메시지를 응답자에게 전송하고 HTTP 응답을 사용하여 응답자의 모든 메시지를 개시자에게 전송합니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 없는 `Offer` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 응답에 `CreateSequenceResponse` 요소가 없는 `Accept` 메시지를 전송합니다.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지와 오류 메시지를 제외한 모든 메시지의 회신에 대한 승인을 처리합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 항상 HTTP 응답에 대한 독립 실행형 승인을 모든 시퀀스 및 `AckRequested` 메시지에 전송합니다.  
  
#### <a name="closesequence-exchange"></a>CloseSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CloseSequence` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `CloseSequenceResponse` 메시지를 전송합니다.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `TerminateSequence` 메시지를 전송하고 HTTP 응답에 `TerminateSequenceResponse` 메시지를 예상합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `TerminateSequenceResponse` 메시지를 전송합니다.  
  
### <a name="one-way-addressable-initiator"></a>주소를 지정할 수 있는 단방향 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 없는 `Offer` 메시지를 전송합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 요청에 `CreateSequenceResponse` 요소가 없는 `Accept` 메시지를 전송합니다.  
  
### <a name="duplex-addressable-initiator"></a>주소를 지정할 수 있는 이중 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공합니다. 이 메시지 교환 패턴은 제한된 방식으로 `Request/Reply`, `Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인한 다음 시퀀스를 만들고 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 전송합니다.  
  
#### <a name="sequence-lifetime"></a>시퀀스 수명  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 개의 시퀀스를 한 개의 전체 이중 세션으로 처리합니다.  
  
 한 개의 시퀀스를 오류 처리하는 오류를 생성하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 원격 끝점이 두 시퀀스를 오류 처리한다고 예상합니다. 한 개의 시퀀스를 오류 처리하는 오류를 읽으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 시퀀스를 오류 처리합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 해당 아웃바운드 시퀀스를 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다. 반대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인바운드 시퀀스를 닫고 해당 아웃바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>요청-회신 및 단방향의 주소를 지정할 수 없는 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 단방향 및 요청-회신 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 개시자의 모든 메시지를 응답자에게 전송하고 HTTP 응답을 사용하여 응답자의 모든 메시지를 개시자에게 전송합니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송하고 HTTP 응답에 `CreateSequenceResponse` 메시지를 예상합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들고 HTTP 응답에 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 예상합니다.  
  
#### <a name="one-way-message"></a>단방향 메시지  
 단방향 메시지 교환을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 요청 시퀀스 메시지를 전송하고 HTTP 응답에 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다. `SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.  
  
#### <a name="two-way-messages"></a>양방향 메시지  
 양방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 회신 시퀀스 메시지를 받습니다. 응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.  
  
 단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.  
  
#### <a name="retrying-replies"></a>회신 다시 시도  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 양방향 메시지 교환 프로토콜 상관 관계에 HTTP 요청-회신 상관 관계를 사용합니다. 따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 응답에 `SequenceAcknowledgement`, 응용 프로그램 회신 또는 오류가 포함되지 않고 요청 시퀀스 메시지가 승인되는 경우 요청 시퀀스 메시지 다시 시도를 중지하지 않습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신이 상호 관련된 요청의 HTTP 응답에 회신을 다시 시도합니다.  
  
#### <a name="closesequence-exchange"></a>CloseSequence 교환  
 모든 단방향 요청 시퀀스 메시지에 대한 모든 회신 시퀀스 메시지와 승인을 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에서 요청 시퀀스에 대한 `CloseSequence` 메시지를 전송하고 HTTP 응답에 `CloseSequenceResponse`를 예상합니다.  
  
 요청 시퀀스를 닫으면 회신 시퀀스가 암시적으로 닫힙니다. 즉, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자에 `SequenceAcknowledgement` 메시지에 대한 회신 시퀀스의 최종 `CloseSequence`가 포함되고 회신 시퀀스에 `CloseSequence` 교환이 포함되지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 모든 회신에 승인했는지 확인하고 HTTP 응답에 `CloseSequenceResponse` 메시지를 전송합니다.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환  
 `CloseSequenceResponse` 메시지를 받으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에서 요청 시퀀스에 대한 `TerminateSequence` 메시지를 전송하고 HTTP 응답에 `TerminateSequenceResponse`를 예상합니다.  
  
 `CloseSequence` 교환과 마찬가지로 요청 시퀀스를 종료하면 회신 시퀀스가 암시적으로 종료됩니다. 즉, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자에 `SequenceAcknowledgement` 메시지에 대한 회신 시퀀스의 최종 `TerminateSequence`가 포함되고 회신 시퀀스에 `TerminateSequence` 교환이 포함되지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 HTTP 응답에 `TerminateSequenceResponse` 메시지를 전송합니다.  
  
### <a name="requestreply-addressable-initiator"></a>요청/회신, 주소를 지정할 수 있는 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 요청-회신 메시지 교환 패턴을 제공합니다. 이 메시지 교환 패턴은 제한된 방식으로 `Duplex, Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청에 `CreateSequence` 요소가 있는 `Offer` 메시지를 전송합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인한 다음 시퀀스를 만들고 `CreateSequenceResponse` 요소가 있는 `Accept` 메시지를 전송합니다.  
  
#### <a name="requestreply-correlation"></a>요청/회신 상관 관계  
 다음 사항은 모든 상호 관련된 요청 및 회신에 적용됩니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 응용 프로그램 요청 메시지에 `ReplyTo` 끝점 참조 및 `MessageId`가 있는지 확인합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 로컬 끝점 참조를 각 응용 프로그램 요청 메시지의 `ReplyTo`로 적용합니다. 로컬 끝점 참조는 개시자에 대한 `CreateSequence` 메시지의 `ReplyTo`와 응답자에 대한 `CreateSequence` 메시지의 `To`입니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 들어오는 요청 메시지에 `MessageId` 및 `ReplyTo`가 있는지 확인합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 응용 프로그램 요청 메시지의 `ReplyTo` 끝점 참조 URI가 앞에서 정의된 대로 로컬 끝점 참조와 일치하는지 확인합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 회신에 올바른 `RelatesTo` 및 `To` 헤더와 `wsa` 요청/회신 상관 관계 규칙이 차례로 있는지 확인합니다.
