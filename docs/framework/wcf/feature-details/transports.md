---
title: "Windows Communication Foundation의 전송"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62eb27919e762004667b3d5179c35cb04d9a9422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transports-in-windows-communication-foundation"></a>Windows Communication Foundation의 전송
전송 계층은 채널 스택의 최하위 수준에 있습니다. HTTP, HTTPS, TCP 및 명명된 파이프가 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 사용되는 기본 전송입니다. 이 단원의 항목에서는 이러한 전송 중에서 특정 전송을 선택하여 구성하고 조정 속성을 설정하는 방법에 대해 설명합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 다른 추가 전송도 포함됩니다. 메시지 큐 (MSMQ) 전송에 대 한 정보를 참조 하십시오. [큐 및 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)합니다. 피어-투-피어 전송에 대 한 정보를 참조 하십시오. [피어 투 피어 네트워킹](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [전송 선택](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 세 가지 기본 전송과 그 중 하나를 선택하기 위해 고려해야 할 사항에 대해 설명합니다.  
  
 [메시지 인코더 선택](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 메시지 인코딩 바인딩 요소를 선택할 때 고려해야 할 사항에 대해 설명합니다.  
  
 [스트리밍 메시지 전송](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 스트리밍을 수행하도록 전송 계층을 구성하는 방법에 대해 설명합니다.  
  
 [HTTP 및 HTTPS 구성](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 HTTP 및 HTTPS 전송 바인딩 요소를 구성하는 방법에 대해 설명합니다.  
  
 [방법: WCF URL 예약을 제한된 예약으로 바꾸기](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 제한 예약을 사용하는 방법에 대해 설명합니다.  
  
 [전송 할당량](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 전송 계층에 사용할 수 있는 할당량을 설정할 때 고려해야 할 사항에 대해 설명합니다.  
  
 [NAT 및 방화벽 작업](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 방화벽을 사용하여 메시지를 주고 받을 경우 또는 NAT(Network Address Translation)를 사용할 경우 전송 계층을 구성하는 방법에 대해 설명합니다.  
  
 [Net.TCP 포트 공유](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 Net.TCP 포트 공유 구성 요소를 사용하는 방법에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>관련 단원  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)
