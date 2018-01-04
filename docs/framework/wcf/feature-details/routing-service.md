---
title: "라우팅 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7214a14b11ae1f91906c8d2140bc82836988390
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="routing-service"></a>라우팅 서비스
라우팅 서비스는 메시지 라우터 역할을 하는 제네릭 SOAP 매개자입니다. 라우팅 서비스의 핵심 기능은 메시지 내용을 기반으로 메시지를 라우트할 수 있는, 즉 메시지 헤더나 메시지 본문 같은 메시지 자체에 포함된 값을 기반으로 메시지를 클라이언트 끝점에 전달할 수 있는 기능입니다.  
  
 <xref:System.ServiceModel.Routing.RoutingService>는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 네임스페이스에서 <xref:System.ServiceModel.Routing> 서비스로 구현됩니다. 라우팅 서비스는 메시지를 받은 다음 메시지 내용을 기반으로 각 메시지를 하나 이상의 클라이언트 끝점에 라우트하는 하나 이상의 서비스 끝점을 노출합니다. 라우팅 서비스는 다음과 같은 기능을 제공합니다.  
  
-   내용 기반 라우팅  
  
    -   서비스 집계  
  
    -   서비스 버전 관리  
  
    -   우선 순위 라우팅  
  
    -   동적 구성  
  
-   프로토콜 브리징  
  
-   SOAP 처리  
  
-   고급 오류 처리  
  
-   백업 끝점  
  
 위에 나열된 이점을 제공하는 매개자 서비스를 만들 수는 있지만 종종 이러한 구현이 특정 시나리오나 솔루션으로 제한되어 새 응용 프로그램에 적용되지 않을 수 있습니다.  
  
 라우팅 서비스는 동적으로 구성 가능한 플러그형 제네릭 SOAP 매개자를 제공합니다. 이 매개자는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 및 채널 모델과 호환되고 SOAP 기반 메시지의 내용 기반 라우팅을 수행하는 데 사용됩니다.  
  
> [!NOTE]
>  라우팅 서비스는 현재 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 서비스의 라우팅을 지원하지 않습니다.  REST 호출을 라우트하려면 사용해 보십시오 <xref:System.Web.Routing> 또는 [응용 프로그램 요청 라우팅](http://go.microsoft.com/fwlink/?LinkId=164589) (http://go.microsoft.com/fwlink/?LinkId=164589).  
  
## <a name="content-based-routing"></a>내용 기반 라우팅  
 내용 기반 라우팅은 메시지에 들어 있는 하나 이상의 값을 기반으로 메시지를 라우트할 수 있는 기능입니다. 라우팅 서비스는 각 메시지를 검사하고 메시지 내용과 사용자 제공 라우팅 논리를 기반으로 메시지를 대상 끝점에 라우트합니다. 내용 기반 라우팅은 서비스 집계, 서비스 버전 관리 및 우선 순위 라우팅에 대한 기초를 제공합니다.  
  
 내용 기반 라우팅을 구현하기 위해 라우팅 서비스는 라우트할 메시지 내의 특정 값과 일치시키는 데 사용되는 <xref:System.ServiceModel.Dispatcher.MessageFilter> 구현을 사용합니다. 경우는 **MessageFilter** 메시지, 메시지와 연결 된 대상 끝점으로 라우팅됩니다. 일치 하는 **MessageFilter**합니다.  메시지 필터는 필터 테이블(<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>)로 그룹화되어 복잡한 라우팅 논리를 생성합니다. 예를 들어 필터 테이블에 다섯 개의 대상 끝점 중 하나로만 메시지를 라우트할 수 있도록 하는 상호 배타적인 다섯 개의 메시지 필터가 있을 수 있습니다.  
  
 라우팅 서비스를 사용하면 내용 기반 라우팅을 수행하는 데 사용되는 논리를 구성할 수 있을 뿐 아니라 런타임에 라우팅 논리를 동적으로 업데이트할 수 있습니다.  
  
 메시지 필터를 필터 테이블로 그룹화하면 다음과 같은 여러 라우팅 시나리오를 처리할 수 있는 라우팅 논리를 생성할 수 있습니다.  
  
-   서비스 집계  
  
-   서비스 버전 관리  
  
-   우선 순위 라우팅  
  
-   동적 구성  
  
 메시지 필터 및 필터 테이블에 대 한 자세한 내용은 참조 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md) 및 [메시지 필터](../../../../docs/framework/wcf/feature-details/message-filters.md)합니다.  
  
### <a name="service-aggregation"></a>서비스 집계  
 내용 기반 라우팅을 사용하면 외부 클라이언트 응용 프로그램의 메시지를 받는 하나의 끝점을 노출한 다음 메시지에 들어 있는 값을 기반으로 각 메시지를 적절한 내부 끝점으로 라우트할 수 있습니다. 이는 다양한 백엔드 응용 프로그램에 대해 하나의 특정 끝점을 제공하거나 다양한 서비스로 응용 프로그램을 팩터링하는 동안 고객에게 하나의 응용 프로그램 끝점을 제공할 때 유용합니다.  
  
### <a name="service-versioning"></a>서비스 버전 관리  
 새 버전의 솔루션으로 마이그레이션하는 경우 기존 고객을 지원하기 위해 이전 버전도 함께 유지 관리해야 할 수 있습니다. 이를 위해 새 버전에 연결하는 클라이언트가 솔루션과 통신할 때 다른 주소를 사용해야 하는 경우가 종종 있습니다. 라우팅 서비스를 사용하면 메시지에 들어 있는 버전 관련 정보를 기반으로 메시지를 적절한 솔루션으로 라우트하여 두 버전의 솔루션을 모두 지원하는 하나의 서비스 끝점을 노출할 수 있습니다. 이러한 구현에 대 한 예제 참조 [방법: 서비스 버전 관리](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md)합니다.  
  
### <a name="priority-routing"></a>우선 순위 라우팅  
 여러 클라이언트에 서비스를 제공하는 경우 일부 파트너와의 SLA(서비스 수준 계약)가 있을 수 있습니다. SLA는 해당 파트너의 모든 데이터를 다른 클라이언트의 데이터와 별도로 처리하도록 요구하는 계약입니다. 메시지에 들어 있는 고객 관련 정보를 검색하는 필터를 사용하면 특정 파트너의 메시지를 해당 파트너의 SLA 요구 사항을 충족시키기 위해 만들어진 끝점으로 손쉽게 라우트할 수 있습니다.  
  
## <a name="dynamic-configuration"></a>동적 구성  
 서비스 중단 없이 메시지를 처리해야 하는 업무용 시스템을 지원하려면 런타임에 시스템 구성 요소의 구성을 수정할 수 있어야 합니다. 이러한 요구를 지원하기 위해 라우팅 서비스는 런타임에 라우팅 서비스 구성을 동적으로 업데이트할 수 있는 <xref:System.ServiceModel.IExtension%601> 구현인 <xref:System.ServiceModel.Routing.RoutingExtension>을 제공합니다.  
  
 라우팅 서비스의 동적 구성에 대 한 자세한 내용은 참조 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md)합니다.  
  
## <a name="protocol-bridging"></a>프로토콜 브리징  
 매개자 시나리오의 과제 중 하나는 메시지가 수신되는 끝점과 다른 전송 또는 SOAP 버전 요구 사항이 내부 끝점에 있을 수 있다는 것입니다. 이 시나리오를 지원하기 위해 라우팅 서비스는 SOAP 메시지를 대상 끝점에 필요한 <xref:System.ServiceModel.Channels.MessageVersion>으로 처리할 뿐 아니라 프로토콜을 브리징할 수 있습니다. 그러면 한 프로토콜은 내부 통신용으로 사용하고 다른 한 프로토콜은 외부 통신용으로 사용할 수 있습니다.  
  
 서로 다른 전송을 사용하는 끝점 간의 메시지 라우팅을 지원하기 위해 라우팅 서비스는 서로 다른 프로토콜을 브리징할 수 있는 시스템 제공 바인딩을 사용합니다. 이 동작은 라우팅 서비스가 메시지가 라우트되는 클라이언트 끝점과 다른 프로토콜을 사용하는 경우 자동으로 발생합니다.  
  
## <a name="soap-processing"></a>SOAP 처리  
 라우팅에 공통적으로 요구되는 기능은 SOAP 요구 사항이 서로 다른 끝점 간에 메시지를 라우트할 수 있는 기능입니다. 이 요구 사항을 지원 하기 위해 라우팅 서비스는 다음과 같이 제공 됩니다. 한 <xref:System.ServiceModel.Routing.SoapProcessingBehavior> 을 자동으로 만드는 새 **MessageVersion** 메시지는에 라우트하기 전에 해당 대상 끝점의 요구 사항을 충족 하는 합니다. 이 동작은 또한 새 만듭니다 **MessageVersion** 되도록 요청 클라이언트 응용 프로그램에 반환 하기 전에 응답 메시지는 **MessageVersion** 응답의 아키텍처와 일치 원래 요청입니다.  
  
 SOAP 처리에 대 한 자세한 내용은 참조 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md)합니다.  
  
## <a name="error-handling"></a>오류 처리  
 네트워크 통신을 사용하는 분산 서비스로 구성된 시스템에서는 시스템 내의 통신이 일시적인 네트워크 오류를 처리할 수 있는지 확인해야 합니다.  라우팅 서비스는 서비스 중지를 초래하는 다양한 통신 오류 시나리오를 처리할 수 있는 오류 처리를 구현합니다.  
  
 라우팅 서비스에서 메시지를 보내려고 시도하는 중에 <xref:System.ServiceModel.CommunicationException>이 발생하면 오류 처리가 수행됩니다.  일반적으로 이러한 예외는 정의된 클라이언트 끝점과 통신을 시도하는 중에 문제가 발생했음을 나타냅니다(예: <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> 또는 <xref:System.ServiceModel.CommunicationObjectFaultedException>).  오류 처리 코드는 또한 catch 하 고 때 보내기를 재시도 합니다는 **TimeoutException** 발생에서 파생 되지 않은 또 다른 일반적인 예외인 **CommunicationException**합니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]오류 처리, 참조 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md)합니다.  
  
## <a name="backup-endpoints"></a>백업 끝점  
 필터 테이블의 각 필터 정의와 연결된 대상 클라이언트 끝점 외에도 전송 실패 시 메시지를 라우트할 백업 끝점의 목록을 만들 수도 있습니다. 오류가 발생할 경우 필터 항목에 대해 정의된 백업 목록이 있으면 라우팅 서비스는 이 목록에 정의되어 있는 첫 번째 끝점에 메시지를 보내려고 시도합니다. 이 전송 시도가 실패하면 라우팅 서비스는 다음 끝점에 메시지를 보내려고 시도하고 전송 시도가 성공하거나 전송과 관련 없는 오류가 반환되거나 백업 목록에 있는 모든 끝점에서 전송 오류가 반환될 때까지 이 작업을 계속 수행합니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]백업 끝점, 참조 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md) 및 [메시지 필터](../../../../docs/framework/wcf/feature-details/message-filters.md)합니다.  
  
## <a name="streaming"></a>스트리밍  
 스트리밍을 지원하도록 바인딩을 설정하는 경우 라우팅 서비스는 성공적으로 메시지를 스트리밍할 수 있습니다.  그러나 메시지를 버퍼링해야 할 수 있는 경우도 있습니다.  
  
-   멀티캐스트(추가 메시지 복사본을 만들기 위한 버퍼)  
  
-   장애 조치(메시지를 백업에 전송해야 하는 경우의 버퍼)  
  
-   System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly가 false임(필터가 본문을 검사할 수 있도록 MessageBuffer와 함께 MessageFilterTable을 표시하기 위한 버퍼)  
  
-   동적 구성  
  
## <a name="see-also"></a>참고 항목  
 [라우팅 소개](../../../../docs/framework/wcf/feature-details/routing-introduction.md)  
 [라우팅 계약](../../../../docs/framework/wcf/feature-details/routing-contracts.md)  
 [메시지 필터](../../../../docs/framework/wcf/feature-details/message-filters.md)
