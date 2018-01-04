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
# <a name="reliable-messaging-protocol-version-10"></a>Reliable Messaging 프로토콜 버전 1.0
이 항목에서는 HTTP 전송을 사용하여 상호 운용에 필요한 WS-ReliableMessaging February 2005(버전 1.0) 프로토콜의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구현 정보에 대해 설명합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 이 항목에서 설명한 제약 조건 및 확인된 내용과 함께 WS-Reliable Messaging 사양을 따릅니다. WS-ReliableMessaging 버전 1.0 프로토콜은 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 이상에서 구현됩니다.  
  
 WS-Reliable Messaging February 2005 프로토콜은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현되었습니다.  
  
 편의상 이 항목에서는 다음 역할을 사용합니다.  
  
-   개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.  
  
-   응답자: 개시자의 요청을 받은 서비스입니다.  
  
 이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.  
  
|접두사|네임스페이스|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>메시징  
  
### <a name="sequence-establishment-messages"></a>시퀀스 설정 메시지  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현하여 신뢰할 수 있는 메시지 시퀀스를 설정합니다. 적용되는 제약 조건은 다음과 같습니다.  
  
-   B1101: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 `CreateSequence` 메시지에서 선택적 Expires 요소를 생성하지 않거나 `CreateSequence` 메시지에 `Offer` 요소가 포함된 경우 `Expires` 요소에서 선택적 `Offer` 요소를 생성하지 않습니다.  
  
-   B1102:에 액세스할 때는 `CreateSequence` 메시지는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `Responder` 둘 다 받을 `Expires` 존재 않지만 해당 값을 사용 하지 않는 경우 요소입니다.  
  
 WS-Reliable Messaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.  
  
-   R1103: `CreateSequence`에 `Offer` 요소가 있는 경우 신뢰할 수 있는 메시징 응답자는 `CreateSequenceResponse` 요소가 포함된 `wsrm:Accept`와 함께 시퀀스 및 응답을 수락하여 상호 관련된 두 개의 역방향 시퀀스를 구성하거나 `CreateSequence` 요청을 거부해야 합니다.  
  
-   R1104: 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지는 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.  
  
-   R1105: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 8비트 형식과 일치하는 주소 값이 있어야 합니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `AcksTo` 및 `ReplyTo` EPR(끝점 참조)의 URI 부분이 동일한지 확인합니다.  
  
-   R1106: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 끝점 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `AcksTo`에 대한 `ReplyTo` 및 `CreateSequence`의 [참조 매개 변수]를 동일한 것으로 지정하지 않지만 동일하다고 가정하며, 승인 및 역방향 시퀀스 메시지에 `ReplyTo` 끝점 참조의 [참조 매개 변수]를 사용합니다.  
  
-   R1107: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 응용 프로그램 메시지를 `ReplyTo`의 `CreateSequence` 끝점 참조로 보내야 합니다.  
  
-   R1108: Offer 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]`의 `wsrm:AcksTo` 요소에 대한 `wsrm:Accept` 끝점 자식 요소의 `CreateSequenceResponse` 속성은 `CreateSequence`의 바이트별 대상 URI와 일치해야 합니다.  
  
-   R1109: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자가 보낸 메시지 및 응답자의 메시지 승인을 같은 끝점 참조로 보내야 합니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging을 사용하여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging 구현에서는 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공합니다. Ws-reliable Messaging `Offer` 메커니즘 `CreateSequence` / `CreateSequenceResponse` 두 상관 관계가 지정 된 역방향 시퀀스를 설정할 수 있습니다 하 고 모든 메시지 끝점에는 적합 한 세션 프로토콜을 제공 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 세션 무결성을 위한 종단 간 보호를 포함하여 세션에 대한 보안 보장을 제공하므로 같은 상대방에 보낼 메시지가 동일한 대상에 도달하는지 확인하는 것이 효율적입니다. 이렇게 하면 응용 프로그램 메시지에서 피기백킹이라고 하는 시퀀스 승인을 사용할 수 있습니다. 따라서 제약 조건 R1104, R1105, 및 R1108은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용됩니다.  
  
 `CreateSequence` 메시지의 예입니다.  
  
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
  
 `CreateSequenceResponse` 메시지의 예입니다.  
  
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
  
### <a name="sequence"></a>Sequence  
 다음은 시퀀스에 적용되는 제약 조건의 목록입니다.  
  
-   B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 생성 하 고 액세스 하는 시퀀스 번호 보다 높은 `xs:long`의 최대 포함 값 9223372036854775807 합니다.  
  
-   B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 항상 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage의 동작 URI와 본문이 비어 있는 마지막 메시지를 생성 합니다.  
  
-   B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 동작 URI가 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage가 아닌 한 `LastMessage` 요소가 포함된 시퀀스 헤더가 있는 메시지를 수신하고 배달합니다.  
  
 시퀀스 헤더의 예입니다.  
  
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
  
### <a name="ackrequested-header"></a>AckRequested 헤더  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 선택적 `MessageNumber` 요소를 생성하지 않습니다. `AckRequested` 요소가 포함된 `MessageNumber` 헤더가 있는 메시지를 수신하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `MessageNumber` 요소의 값을 무시합니다.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement 헤더  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging에 제공된 시퀀스 승인에 피기백 메커니즘을 사용합니다.  
  
-   R1401: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `SequenceAcknowledgement` 헤더가 받는 사람에게 전송된 응용 프로그램 메시지에 포함될 수 있습니다.  
  
-   B1402: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 시퀀스 메시지를 받기 전에 승인을 생성해야 하는 경우(예를 들어, `AckRequested` 메시지를 충족해야 하는 경우) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 0-0 범위가 포함된 `SequenceAcknowledgement` 헤더를 생성합니다.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `SequenceAcknowledgement` 요소가 포함된 `Nack` 헤더를 생성하지 않지만 `Nack` 요소를 지원합니다.  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging 오류  
 다음은 WS-Reliable Messaging 오류의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현에 적용되는 제약 조건 목록입니다.  
  
-   B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `MessageNumberRollover` 오류를 생성하지 않습니다.  
  
-   B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점이 생성 될 수 있습니다 `CreateSequenceRefused` 사양에 설명 된 대로 오류가 발생 합니다.  
  
-   B1503:When 서비스 끝점에서 연결 제한에 도달 하 고 새 연결을 처리할 수 없습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추가 생성 `CreateSequenceRefused` 오류 하위 코드, `netrm:ConnectionLimitReached`다음 예제에 나온 것 처럼 합니다.  
  
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
  
### <a name="ws-addressing-faults"></a>WS-Addressing 오류  
 WS-Reliable Messaging에서는 WS-Addressing을 사용하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 WS-Reliable Messaging을 구현하는 경우에는 WS-Addressing 오류를 생성할 수 있습니다. 이 단원에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 WS-Reliable Messaging 계층에 명시적으로 생성하는 WS-Addressing 오류에 대해 설명합니다.  
  
-   B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 다음 중 하나에 메시지 주소 지정 헤더가 필요 오류를 생성 합니다.  
  
    -   메시지에 `Sequence` 헤더 및 `Action` 헤더가 없습니다.  
  
    -   `CreateSequence` 메시지에 `MessageId` 헤더가 없습니다.  
  
    -   `CreateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.  
  
-   B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 누락 된 메시지에 대 한 응답이 아닌 지원 되지 않는 기능 오류를 생성 한 `Sequence` 헤더에는 `Action` Ws-reliable Messaging 사양에 인식 된 헤더입니다.  
  
-   B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점에서 사용할 수 없는 끝점의 검사를 기준으로 시퀀스를 처리 하지 않습니다 나타내는 오류를 생성 된 `CreateSequence` 메시지 주소 지정 헤더입니다.  
  
## <a name="protocol-composition"></a>프로토콜 구성  
  
### <a name="composition-with-ws-addressing"></a>WS-Addressing을 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Addressing의 두 개 버전, WS-Addressing 2004/08 [WS-ADDR]과 W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] 및 [WS-ADDR-SOAP]를 지원합니다.  
  
 WS-Reliable Messaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   R2101: 두 Ws-addressing 2004/08 및 Ws-addressing 1.0 Ws-reliable Messaging과 함께 사용할 수 있습니다.  
  
-   지정 된 Ws-reliable Messaging 시퀀스 또는 한 쌍의 역방향 시퀀스를 사용 하 여 상관 관계가 지정 된 전체에서 R2102:A 단일 버전의 Ws-addressing을 사용 해야 합니다는 `wsrm:Offer` 메커니즘입니다.  
  
### <a name="composition-with-soap"></a>SOAP를 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging과 함께 SOAP 1.1 및 SOAP 1.2를 모두 사용할 수 있도록 지원합니다.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>WS-Security 및 WS-SecureConversation을 사용하여 구성  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 보안 전송(HTTPS), WS-Security를 사용한 구성 및 WS-Secure Conversation을 사용한 구성을 통해 WS-Reliable Messaging 시퀀스를 보호합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   R2301: 개별 메시지의 무결성 뿐만 아니라 Ws-reliable Messaging 시퀀스의 무결성과 기밀성을 보호 하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Ws-secure Conversation을 사용 해야 합니다.  
  
-   R2302:AWS-Ws-reliable Messaging 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.  
  
-   R2303: WS-Reliable Messaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.  
  
-   B2304:WS-신뢰할 수 있는 메시징 시퀀스 또는 한 쌍의 상관 관계가 지정 된 역방향 시퀀스는 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소스는 `wsse:SecurityTokenReference` 메시지의 요소 확장성 섹션에 `CreateSequence` 요소를 생성합니다.  
  
-   R2305:When Ws-secure Conversation으로 구성 된 `CreateSequence` 메시지에 포함 해야 합니다는 `wsse:SecurityTokenReference` 요소입니다.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>WS-Reliable Messaging WS-Policy Assertion  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion`을 사용하여 끝점 기능을 설명합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsrm:RMAssertion` WS-Policy Assertion을 `wsdl:binding` 요소에 연결합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `wsdl:binding` 및 `wsdl:port` 요소에 대한 두 개 첨부 파일을 모두 지원합니다.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Ws-reliable Messaging 어설션의 다음과 같은 선택적 속성을 지원 하 고를 제어에 제공 된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     다음은 예제입니다.  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>흐름 제어 WS-Reliable Messaging 확장  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 WS-Reliable Messaging 확장성을 사용하여 선택적으로 시퀀스 메시지 흐름을 보다 엄격하게 제어합니다.  
  
 흐름 제어를 설정 하 여 활성화는 `ReliableSessionBindingElement`의 `FlowControlEnabled``bool` 속성을 `true`합니다. 다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 적용되는 제약 조건의 목록입니다.  
  
-   B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `netrm:BufferRemaining` 헤더의 요소 확장성에 `SequenceAcknowledgement` 요소를 생성합니다.  
  
-   B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 예제에서처럼 `netrm:BufferRemaining` 요소를 `SequenceAcknowledgement` 헤더에 제공할 필요가 없습니다.  
  
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
  
-   B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `netrm:BufferRemaining`을 사용하여 신뢰할 수 메시징 대상이 버퍼링할 수 있는 새 메시지 수를 나타냅니다.  
  
-   B4004:는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 서비스 신뢰할 수 있는 메시징 대상 응용 프로그램이 신속 하 게 메시지를 받을 수 있을 경우 전송할 메시지의 수를 제한 합니다. 신뢰할 수 있는 메시징 대상은 메시지를 버퍼링하고 요소의 값을 0으로 줄입니다.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 0과 4096 사이의 `netrm:BufferRemaining` 정수 값을 생성하고 0과 `xs:int`의 `maxInclusive` 값 214748364 사이의 정수 값을 읽습니다.  
  
## <a name="message-exchange-patterns"></a>메시지 교환 패턴  
 이 단원에서는 WS-Reliable Messaging이 다른 메시지 교환 패턴에 사용되는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동작을 설명합니다. 각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.  
  
-   주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.  
  
-   주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.  
  
### <a name="one-way-non-addressable-initiator"></a>주소를 지정할 수 없는 단방향 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 HTTP 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 RMS의 모든 메시지를 RMD에게 전송하고 HTTP 응답을 사용하여 RMD의 모든 메시지를 RMS에게 전송합니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하지 않는 `CreateSequence` 메시지를 생성합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 없는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지를 통해 `CreateSequenceResponse` 요청에 응답합니다.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 `CreateSequence` 메시지와 오류 메시지를 제외한 모든 메시지의 회신에 대한 승인을 처리합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 항상 시퀀스 및 `AckRequested` 메시지 모두에 대한 응답으로 독립 실행형 승인을 생성합니다.  
  
#### <a name="terminatesequence-message"></a>TerminateSequence 메시지  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `TerminateSequence`를 단방향 작업으로 처리합니다. 즉, HTTP 응답에는 비어 있는 본문과 HTTP 202 상태 코드가 있습니다.  
  
### <a name="one-way-addressable-initiator"></a>주소를 지정할 수 있는 단방향 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 Http 채널을 통해 한 개의 시퀀스를 사용하여 단방향 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하지 않는 `CreateSequence` 메시지를 생성합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 없는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequenceResponse` 끝점 참조를 사용하여 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.  
  
### <a name="duplex-addressable-initiator"></a>주소를 지정할 수 있는 이중 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 완전히 비동기적인 양방향 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `CreateSequenceResponse`의 `CreateSequence` 끝점 참조로 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.  
  
#### <a name="sequence-lifetime"></a>시퀀스 수명  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 개의 시퀀스를 한 개의 전체 이중 세션으로 처리합니다.  
  
 한 개의 시퀀스를 오류 처리하는 오류를 생성하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 원격 끝점이 두 시퀀스를 오류 처리한다고 예상합니다. 한 개의 시퀀스를 오류 처리하는 오류를 읽으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 두 시퀀스를 오류 처리합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 해당 아웃바운드 시퀀스를 닫고 해당 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다. 반대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 인바운드 시퀀스를 닫고 해당 아웃바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.  
  
### <a name="request-reply-non-addressable-initiator"></a>요청-회신, 주소를 지정할 수 없는 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 단방향 및 요청-회신 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 요청 시퀀스의 메시지를 전송하고 HTTP 응답을 사용하여 회신 시퀀스의 메시지를 전송합니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 메시지를 통해 `CreateSequenceResponse` 요청에 응답합니다.  
  
#### <a name="one-way-message"></a>단방향 메시지  
 단방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다. `SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.  
  
#### <a name="two-way-messages"></a>양방향 메시지  
 양방향 메시지 교환 프로토콜을 완료하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자가 HTTP 요청에 대한 요청 시퀀스 메시지를 전송하고 HTTP 응답에 대한 회신 시퀀스 메시지를 받습니다. 응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함된 응답으로 요청에 회신할 수 있습니다.  
  
 단방향 메시지가 있고 응용 프로그램이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.  
  
#### <a name="retrying-replies"></a>회신 다시 시도  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 양방향 메시지 교환 프로토콜 상관 관계에 HTTP 요청-회신 상관 관계를 사용합니다. 따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 응답에 승인, 사용자 메시지 또는 오류가 포함되지 않고 요청 시퀀스 메시지가 승인되는 경우 요청 시퀀스 메시지 다시 시도를 중지하지 않습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신과 상호 관련된 요청의 HTTP 요청 레그에서 회신을 다시 시도합니다.  
  
#### <a name="lastmessage-exchange"></a>LastMessage 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청 레그에서 본문이 비어 있는 마지막 메시지를 생성하여 전송합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 응답이 필요하지만 실제 응답 메시지를 무시합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 본문이 비어 있는 마지막 메시지를 사용하여 요청 시퀀스의 본문이 비어 있는 마지막 메시지에 대해 회신합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자가 동작 URI가 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage가 아닌 마지막 메시지를 수신할 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 마지막 메시지를 사용하여 회신합니다. 양방향 메시지 교환 프로토콜의 경우 마지막 메시지에 응용 프로그램 메시지가 포함되어 있으며, 단방향 메시지 교환 프로토콜의 경우 마지막 메시지는 비어 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 본문이 비어 있는 마지막 메시지에 대한 승인이 필요 없습니다.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환  
 모든 요청이 유효한 회신을 수신하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 HTTP 요청 레그에 요청 시퀀스의 `TerminateSequence` 메시지를 생성하고 전송합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 응답이 필요하지만 실제 응답 메시지를 무시합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 회신 시퀀스의 `TerminateSequence` 메시지를 사용하여 요청 시퀀스의 `TerminateSequence` 메시지에 대해 회신합니다.  
  
 정상적인 종료 시퀀스에서 두 `TerminateSequence` 메시지 모두에 전체 범위의 `SequenceAcknowledgement`가 포함되어 있습니다.  
  
### <a name="requestreply-addressable-initiator"></a>요청/회신, 주소를 지정할 수 있는 개시자  
  
#### <a name="binding"></a>바인딩  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 각각 한 개의 인바운드 및 아웃바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용하여 요청-회신 메시지 교환 패턴을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 HTTP 요청을 사용하여 모든 메시지를 전송합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.  
  
#### <a name="createsequence-exchange"></a>CreateSequence 교환  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 시퀀스를 제공하는 `CreateSequence` 메시지를 생성합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 시퀀스를 만들기 전에 `CreateSequence`에서 제공하는 시퀀스가 있는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 `CreateSequenceResponse`의 `CreateSequence` 끝점 참조로 주소가 지정된 HTTP 요청에 `ReplyTo` 메시지를 전송합니다.  
  
#### <a name="requestreply-correlation"></a>요청/회신 상관 관계  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 모든 응용 프로그램 요청 메시지에 `MessageId` 및 `ReplyTo` 끝점 참조가 있는지 확인합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개시자는 각 응용 프로그램 요청 메시지에 `CreateSequence` 메시지의 `ReplyTo` 끝점 참조를 적용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자의 경우 들어오는 요청 메시지에 `MessageId` 및 `ReplyTo`가 있어야 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 `CreateSequence` 및 모든 응용 프로그램 요청 메시지의 끝점 참조 URI가 일치하는지 확인합니다.
