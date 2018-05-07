---
title: 중요한 추적
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 2dc5010874285ba14dae625fcbf92740eb1707b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="significant-traces"></a>중요한 추적
이 항목에서는 일부 Windows Communication Foundation (WCF)에서 내보낸 주요 추적 합니다.  
  
## <a name="significant-traces"></a>중요한 추적  
  
|추적|설명|  
|-----------|-----------------|  
|메시지 로그 추적|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 사용할 때 `System.ServiceModel.MessageLogging` 메시지가 메시지 로깅 기능에 의해 기록되는 경우 이 추적을 내보냅니다. 이 추적을 클릭하면 메시지가 표시됩니다. 메시지에 대해 네 가지 구성 가능한 로깅 지점은 `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive` 및 `ServiceLevelReceiveRequest`이며 이러한 로깅 지점도 메시지 로그 추적의 메시지 소스 특성에 표시됩니다.|  
|수신된 메시지 추적|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 Information 또는 Verbose 수준에서 사용하는 경우 `System.ServiceModel` 메시지를 받을 때 이 추적을 내보냅니다. 이 추적은 동작 그래프 보기에서 메시지 상관 관계 화살표를 확인해야 합니다.|  
|전송된 메시지 추적|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 Information 또는 Verbose 수준에서 사용하는 경우 `System.ServiceModel` 메시지를 보낼 때 이 추적을 내보냅니다. 이 추적은 동작 그래프 보기에서 메시지 상관 관계 화살표를 확인해야 합니다.|  
|Get ChannelEndpointElement|Information 수준에서 생성 채널 팩터리에 이 추적을 내보냅니다. 클라이언트가 통신하는 끝점에 대한 설명(원격 주소, 바인딩, 계약 이름)을 제공합니다.|  
|Get ServiceElement|Information 수준에서 생성 서비스 호스트에 이 추적을 내보냅니다. 서비스 계약 및 바인딩의 설명을 제공합니다.|  
|SocketConnection create|클라이언트가 수행한 첫 번째 프로세스 동작 및 서비스의 Receive bytes 동작에 이 추적을 내보냅니다. 로컬 및 원격 IP 주소를 제공합니다. Information 수준에서 내보내집니다.|
