---
title: "비동기 메시지 기반 통신"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 비동기 메시지 기반 통신"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df39771295d12e122edbe27e91cd899e3318e301
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="asynchronous-message-based-communication"></a>비동기 메시지 기반 통신

비동기 메시징 및 이벤트 기반 통신은 여러 microservices 및 해당 관련된 도메인 모델에서 변경 내용을 전파할 때 중요 합니다. 토론 microservices 및 경계가 지정 된 컨텍스트 BCs ()의 앞부분에 언급 했 듯이 모델 (사용자, 고객, 제품, 계정, 등) 다른 microservices 또는 BCs 게 서로 다른 것을 의미할 수 있습니다. 변경 될 때 여러 모델에 걸쳐 변경 내용을 조정 하는 방법이 필요는 것입니다. 방법은 결과적 일관성 및 비동기 메시징에 따라 이벤트 기반 통신입니다.

메시징를 사용할 경우 프로세스는 비동기적으로 메시지를 교환 하 여 통신 합니다. 클라이언트 서비스를 하는 명령이 나 요청 메시지를 전송 하 여 합니다. 서비스 회신 하는 경우 클라이언트에 서로 다른 메시지를 보냅니다. 메시지 기반 통신 이므로 클라이언트는 회신 수신 되지 않고 즉시 하 고 있을 수 있음을 응답이 전혀 가정 합니다.

메시지 헤더 (예: 식별 또는 보안 정보 메타 데이터)와 본문으로 구성 됩니다. 메시지는 AMQP 같은 비동기 프로토콜을 통해 일반적으로 전송 됩니다.

이러한 유형의 microservices 커뮤니티의 통신에 대 한 기본 인프라는 달리 큰 브로커 및 orchestrators SOA에 사용 되는 간단한 메시지 브로커를입니다. 간단한 메시지 브로커의 인프라를 일반적으로 "단순," RabbitMQ 또는 Azure 서비스 버스 클라우드의에서 확장 가능한 서비스 버스와 같은 간단한 구현과 함께 메시지 브로커를 으로만 작동 합니다. 이 시나리오에서 대부분의 "스마트" 생각 실리는 생성 하 고 메시지를 사용 하는 끝점에서-즉,는 microservices에 있습니다.

가능한 한을 수행 하려고 노력 해야 다른 규칙은 내부 서비스 간에 비동기 메시징를 사용 하 고 프런트 엔드 서비스 (API 게이트웨이 + 첫 번째 수준에만 클라이언트 앱에서에서 (예: HTTP) 동기 통신을 사용 하도록 microservices).

비동기 메시징 통신의 두 종류가: 단일 수신자 메시지 기반 통신 및 여러 수신기 메시지 기반 통신입니다. 다음 섹션에서 세부 정보 제공 합니다.

## <a name="single-receiver-message-based-communication"></a>단일 수신기 메시지 기반 통신 

단일 수신자와 비동기 통신 메시지 기반 지점 간 통신 하는 채널을 읽고 메시지를 한 번만 처리 하는 소비자 중 정확히 하나에 메시지를 배달 하는 것을 의미 합니다. 그러나 특별 한 경우가 있습니다. 예를 들어, 오류 로부터 자동으로 복구 하려고 하는 클라우드 시스템에는 동일한 메시지를 보낼 수 여러 번입니다. 네트워크 또는 기타 실패로 인해 인해 메시지 보내기를 시도할 수에 대 한 클라이언트 및 서버에서 특정 메시지를 한 번만 처리 하기 위해 idempotent 되도록 작업을 구현 하 합니다.

메시지 기반 통신 수신기 단일 특히 적합에 그림 4-18이이 방법을 보여 주는 같이 다른 비동기 명령을 한 마이크로 서비스에서 전송 합니다.

보내는 메시지 기반 통신 (명령 또는 이벤트 중 하나)을 시작 하면 메시지 기반 통신 동기 HTTP 통신을 혼합 하지 마십시오.

![](./media/image18.PNG)

**그림 4-18**합니다. 비동기 메시지를 수신 하는 단일 마이크로 서비스

명령이 클라이언트 응용 프로그램에 연결 하는 경우 이러한 구현 될 수 있는지 HTTP 동기 명령으로 참고 합니다. 보다 높은 확장성을 할 때 또는 비즈니스 메시지 기반 프로세스에서 이미 실행 중인 경우에 메시지 기반 명령을 사용 해야 합니다.

## <a name="multiple-receivers-message-based-communication"></a>여러 수신기 메시지 기반 통신 

보다 유연한 방식을로 보낸 사람 으로부터 프로그램 통신 될 또는 외부 응용 프로그램에 추가 구독자 microservices를 사용할 수 있도록 게시/구독 메커니즘을 사용 하 여 수도 있습니다. 따라서 하도록 지 원하는 따라는 [원칙 열기/닫기](https://en.wikipedia.org/wiki/Open/closed_principle) 보내는 서비스에 있습니다. 이런 방식으로 추가 하는 구독자는 보낸 사람에 게 서비스를 수정 하지 않고도 나중에 추가할 수 있습니다.

게시/구독 통신을 사용 하면 이벤트 버스 인터페이스를 사용 하 여 모든 구독자에 이벤트 게시를 사용 중일 수 있습니다.

## <a name="asynchronous-event-driven-communication"></a>이벤트 기반 비동기 통신

이벤트 기반 비동기 통신을 사용할 경우 마이크로 서비스는 해당 도메인 내에서 특정 작업이 발생 하 고 다른 마이크로 서비스 제품 카탈로그 마이크로 서비스의 가격 변경 등을 인식 해야 하는 경우 통합 이벤트를 게시 합니다. 추가 microservices 들을 비동기적으로 받을 수 있도록 이벤트를 구독 합니다. 이 경우 수신자를 게시할 수 있는 더 많은 통합 이벤트를 일으킬 수 있는 자체 도메인 엔터티를 업데이트할 수 있습니다. 이 게시/구독 시스템은 일반적으로 이벤트 버스의 구현을 사용 하 여 수행 됩니다. 이벤트 버스 추상화 또는 구독 또는 이벤트를 구독 취소 하 고 이벤트를 게시 하는 데 필요한 api 인터페이스를 디자인할 수 있습니다. 이벤트 버스 있을 수도 있습니다 또는 모든 프로세스 간 및 메시징 브로커 메시징 큐 또는 비동기 통신 및 게시/구독 모델을 지 원하는 서비스 버스와 같은 지역에 더 많은 구현 합니다.

시스템 통합 이벤트에 의해 발생 하는 결과적 일관성을 사용할 경우이 접근 방식을 완전히 지우기 최종 사용자에 게 수 있도록 하는 것이 좋습니다. 시스템 통합 이벤트 SignalR 클라이언트에서 폴링 시스템 등을 모방 하는 접근 방식을 사용 하지 마십시오. 최종 사용자와 비즈니스 소유자 명시적으로 시스템에서 결과적 일관성을 그대로 사용 하 고은 명시적으로 대부분의 경우에서 비즈니스 하지 않았는지이 접근 방식으로 모든 문제를 인식 해야 합니다.

이전에 설명한 것 처럼는 [문제 및 솔루션에 대 한 분산 데이터 관리](#challenges-and-solutions-for-distributed-data-management) 섹션을 여러 microservices에 걸쳐 있는 비즈니스 작업을 구현 하 통합 이벤트를 사용할 수 있습니다. 따라서 해당 서비스 간의 결과적 일관성을 해야 합니다. 결국 일관 된 트랜잭션은 분산된 작업의 컬렉션으로 이루어져 있습니다. 각 동작에서 관련된 마이크로 서비스 도메인 엔터티를 업데이트 하 고 같은 종단 간 비즈니스 태스크 내에서 다음 작업을 발생 시키는 다른 통합 이벤트를 게시 합니다.

중요 한 점은 같은 이벤트를 구독 하는 여러 microservices와 통신 하려는 경우도 있습니다. 게시/구독을 사용할 수 있도록 할 메시징 기반으로 이벤트 기반 통신 그림 4-19에 나와 있는 것 처럼 합니다. 이 게시/구독 메커니즘은 마이크로 서비스 아키텍처에만 적용 되지 않습니다. 하는 방식과 유사 [경계가 지정 된 컨텍스트](http://martinfowler.com/bliki/BoundedContext.html) 에 DDD 전달 해야 하거나 읽기의 데이터베이스에 쓰기 데이터베이스에서 업데이트를 전파 하는 방식과 [명령 및 쿼리 책임 분리 (CQRS)](http://martinfowler.com/bliki/CQRS.html)아키텍처 패턴입니다. 목표는 분산된 시스템에서 여러 데이터 원본 간의 결과적 일관성을 것입니다.

![](./media/image19.png)

**그림 4-19**합니다. 이벤트 기반 비동기 메시지 통신

이벤트 구동 메시지 기반 통신에 사용할 프로토콜 구현에서 결정 합니다. [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) 신뢰할 수 있는 대기 중인된 통신을 달성할 수 있게 합니다.

와 같은 메시지 브로커에서 API를 사용 하 여 코드로 클래스에 관련 된 구현에 따라 (예: 이벤트 버스 인터페이스)는 추상화 수준을 사용 하려는 이벤트 버스를 사용 하면 [RabbitMQ](https://www.rabbitmq.com/) 또는 와같은서비스버스[항목을 사용 하 여 azure 서비스 버스](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)합니다. 또는 다음 NServiceBus, MassTransit, 또는 Brighter와 같은 더 높은 수준의 서비스 버스 이벤트 버스 표현 및 게시/구독 시스템을 사용 하는 것이 좋습니다.

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>프로덕션 시스템에 대 한 기술 메시징에 대 한 참고

추상 이벤트 버스 구현에 사용할 수 있는 메시징 기술을 서로 다른 수준에 노출 됩니다. 예를 들어, 제품 RabbitMQ (메시징 브로커 전송) 및 Azure 서비스 버스와 같은 다른 같은 제품, NServiceBus, MassTransit, 또는 Brighter RabbitMQ 및 Azure 서비스 버스를 기반으로 사용할 수 있는 보다 낮은 수준에서 앉아 합니다. 선택한 응용 프로그램 수준 및 기본적으로 확장성 응용 프로그램에 필요한 개수 다양 한 기능에 따라 달라 집니다. 개발 환경에 대 한 개념 증명 이벤트 버스를 구현 하기 위한 eShopOnContainers 샘플에 했던 대로 Docker 컨테이너에서 실행 중인 RabbitMQ 위에 간단한 구현으로 충분 합니다.

그러나 중요 하이퍼 확장성을 필요로 하는 프로덕션 시스템에서는 Azure 서비스 버스를 평가 해야 할 수 있습니다. 상위 수준 추상화 및 분산된 응용 프로그램의 개발을 용이 하는 기능에 대 한 Brighter NServiceBus, MassTransit, 등의 다른 상용 및 오픈 소스 서비스 버스를 평가 하는 것이 좋습니다. 물론, RabbitMQ 및 Docker와 같은 하위 수준의 기술 기반으로 서비스 버스 기능을 직접 작성할 수 있습니다. 하지만 배관 작동 하는 수는 사용자 지정 엔터프라이즈 응용 프로그램에 대 한 너무 많은 비용.

## <a name="resiliently-publishing-to-the-event-bus"></a>탄력적 이벤트 버스에 게시

여러 microservices에서 이벤트 기반 아키텍처를 구현 하는 경우 문제는 원자 단위로 탄력적 관련된 통합 이벤트에 따라 어떻게 하 든 이벤트 버스에 게시 하는 동안 원래 마이크로 서비스에서 상태를 업데이트 하는 방법 트랜잭션입니다. 다음은 추가 방법은 있을 수 있지만이 수행 하는 몇 가지 방법을 합니다.

-   MSMQ와 같은 트랜잭션 (DTC 기반) 큐를 사용합니다. 그러나 (이것은 레거시 방식입니다.)

-   사용 하 여 [트랜잭션 로그 마이닝](http://www.scoop.it/t/sql-server-transaction-log-mining)합니다.

-   전체를 사용 하 여 [이벤트 소싱](https://msdn.microsoft.com/en-us/library/dn589792.aspx) 패턴입니다.

-   사용 하는 [보낼 편지함 패턴](http://gistlabs.com/2014/05/the-outbox/): 이벤트는 만들고 게시 하는 이벤트 생성자 구성 요소에 대 한 기준 수 있는 메시지 큐로 트랜잭션 데이터베이스 테이블입니다.

비동기 통신을 사용할 때 고려해 야 할 추가 항목은 메시지 idempotence 및 메시지 중복을 제거 합니다. 섹션에서 다루는 이러한 항목은 [microservices (통합 이벤트) 간의 이벤트 기반 통신 구현](#implementing_event_based_comms_microserv) 이 가이드의 뒷부분에 나오는 합니다.

## <a name="additional-resources"></a>추가 리소스

-   **이벤트 구동 메시징**
    [*http://soapatterns.org/design\_패턴/이벤트\_구동\_메시징*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **채널 게시/구독**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **Udi Dahan 합니다. CQRS 설명이 명확해졌습니다**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **명령 및 책임 분리 (CQRS) 쿼리**
    [*https://docs.microsoft.com/azure/architecture/patterns/cqrs*](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

-   **경계가 지정 된 컨텍스트 간 통신**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)

-   **결과적 일관성**
    [*https://en.wikipedia.org/wiki/Eventual\_일관성*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Jimmy Bogard. 복원 력으로 리팩터링: 결합 평가**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)


>[!div class="step-by-step"]
[이전] (통신-에-마이크로 서비스-architecture.md) [다음] (유지 관리-마이크로 서비스-apis.md)
