---
title: "마이크로 서비스 아키텍처의 통신"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스 아키텍처 아키텍처의 통신"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8d38095a151b7568619b17340d768eff684d3271
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="communication-in-a-microservice-architecture"></a>마이크로 서비스 아키텍처의 통신

단일 프로세스에서 실행 중인 단일 응용 프로그램, 구성 요소 언어 수준 메서드 또는 함수 호출을 사용 하 여 서로 호출 합니다. 이러한 결합 될 수 있는 강력한 코드와 함께 개체를 만드는 경우 (예를 들어 `new ClassName()`), 또는 구체적인 개체 인스턴스가 아닌 추상화를 참조 하 여 종속성 주입을 사용 하는 경우 분리 된 방식으로 호출할 수 있습니다. 어떤 방법을 사용 하는 개체는 동일한 프로세스 내에서 실행 됩니다. 가장 큰 문제 microservices 기반 응용 프로그램에 단일 응용 프로그램에서 변경 하는 경우 통신 메커니즘을 변경 있다는 점입니다. 서비스에 대 한 RPC 호출에 대 한 프로세스에서 메서드 호출에서 직접 변환은 수 다 스러운 고 분산 환경이 없습니다 효율적 통신의 원활한 수행 되지 것입니다. 분산된 시스템을 제대로 디자인 문제는 적절 하 게 이라는 것도 라고 canon는 [분산 컴퓨팅 fallacies](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) 개발자에서 이동할 때 종종 확인 된 가정을 나열 하는 모놀리식 디자인을 배포합니다.

한 가지 해결 하지 않지만 몇 가지 있습니다. 한 가지 해결 최대한 많은 비즈니스 microservices 격리 하는 작업이 포함 됩니다. 그런 다음 내부 microservices 간의 비동기 통신을 사용 하 고 세분화 된 통신을 성긴 통신을 사용 하 여 개체 간의 프로세스 내의 통신에서 일반적으로 바꿉니다. 이 작업은 호출, 그룹화 하 고 클라이언트에 여러 내부 호출의 결과 집계 하는 데이터를 반환 하 여 수행할 수 있습니다.

Microservices 기반 응용 프로그램은 여러 프로세스 또는 서비스에 일반적으로 균등 여러 서버 또는 호스트에서 실행 되는 분산된 시스템입니다. 각 서비스 인스턴스는 일반적으로 프로세스입니다. 따라서 서비스는 HTTP, AMQP 또는 각 서비스의 성격에 따라 TCP와 같은 이진 프로토콜 등 프로세스 간 통신 프로토콜을 사용 작용 해야 합니다.

마이크로 서비스 커뮤니티의 방법은 승격 "[스마트 끝점 및 단순 파이프](http://simplicable.com/new/smart-endpoints-and-dumb-pipes)." 이 표 어를 분리 microservices, 간의 가능한 및 단일 마이크로 서비스 내에서 가능한 같이 화합 디자인을 권장 합니다. 앞에서 설명한 대로 각 마이크로 서비스는 자체 데이터 및 자체 도메인 논리를 소유 합니다. WS-같은 복잡 한 프로토콜 대신 REST 통신을 사용 하 여 종단 간 응용 프로그램을 작성 microservices choreographed 단순히 일반적으로 하지만\* 대신 유연한 이벤트 기반 통신 중앙 orchestrators 비즈니스 프로세스-합니다.

두 가지 자주 사용 되는 프로토콜은 HTTP 요청/응답 리소스 (대부분의 모든 쿼리) 하는 경우 Api 사용 하 고 여러 microservices 간에 업데이트 통신할 때 경량 비동기 메시징 합니다. 이러한 작업은 다음 섹션에서 자세히 설명 되어 있습니다.

## <a name="communication-types"></a>통신 형식

클라이언트와 서비스는 다양 한 유형의 각각 다른 시나리오 및 목표를 대상으로 지정 되지 않은 통신을 통해 통신할 수 있습니다. 처음 두 개의 축에는 이러한 유형의 통신을 분류할 수 있습니다.

프로토콜은 동기 또는 비동기 경우 첫 번째 축 정의:

-   동기 프로토콜입니다. HTTP는 동기 프로토콜입니다. 클라이언트 요청을 보내고 서비스 로부터 응답을 대기 합니다. 동기 될 수 있는 클라이언트 코드 실행의 독립적인 (스레드 차단) 또는 비동기 (스레드가 차단 되지 않으며, 및 응답에는 콜백 결국 도달 합니다). 여기서 중요 한 프로토콜 (HTTP/HTTPS) 동기화 되었으며 클라이언트 코드는 HTTP 서버 응답을 받을 때 해당 작업을 계속만 수는 있습니다.

-   비동기 프로토콜입니다. AMQP (많은 운영 체제 및 클라우드 환경에서 지 원하는 프로토콜)와 같은 다른 프로토콜 비동기 메시지를 사용 합니다. 응답을 받기 위해 일반적으로 클라이언트 코드 또는 메시지 보낸 사람을 설치 하지 기다리지 않습니다. 방금 RabbitMQ 큐 나 기타 메시지 브로커에 메시지를 보낼 때 메시지를 보냅니다.

두 번째 축 정의 하는 것의 통신에는 단일 수신자 또는 여러 수신기:

-   단일 수신자입니다. 정확히 하나의 수신기 또는 서비스에서 각 요청을 처리 해야 합니다. 이 통신의 예로 [명령 패턴](https://en.wikipedia.org/wiki/Command_pattern)합니다.

-   여러 수신기입니다. 여러 수신기를 0으로 각 요청을 처리할 수 있습니다. 이러한 유형의 통신 비동기 이어야 합니다. 예로 [게시/구독](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) 같은 패턴에 사용 되는 메커니즘 [이벤트 기반 아키텍처](http://microservices.io/patterns/data/event-driven-architecture.html)합니다. 이 크기는 기반 이벤트 버스 인터페이스 또는 메시지 브로커에 이벤트를 통해 여러 microservices 사이 데이터 업데이트를 전파 하는 동안 일반적으로 서비스 버스 또는 같은 비슷한 아티팩트를 통해 구현 [Azure 서비스 버스](https://azure.microsoft.com/services/service-bus/) 를 사용 하 여 [항목과 구독](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)합니다.

마이크로 서비스 기반 응용 프로그램에는 이러한 통신 스타일의 조합을 종종 사용 합니다. 가장 일반적인 유형이 동기 프로토콜로 HTTP/HTTPS와 같은 단일 발신자 통신이 일반 Web API HTTP 서비스를 호출할 때. 일반적으로 Microservices microservices 간의 비동기 통신에 대 한 메시징 프로토콜을 사용합니다.

이러한 축이 가능한 통신 메커니즘에 쉽게 구분할 수 있도록 해야 하지만 없는 중요 한 고려 사항 microservices 빌드할 때 알아 두면 유용 합니다. 선택한 프로토콜을 클라이언트 스레드 실행 하더라도 비동기 특성의 비동기 특성은 microservices를 통합 하는 경우 중요 한 포인트입니다. 어떤 *은* 중요 수 있는 다음 섹션에서 설명한 대로 microservices의 독립성을 유지 하면서 사용자 microservices 비동기적으로 통합할 수 있습니다.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>비동기 마이크로 서비스 마이크로 서비스의 자치 성을 적용합니다

앞서 언급 했 듯이 microservices 기반 응용 프로그램을 빌드할 때 중요 한 점은 프로그램 microservices 통합 방법입니다. 이상적으로 내부 microservices 간의 통신을 최소화 하려고 해야 합니다. 덜 간의 통신 microservices, 나아집니다. 하지만, 대부분의 경우에서 해야 합니다는 microservices 어떻게 하 든 통합. 그렇게 해야 할 때 중요 한 규칙을 여기가 microservices 간의 통신은 비동기 되어야 합니다. 의미는 아닙니다 (예를 들어 비동기 메시징 동기 HTTP 비교)는 특정 프로토콜을 사용 해야 합니다. 할 microservices 간의 통신 데이터를 비동기적으로 전파만 수행 되어야 하지만 다른 내부 microservices 초기 서비스의 HTTP 요청/응답 작업의 일환으로 의존 하지 마십시오.

가능 하면 쿼리에 대해서도 하지 여러 microservices 간에 동기 통신 (요청/응답)에 종속 되지 않습니다. 각 마이크로 서비스의 목표는 자치 및 클라이언트 소비자에 게 사용할 수 있는 경우에 종단 간 응용 프로그램의 일부인 다른 서비스는 다운 되었거나 비정상입니다. 하나의 마이크로 서비스에서 다른 microservices (예: 데이터 쿼리에 대 한 HTTP 요청을 수행 중)의 호출을 수행 하도록 만들어야 생각 되 면 클라이언트 응용 프로그램에 대 한 응답을 제공할 수 있게 되기를 주문, 일부 경우에 복원 되지 않는 아키텍처가 있다고 microservices 실패합니다.

또한 microservices, 긴를 만들 때 사용 된 HTTP 요청/응답 주기 그림 4-15의 첫 부분에 나와 있는 것 처럼 체인을 요청 하는 같은 간의 HTTP 종속성 뿐만 아니라를 사용 하면 프로그램 microservices 하지 자치 하지만 성능에도 해당 체인의 서비스 중 하나는 하지 정상적으로 수행 되는 즉시 영향을 받습니다. 

쿼리 요청 등 microservices 간의 동기 종속성 추가 더, 클라이언트 응용 프로그램에 대 한는 나쁜 전체 응답 시간을 가져옵니다.

![](./media/image15.png)

**그림 4-15**합니다. Microservices 간의 통신의 방식과 안티패턴

프로그램 마이크로 서비스를 다른 마이크로 서비스에 추가 기능으로 발생 하는 경우 가능 하면 수행 하지 마십시오 해당 작업이 동기적으로 처리 하 고 원래 마이크로 서비스 요청 및 응답 작업의 일환으로. 대신, 비동기적으로 수행 (등 비동기 메시징 또는 통합 이벤트, 큐를 사용 하 여.). 그러나 가능한 한 많은 원래 동기 요청 및 응답 작업의 일부로 동기적으로 동작을 호출 하지 마십시오.

마지막으로 (및이 대부분의 문제 microservices 빌드할 때 발생 하는 위치)에 초기 마이크로 서비스 원래 다른 microservices가 소유 하는 데이터를 필요로 한다면 해당 데이터에 대 한 동기 요청에 의존 하지 마십시오. 대신, 복제 하거나 (일반적으로 사용 하 여 통합 이벤트 이후 단원에서 설명 된 대로) 결과적 일관성을 사용 하 여 초기 서비스의 데이터베이스에 해당 데이터 (만: 필요한 특성)를 전파 합니다.

섹션에서 설명한 것 처럼 [각 마이크로 서비스에 대 한 도메인 모델 경계를 식별](#identifying-domain-model-boundaries-for-each-microservice), 여러 microservices에서 일부 데이터를 중복은 잘못 된 디자인 하지-반면 경우 이렇게 하면 수 데이터 변환 하 고 특정 언어 또는 조건에 해당 추가 도메인 또는 컨텍스트 제한 합니다. 예를 들어,는 [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) 라는 identity.api 엔터티가 명명 된 사용자는 대부분의 사용자의 데이터를 담당 하는 마이크로 서비스를 해야 하는 응용 프로그램입니다. 그러나 Ordering 마이크로 서비스 내에서 사용자에 대 한 데이터를 저장 해야 하는 경우 저장할 있습니다 구매자 라는 다른 엔터티로. 구매자 엔터티는 원래 사용자 엔터티와 동일한 id를 공유 하지만 Ordering 도메인과 전체 사용자 프로필이 아닌에 필요한 몇 가지 특성 수 있습니다.

전달 하 고 결과적 일관성을 가지려면 microservices 비동기적으로 데이터에 전파 모든 프로토콜을 사용할 수 있습니다. 앞서 언급 했 듯이 통합 이벤트 또는 이벤트 버스 메시지 브로커 또는 있습니다 사용 하 여 HTTP 대신 다른 서비스를 폴링하여 이벤트 알림에 사용 되 고 사용할 수 있습니다. 중요 하지 않습니다. 중요 한 규칙에 microservices 간의 동기 종속성을 만들지입니다.

다음 섹션에서는 마이크로 서비스 기반 응용 프로그램에서 사용을 고려 하는 여러 통신 스타일에 설명 합니다.

## <a name="communication-styles"></a>통신 스타일

여러 프로토콜 및 선택 항목을 사용 하려면 통신 유형에 따라 통신에 사용할 수 있습니다. 동기 요청/응답 기반 통신 메커니즘을 사용 하는 HTTP 및 REST 방식 등의 프로토콜 경우 가장 일반적인 Docker 호스트나 마이크로 서비스 클러스터 외부 서비스를 게시 하는 경우에 특히 합니다. 내부적으로 (Docker 호스트나 microservices 클러스터) 서비스 간에 통신 하는 경우 (예: 서비스 패브릭 원격 또는 TCP 및 이진 형식을 사용 하 여 WCF) 이진 형식 통신 메커니즘을 사용할 수도 있습니다. 또는 AMQP 같은 비동기, 메시지 기반 통신 메커니즘을 사용할 수 있습니다.

JSON 또는 XML과 같은 여러 메시지 형식의 또는 이진 형식으로 더 효율적일 수 있습니다. 선택한 이진 형식에 맞게 표준 없으면 것이 좋습니다 되지 않았을 수는 해당 형식을 사용 하 여 서비스를 게시할 공개적으로 합니다. 프로그램 microservices 간의 내부 통신에 대 한 비표준 형식을 사용할 수 있습니다. Microservices (Docker orchestrators 또는 Azure 서비스 패브릭) Docker 호스트나 마이크로 서비스 클러스터 내에서 또는 통신 하는 microservices 고유의 클라이언트 응용 프로그램 간의 통신 하는 경우 이렇게 할 수도 있습니다.

### <a name="requestresponse-communication-with-http-and-rest"></a>HTTP와 REST 요청/응답 통신 

클라이언트가 요청/응답 통신을 사용 하는 요청을 서비스에는 서비스 프로세스 요청을 보냅니다 하 고 응답을 보냅니다. 요청/응답 통신은 특히 적합 클라이언트 앱에서 실시간으로 UI (라이브 사용자 인터페이스)에 대 한 데이터를 쿼리 합니다. 따라서 마이크로 서비스 아키텍처에서 사용이 통신 메커니즘 대부분의 쿼리에서 같이 그림 4-16입니다.

![](./media/image16.png)

**그림 4-16**합니다. HTTP 요청/응답 통신 (동기 또는 비동기)를 사용 하 여

클라이언트가 요청/응답 통신을 사용 하는 응답 도달 하는 짧은 시간에 일반적으로 몇 초 또는 1 초 미만, 최대 가정 합니다. 응답이 지연된에 대 한 기반으로 하는 비동기 통신을 구현 해야 [메시징 패턴](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) 및 [메시징 기술](https://en.wikipedia.org/wiki/Message-oriented_middleware), 다음 섹션에서 설명 하는 다른 접근 방식을 변수인 합니다.

요청/응답 통신을 위한 인기 있는 아키텍처 스타일은 [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)합니다. 이 방법은, on,와 밀접 하 게 결합 기반는 [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) 프로토콜, POST, GET, 등의 HTTP 동사를 수용 하 고 저장 합니다. REST은 서비스를 만들 때 가장 흔히 사용 되는 아키텍처 통신 방법을입니다. ASP.NET Core 웹 API 서비스를 개발 하는 경우에 REST 서비스를 구현할 수 있습니다.

인터페이스 정의 언어로 HTTP REST 서비스를 사용 하는 경우 추가 값이 있습니다. 예를 들어, 사용 하는 경우 [Swagger 메타 데이터](http://swagger.io/) 서비스 API를 설명 하기 위해 직접 검색 하 고 서비스를 사용할 수 있는 클라이언트 스텁을 생성 하는 도구를 사용할 수 있습니다.

### <a name="additional-resources"></a>추가 리소스

-   **Martin Fowler. Richardson Maturity Model입니다.** 나머지 모델에 대 한 설명
    [*http://martinfowler.com/articles/richardsonMaturityModel.html*](http://martinfowler.com/articles/richardsonMaturityModel.html)

-   **Swagger 합니다.** 공식 사이트입니다.
    [*http://swagger.io/*](http://swagger.io/)

### <a name="push-and-real-time-communication-based-on-http"></a>밀어넣기 및 HTTP 기반 실시간 통신

와 같은 다른 가능성 (일반적으로 다양 한 용도로 REST 보다)는 더 높은 수준의 프레임 워크와 함께 실시간 및 1 대 다 통신 [ASP.NET SignalR](https://www.asp.net/signalr) 및와 같은 프로토콜 [Websocket](https://en.wikipedia.org/wiki/WebSocket)합니다.

그림 4-17에서 볼 수 있듯이 실시간 HTTP 통신 서버 코드 데이터를 사용할 수 있게 되 면 연결 된 클라이언트에 콘텐츠를 푸시하는 대신 새 데이터를 요청 하는 클라이언트에 대 한 대기 서버는 있음을 의미 합니다.

![](./media/image17.png)

**그림 4-17**합니다. 일대일 실시간 비동기 메시지 통신

실시간으로 통신 이므로 클라이언트 응용 프로그램 설정이 거의 즉시 변경 내용이 표시 합니다. 이 일반적으로 많은 Websocket 연결 (클라이언트 마다 하나씩)를 사용 하 여 Websocket와 같은 프로토콜에서 처리 됩니다. 일반적인 예는 서비스 동시에 여러 클라이언트에 대 한 웹 응용 프로그램에 스포츠 경기 점수에 변경 내용을 전달 하는 경우입니다.


>[!div class="step-by-step"]
[이전] [다음] (비동기-메시지-기반-communication.md) (direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
