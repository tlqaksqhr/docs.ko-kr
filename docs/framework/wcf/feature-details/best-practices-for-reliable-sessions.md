---
title: 신뢰할 수 있는 세션을 위한 최선의 방법
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-for-reliable-sessions"></a>신뢰할 수 있는 세션을 위한 최선의 방법

이 항목에서는 신뢰할 수 있는 세션에 대 한 모범 사례를 설명 합니다.

## <a name="setting-maxtransferwindowsize"></a>MaxTransferWindowSize 설정

신뢰할 수 있는 세션의 Windows Communication Foundation (WCF)은 전송 창을 사용 하 여 클라이언트와 서비스에서 메시지를 보관 합니다. 구성 가능한 속성 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A>는 전송 창이 보관할 수 있는 메시지 수를 나타냅니다.

발신자의 경우 전송 창이 승인을; 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다. 수신기에서 서비스에 대해 버퍼링 할 메시지 수 나타냅니다.

올바른 크기를 선택 합니다. 네트워크의 효율성과 서비스의 최적 용량에 영향을 줍니다. 다음 섹션에서는이 속성 및 값의 영향에 대 한 값을 선택할 때 고려해 야 할 사항을 설명 합니다.

기본 전송 창 크기는 8 개의 메시지.

### <a name="efficient-use-of-the-network"></a>네트워크의 효율적인 사용

이 컨텍스트에서 용어 *네트워크* 클라이언트 (발신자)와 서비스 (수신자) 간의 통신의 기본으로 사용 되는 모든 항목에 해당 합니다. 여기에 전송 연결 및 모든 중간 매개자 또는 사이는 브리지 SOAP 라우터 또는 HTTP 프록시/방화벽을 포함 하 여 합니다.

네트워크를 효율적으로 사용하려면 네트워크 용량을 최대한 사용합니다. 네트워크를 통해 초당 전송할 수 있는 데이터의 양 (*데이터 속도*) 및 수신자에 게 보낸 사람 으로부터 데이터를 전송 하는 데 걸리는 시간 (*대기 시간*) 영향을 얼마나 효과적으로 네트워크 사용 합니다.

발신자의 경우 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 속성은 전송 창이 승인을 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다. 네트워크 대기 시간이 깁니다 하 고 응답 보낸 사람 및 효과적인 네트워크 사용률을 보장 하기 위해 전송 창 크기를 증가 해야 합니다.

예를 들어 보낸 사람에 게 데이터 전송 속도 유지 하는 경우에, 대기 시간 수 높은 경우 발신자와 수신자 간에 여러 매개 자가 존재 또는 데이터 손실 매개자 또는 네트워크를 통과 해야 합니다. 따라서, 발신자는 통신 중에 보낼 새 메시지를 받기 전에 전송 창의 메시지에 대 한 승인을 기다려야 합니다. 버퍼가 대기 시간이 긴 덜 유효 네트워크 사용률입니다. 반면에 전송 창 크기가 너무 클 서비스 클라이언트에서 보낸 데이터의 높은 속도를 따라가야 하기를 할 수 있으므로 서비스를 떨어질 수 있습니다.

### <a name="running-the-service-to-capacity"></a>용량에 맞게 서비스 실행

네트워크를 효율적으로 사용 하 고, 필요한 만큼도 좋습니다 최적의 용량에 실행 되도록 서비스. 수신자의 전송 창 크기 속성은 수신자가 버퍼링할 수 있는 메시지 수를 나타냅니다. 이 메시지 버퍼링은 네트워크 흐름 제어에 도움을 줄 뿐만 아니라 서비스를 최대 용량으로 실행할 수 있도록 합니다. 예를 들어 하나의 메시지를 버퍼가 하 고 메시지가 서비스가 처리할 수 있는 것 보다 빨리 도착할 경우, 다음 네트워크 메시지를 삭제 될 수 있습니다 및 용량을 불필요 하 게 또는 미달 사용 될 수 있습니다.

동시에 수신 하 고 이전에 수신된 된 메시지를 처리 하는 동안 메시지를 버퍼링 하는 대로 서비스의 가용성을 증가 버퍼를 사용 하 여 합니다.

동일한를 사용 하는 것이 좋습니다 `MaxTransferWindowSize` 발신자와 수신자 모두에 있습니다.

### <a name="enabling-flow-control"></a>흐름 제어 사용

*흐름 제어* 는 발신자와 수신자에 맞춰 서로, 메시지를 사용 하 고 작업을 수행 하는, 즉 보장 하는 메커니즘은 생성 하는 가능한 한 빨리 합니다. 클라이언트 및 서비스의 전송 창 크기는 발신자와 수신자가 적절한 동기화 창 내에 있도록 합니다.

속성을 설정 하는 것이 좋습니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> 를 `true` WCF 클라이언트와 WCF 서비스 간에 신뢰할 수 있는 세션을 사용 중인 경우.

## <a name="setting-maxpendingchannels"></a>MaxPendingChannels 설정

하지만 다른 클라이언트의 신뢰할 수 있는 세션 통신 하는 서비스를 작성할 때 여러 클라이언트가 동시에 서비스에 신뢰할 수 있는 세션을 설정 하는 것이 같습니다. 이 경우 서비스 응답은 `MaxPendingChannels` 속성에 따라 달라집니다.

발신자가 수신자에 대해 신뢰할 수 있는 세션 채널을 만드는 경우 발신자와 수신자 간의 핸드셰이크에서 신뢰할 수 있는 세션이 설정됩니다. 신뢰할 수 있는 세션이 설정된 후 채널은 서비스에서 허용할 수 있도록 보류 중인 채널 큐에 저장됩니다. `MaxPendingChannels` 속성은 이 상태에 있을 수 있는 채널 수를 나타냅니다.

더 이상 추가 채널을 받을 수 없는 상태 서비스에 대 한 것 같습니다. 큐가 가득 신뢰할 수 있는 세션 설정 시도가 거부 되 고 클라이언트가 다시 시도해 야 합니다.

더 긴 시간에 대 한 큐에 보류 중인 채널 큐에 남을 수 이기도 합니다. 한편, 신뢰할 수 있는 세션에는 비활성 시간 제한을 발생할 수 있습니다, 채널이 faulted 상태로 전환 합니다.

동시에 여러 클라이언트가 서비스를 제공 하는 서비스를 작성할 때 사용자의 요구에 적합 한 값을 설정 해야 합니다. 에 대 한 값을 너무 높게 설정 된 `MaxPendingChannels` 속성 작업 집합에 영향을 줍니다.

에 대 한 기본값 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> 4 개의 채널 됩니다.

## <a name="reliable-sessions-and-hosting"></a>신뢰할 수 있는 세션 및 호스팅

다음과 같은 중요 한 고려 사항을 염두에서에 둬야 해야, 웹 신뢰할 수 있는 세션을 사용 하는 서비스를 호스팅 하는 경우:

- 신뢰할 수 있는 세션은 상태 저장 세션이며 상태는 AppDomain에 유지됩니다. 따라서 신뢰할 수 있는 세션의 일부인 모든 메시지는 동일한 AppDomain에서 처리되어야 합니다. 팜 또는 가든의 크기는 노드가 하나 보다 큰 웹 팜 및 웹 가든이 제약이 조건을 보장할 수 없습니다.

- 이중 HTTP 채널을 사용 하 여 신뢰할 수 있는 세션 (예: 사용 `WsDualHttpBinding`) 두 HTTP 연결에서 클라이언트의 경우 보다 더 필요할 수 있습니다. 즉, 동시 응용 프로그램 및 프로토콜 메시지가 주어진된 시간에 각 방식으로 전송 될 수 있으므로 신뢰할 수 있는 이중 세션 최대 두 개의 연결이 각 방법 마다 필요할 수 있습니다. 서비스의 메시지 교환 패턴에 따라 특정 조건에서 이중 HTTP 및 신뢰할 수 있는 세션을 사용 하는 웹 호스팅 서비스에 교착 상태가 발생할 수 있다는 것을 의미 합니다. 클라이언트당 허용 가능한 HTTP 연결 수를 늘리려면 다음 관련 구성 파일을 추가 합니다 (예를 들어 *web.config* 해당 서비스의):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  값은 `maxconnection` 특성은 필요한 연결 수입니다. 이 경우 최소값에 대 한 연결 4 이어야 합니다.
