---
title: "Windows Communication Foundation의 큐"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4dfc78d355db4bd8c9d43541545e6fac35086b39
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="queues-in-windows-communication-foundation"></a>Windows Communication Foundation의 큐
이 단원의 항목에서는 큐에 대한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 지원에 대해 설명합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 Microsoft Message Queuing(이전에 MSMQ라고 함)을 전송으로 사용하여 큐에 대한 지원을 제공하고 다음 시나리오를 사용합니다.  
  
-   느슨하게 결합된 응용 프로그램. 송신 응용 프로그램은 수신 응용 프로그램이 메시지를 처리할 수 있는지 여부를 확인할 필요 없이 큐에 메시지를 보낼 수 있습니다. 큐는 수신 응용 프로그램이 메시지를 처리할 수 있는 속도에 따라 변경되지 않는 일정한 속도로 송신 응용 프로그램이 메시지를 큐에 보낼 수 있는 독립적인 프로세스를 제공합니다. 큐에 메시지를 보내는 작업이 메시지 처리 작업과 밀접하게 연결되지 않을 경우 전반적인 시스템 가용성이 증가합니다.  
  
-   실패 격리. 메시지를 큐에 보내거나 받는 응용 프로그램이 서로 간에 영향을 주지 않고 실패할 수 있습니다. 예를 들어 수신 응용 프로그램이 실패하더라도 송신 응용 프로그램은 계속해서 큐에 메시지를 보낼 수 있습니다. 수신 응용 프로그램이 다시 활성화되면 큐에서 메시지를 처리할 수 있습니다. 실패 격리는 전체 시스템 안정성 및 가용성을 향상시킵니다.  
  
-   로드 조정. 송신 응용 프로그램이 수신 응용 프로그램을 메시지로 가득 채울 수 있습니다. 큐는 수신 응용 프로그램이 과부하가 걸리지 않도록 일치하지 않는 메시지 작성 및 사용률을 관리할 수 있습니다.  
  
-   연결이 끊긴 작업. 송신, 수신 및 처리 작업은 모바일 장치의 경우처럼 대기 시간이 긴 네트워크 또는 가용성이 제한된 네트워크에서 통신하는 경우 연결이 끊어질 수 있습니다. 큐를 사용하면 끝점의 연결이 끊어지더라도 이러한 작업을 계속 수행할 수 있습니다. 다시 연결이 되면 큐가 메시지를 수신 응용 프로그램으로 전달합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 큐 기능을 사용하기 위해 표준 바인딩 중 하나를 사용하거나 표준 바인딩 중 하나가 요구 사항을 충족하지 못하는 경우 사용자 지정 바인딩을 만들 수 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]하나를 선택 하는 방법 및 관련 된 표준 바인딩 참조 [하는 방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지를 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 바인딩을 만들 참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [큐 개요](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 메시지 큐 개념의 개요.  
  
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 큐 지원의 개요.  
  
 [방법: 대기 중인 메시지와 WCF 끝점 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 <xref:System.ServiceModel.NetMsmqBinding> 클래스를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 사이에서 통신하는 방법에 대해 설명합니다.  
  
 [방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 메시지 큐 응용 프로그램 사이에서 통신하는 방법에 대해 설명합니다.  
  
 [세션의 대기 중인 메시지 그룹화](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 단일 수신 응용 프로그램으로 상호 관련된 메시지 처리를 용이하게 하기 위해 큐의 메시지를 그룹화하는 방법에 대해 설명합니다.  
  
 [트랜잭션에서 메시지 일괄 처리](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 메시지를 트랜잭션으로 일괄 처리하는 방법에 대해 설명합니다.  
  
 [배달 못 한 편지 큐를 사용하여 메시지 전송 오류 처리](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 배달 못 한 편지 큐를 사용하여 메시지 전송 및 배달 실패를 처리하고 배달 못 한 편지 큐에서 메시지를 처리하는 방법에 대해 설명합니다.  
  
 [포이즌 메시지 처리](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 포이즌 메시지(수신 응용 프로그램에 전달하는 최대 배달 시도 횟수를 초과한 메시지)를 처리하는 방법에 대해 설명합니다.  
  
 [Windows Vista, Windows Server 2003 및 Windows XP의 큐 기능 차이점](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], [!INCLUDE[wv](../../../../includes/wv-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 간 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 큐 기능의 차이점에 대해 요약합니다.  
  
 [전송 보안을 사용하여 메시지에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 전송 보안을 사용하여 대기 중인 메시지의 보안을 유지하는 방법에 대해 설명합니다.  
  
 [메시지 보안을 사용하여 메시지에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 메시지 보안을 사용하여 대기 중인 메시지의 보안을 유지하는 방법에 대해 설명합니다.  
  
 [대기 중인 메시지 문제 해결](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 일반적인 큐 문제를 해결하는 방법에 대해 설명합니다.  
  
 [대기 중인 통신을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 대기 중인 통신 사용에 대한 최선의 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메시지 큐](http://msdn.microsoft.com/library/ff917e87-05d5-478f-9430-0f560675ece1)
