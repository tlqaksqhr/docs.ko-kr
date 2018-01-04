---
title: "큐 및 신뢰할 수 있는 세션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9a78bab9f7c4af23cf01c44e1d22a41a87a96f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="queues-and-reliable-sessions"></a>큐 및 신뢰할 수 있는 세션
큐 및 신뢰할 수 있는 세션은 신뢰할 수 있는 메시징을 구현하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 기능입니다. 이 단원에 포함된 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 메시징 기능에 대해 설명합니다.  
  
 신뢰할 수 있는 메시징이란 신뢰할 수 있는 메시징 소스(소스라고 함)에서 신뢰할 수 있는 메시징 대상(대상이라고 함)으로 메시지를 안전하게 전송하는 방법입니다.  
  
 신뢰할 수 있는 메시징의 주요 요소는 다음과 같습니다.  
  
-   메시지 전송 실패 또는 전송 실패와 상관없이 소스에서 대상으로 보낸 메시지에 대한 보증을 전송합니다.  
  
-   소스와 대상을 서로 구분하면 소스 및 대상의 실패와 복구를 따로 관리할 수 있으며 소스나 대상을 사용할 수 없는 경우라도 메시지를 안전하게 전송 및 배달할 수 있습니다.  
  
 하지만 신뢰할 수 있는 메시징에는 대기 시간이 길다는 단점이 있습니다. 대기 시간이란 메시지가 소스에서 대상까지 도달하는 데 걸리는 시간입니다. 따라서[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 다음과 같은 유형의 신뢰할 수 있는 메시징을 제공합니다.  
  
-   [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md), 신뢰할 수 있는 전송 대기 시간이 길어진다는 비용 없이 제공 됩니다  
  
-   [WCF의 큐](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md), 신뢰할 수 있는 전송과 원본과 대상 간의 분리를 제공 합니다.  
  
## <a name="reliable-sessions"></a>신뢰할 수 있는 세션  
 신뢰할 수 있는 세션에서는 메시징 끝점(소스와 대상)을 분리하는 매개자의 형식이나 개수에 상관없이, WS-ReliableMessaging 프로토콜을 사용하여 소스와 대상 간의 안전한 종단 간 메시지 전송을 제공합니다. 여기에는 끝점 간의 메시지 흐름에 필요한, SOAP를 사용하지 않는 전송 매개자(예: HTTP 프록시) 또는 SOAP를 사용하는 매개자(예: SOAP 기반 라우터나 브리지)가 포함됩니다. 전송에 실패한 경우 신뢰할 수 있는 세션은 메모리 내 전송 창을 사용하여 SOAP 메시지 수준 오류를 마스킹하고 다시 연결합니다.  
  
 신뢰할 수 있는 세션은 대기 시간이 짧은 안전한 메시지 전송을 제공하며, TCP가 IP 브리지를 통해 패킷을 지원하는 것과 같이, 프록시나 매개자를 통해 SOAP 메시지를 지원합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]신뢰할 수 있는 세션 참조 [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)합니다.  
  
### <a name="queues"></a>큐  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 큐를 사용하면 메시지를 안전하게 전송할 수 있으며 소스와 대상을 분리할 수 있지만 대기 시간이 깁니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 대기 중인 통신은 메시지 큐(MSMQ라고도 함)의 위에 빌드됩니다.  
  
 MSMQ는 NT 서비스로 실행되는 Windows의 옵션으로 제공됩니다. 소스 대신 전송 큐에서 전송할 메시지를 캡처하여 대상 큐로 배달합니다. 대상 큐는 대상을 대신해 메시지를 수락하고 나중에 대상에서 메시지를 요청할 때 배달합니다. MSMQ 큐 관리자는 전송 중에 메시지가 손실되지 않도록 신뢰할 수 있는 메시지 전송 프로토콜을 구현합니다. 이러한 프로토콜에는 네이티브 프로토콜 또는 SRMP(SOAP Reliable Messaging Protocol)와 같은 SOAP 기반 프로토콜이 해당됩니다.  
  
 큐 간의 안전한 메시지 전송과 결합된 분리를 통해, 느슨하게 결합된 응용 프로그램이 안전하게 통신할 수 있습니다. 신뢰할 수 있는 세션과 달리 소스와 대상은 동시에 실행될 필요가 없습니다. 따라서 소스의 메시지 생산율과 대상의 메시지 소비율이 맞지 않을 경우, 사실상 큐가 로드 조정 메커니즘으로 사용됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]큐, 참조 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)  
 [신뢰할 수 있는 세션 개요](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
