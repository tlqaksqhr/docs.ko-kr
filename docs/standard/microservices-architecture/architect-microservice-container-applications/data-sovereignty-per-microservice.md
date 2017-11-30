---
title: "마이크로 서비스 당 데이터 sovereignty"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스 당 데이터 sovereignty"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c51daae04215cfa6f5b5b8d2158a8ed1a8949652
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="data-sovereignty-per-microservice"></a>마이크로 서비스 당 데이터 sovereignty

Microservices 아키텍처에 대 한 중요 한 규칙은 도메인 데이터와 논리 각 마이크로 서비스를 소유 해야 합니다. 전체 응용 프로그램에서 해당 논리 및 데이터를 소유 하는 것 처럼 하므로 각 마이크로 서비스 소유 해야 해당 논리 및 데이터가 마이크로 서비스 당 독립 배포와는 자치 수명 주기에서 합니다.

즉, 도메인의 개념적 모델 하위 시스템 또는 microservices 간에 달라 집니다. 엔터프라이즈 응용 프로그램을 고객 관계 관리 (CRM) 응용 프로그램, 트랜잭션 구매 하위 시스템 및 고객 지원 하위 시스템 고유한 고객 엔터티 특성 및 데이터에 대 한 각 호출 하 고 각각 서로 다른 사용 고려 컨텍스트 (BC)을 제한 합니다.

이 원칙은 비슷합니다 [도메인 기반 디자인 (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design)여기서 각 [경계가 지정 된 컨텍스트](https://martinfowler.com/bliki/BoundedContext.html) 또는 자치 하위 시스템 또는 서비스의 도메인 모델 (데이터와 논리 및 동작)를 소유 해야 합니다. 각 DDD 경계가 지정 된 컨텍스트는 한 비즈니스 마이크로 서비스 (하나 또는 여러 서비스)에 연결 됩니다. (여기서 확장 다음 섹션에서 컨텍스트 경계가 지정 된 패턴에 대 한이 지점에서.)

반면에 단일 중앙 집중식된 데이터베이스 또는 몇 개의 데이터베이스 하는 많은 응용 프로그램에서 사용 하는 일반적인 (모놀리식 데이터) 방법이입니다. 그림 4-7 같이 전체 응용 프로그램 및 해당 모든 내부 하위 시스템에 사용 되는 SQL 데이터베이스를 정규화 종종입니다.

![](./media/image7.png)

**그림 4-7**합니다. 데이터 sovereignty 비교: microservices와 모놀리식 데이터베이스

중앙 집중식된 데이터베이스 접근 방식 처음 간단 모양과 일관성 있는 모든 다른 하위 시스템에 있는 엔터티의 다시 사용할 수 있도록 하는 것 같습니다. 하지만 여러 다른 하위 시스템을 제공 하는 대부분의 경우 특성 및 필요 하지 않은 열을 포함 하는 큰 테이블 /fd 현실은 합니다. 짧은 내역 하이킹 하루 종일 자동차 여행 가져오고 geography 학습에 대해 동일한 물리적 맵을 사용 하는 동안 같습니다.

일반적으로 단일 관계형 데이터베이스와는 모놀리식 응용 프로그램에 중요 한 이점: [ACID 트랜잭션](https://en.wikipedia.org/wiki/ACID) 및 SQL 언어를 모든 테이블 및 응용 프로그램에 관련 된 데이터에서 모두 작동 합니다. 이 방법은 쉽게 여러 테이블의에서 데이터를 결합 하는 쿼리를 작성 하는 방법을 제공 합니다.

그러나 microservices 아키텍처를 이동할 때 데이터 액세스는 훨씬 더 복잡해 집니다. 하지만 ACID 트랜잭션 수 또는 마이크로 서비스 또는 경계가 지정 된 컨텍스트 내에서 사용 해야 하는 경우에 각 마이크로 서비스를 소유한 데이터는 해당 마이크로 서비스에 전용 포트 이며 해당 마이크로 서비스 API를 통해 액세스할 수 있습니다. 데이터를 캡슐화 하면는 microservices 느슨하게 결합 된 있고 서로 독립적으로 개발할 수 있습니다. 여러 서비스에 동일한 데이터에 액세스 된, 스키마 업데이트는 모든 서비스에 대 한 조정 된 업데이트 해야 합니다. 마이크로 서비스 수명 주기 자치를 작동 하지 않으므로이 있습니다. 하지만 분산된 데이터 구조 뜻합니다 microservices 간에 단일 ACID 트랜잭션을 만들 수 없습니다. 이 다시 여러 microservices 비즈니스 프로세스에 걸쳐 있는 경우 결과적 일관성을 사용 해야 의미 합니다. 이 단순한 SQL 조인; 보다 구현 하기가 훨씬 쉽다는 점 마찬가지로, 관계형 데이터베이스의 다른 여러 기능이 사용할 수 없는 여러 microservices 에서입니다.

더 나아가 다른 microservices 자주 사용 하 여 다른 *종류* 데이터베이스. 최신 응용 프로그램 저장소 및 다양 한 종류의 데이터를 프로세스와 관계형 데이터베이스 않습니다 항상 가장 좋습니다. 일부에 대 한 사용 사례, Azure DocumentDB 또는 MongoDB와 같은 NoSQL 데이터베이스는 보다 편리한 데이터 모델 및 성능 향상 및 SQL Server와 같은 SQL 데이터베이스 또는 Azure SQL 데이터베이스 보다 확장성을 제공 합니다. 다른 경우 관계형 데이터베이스는 여전히 가장 좋은 방법입니다. 따라서 microservices 기반 응용 프로그램 자주 사용 하 여 다양 한 SQL 및 NoSQL 데이터베이스 라고도 하는 [polyglot 지 속성](http://martinfowler.com/bliki/PolyglotPersistence.html) 접근 방식입니다.

데이터 저장소에 대 한 분할된 된 polyglot 영구 아키텍처에는 많은 장점이 있습니다. 여기에 느슨하게 연결 된 서비스 및 더 나은 성능, 확장성, 비용 및 관리 효율성 포함 됩니다. 하지만 설명할 것 처럼 분산된 데이터 관리 문제가 발생할 수 있습니다 "[도메인 모델 경계를 식별](#identifying-domain-model-boundaries-for-each-microservice)"를이 참조 합니다.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>Microservices과 컨텍스트 경계가 지정 된 패턴의 관계

마이크로 서비스 개념에서 파생 되는 [경계가 지정 된 컨텍스트 (BC) 패턴](http://martinfowler.com/bliki/BoundedContext.html) 에 [도메인 기반 디자인 (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design)합니다. DDD 여러 BCs는 및 해당 경계에 대 한 명시적 개방형 큰 모델을 다룹니다. 각 BC 자체 모델 및 데이터베이스; 있어야 합니다. 마찬가지로, 각 마이크로 서비스 관련된 데이터를 소유합니다. 또한 일반적으로 각 BC에는 자체 [유비쿼터스 언어](http://martinfowler.com/bliki/UbiquitousLanguage.html) 소프트웨어 개발자와 도메인 전문가 간의 통신에 있도록 합니다.

(즉, 고유 ID 저장소에서 엔터티를 읽는 데 사용 되는) 동일한 id를 공유 하는 다른 경우에 도메인 엔터티를 유비쿼터스 언어에서 용어 (주로 도메인 엔터티) 다른 경계가 지정 된 컨텍스트에서 서로 다른 이름을 가질 수 있습니다. 예를 들어, 컨텍스트에서 사용자 프로필 경계가 지정 된 사용자 도메인 엔터티가 공유할 수 identity 정렬 경계가 지정 된 컨텍스트에서 구매자 도메인 엔터티.

마이크로 서비스를 제한 하는 컨텍스트를 따라서 비슷합니다. 하지만 또한 분산된 서비스 임을 지정 합니다. 각 경계가 지정 된 컨텍스트에 대 한 별도 프로세스로 빌드될 및 HTTP/HTTPS, WebSockets, 같은 앞에서 설명한 것 분산된 프로토콜을 사용 해야 하거나 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)합니다. 그러나 경계가 지정 된 컨텍스트 패턴 지정 하지 않습니다 경계가 지정 된 컨텍스트는 분산된 서비스 되는지 또는 단순히 (예: 제네릭 하위 시스템)는 논리적 경계 경우 모놀리식 배포 응용 프로그램 내에서.

각 경계가 지정 된 컨텍스트에 대 한 서비스를 정의 하려면 먼저 시작할 임을 강조 표시 하는 것이 유용 합니다. 하지만 디자인을 제한할 필요가 없습니다. 경우에 따라 경계가 지정 된 컨텍스트를 디자인 해야 또는 몇 가지 물리적 서비스는 비즈니스 마이크로 서비스를 구성 합니다. 하지만 궁극적으로, 두 패턴-경계가 지정 된 컨텍스트 및 마이크로 서비스-밀접 한 관련이 있습니다.

DDD 분산된 microservices 형식의 실제 경계를 가져와서 microservices에서 활용 합니다. 하지만 microservices 간에 모델을 공유 하지 않고 같은 역할을 하는 또한 수행할 경계가 지정 된 컨텍스트에 있는 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **Chris Richardson 합니다. 패턴: 서비스 당 데이터베이스**
    [*http://microservices.io/patterns/data/database-per-service.html*](http://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*http://martinfowler.com/bliki/BoundedContext.html*](http://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*http://martinfowler.com/bliki/PolyglotPersistence.html*](http://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini 합니다. 전략적 도메인 기반 상황에 맞는 매핑 사용 하 여 디자인**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[이전] (microservices-architecture.md) [다음] (논리적-대-물리적-architecture.md)
