---
title: "문제 및 분산된 데이터 관리를 위한 솔루션"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 문제 및 분산된 데이터 관리를 위한 솔루션"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f961475b40c74bf448cff1aeae04ae4866360e52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>문제 및 분산된 데이터 관리를 위한 솔루션

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>챌린지 \#1: 각 마이크로 서비스의 경계를 정의 하는 방법

모든 사용자가 발견 한 첫 번째 인증 되었을 마이크로 서비스 경계를 정의 합니다. 각 마이크로 서비스 응용 프로그램의 일부일 수 있으며 각 마이크로 서비스 이점과 있는 과제와 자치 이어야 합니다. 하지만 이러한 경계를 어떻게 알아볼 수 있을까요?

첫째, 응용 프로그램의 논리 도메인 모델 및 관련된 데이터에 집중 해야 합니다. 데이터와 같은 응용 프로그램의 다양 한 상황의 분리 된 제도 식별 하려고 합니다. 컨텍스트마다 다른 비즈니스 언어 (다양 한 비즈니스 용어) 있을 수 있습니다. 컨텍스트를 정의 하 고 독립적으로 관리 해야 합니다. 용어와 이러한 다양 한 컨텍스트에서 사용 되는 엔터티 수와 마찬가지로 사운드 하지만 특정 컨텍스트에서 있는 다른 컨텍스트에서 다른 용도로 하나가 지정 된 비즈니스 개념이 사용 됩니다 발견할 수 하 고 다른 이름이 될 수 있습니다. 예를 들어, 사용자 id 또는 멤버 자격 컨텍스트에서 사용자로 정렬 컨텍스트에서 구매자 CRM 컨텍스트에서 인 고객으로 참조할 수 등.

컨텍스트마다 정확 하 게 식별 하는 방법 수 각 비즈니스 마이크로 서비스 및 관련 된에 대 한 경계에 대해 다른 도메인의 여러 응용 프로그램 컨텍스트 간에 경계를 식별 하는 방법은 도메인 모델 및 데이터입니다. 항상 이러한 microservices 간의 결합을 최소화 하려고 합니다. 이 가이드의 섹션에서이 식별 및 도메인 모델 디자인에 대 한 자세한 내용으로 이어집니다 [각 마이크로 서비스에 대 한 도메인 모델 경계를 식별](#identifying-domain-model-boundaries-for-each-microservice) 나중입니다.

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>챌린지 \#2: 여러 microservices에서 데이터를 검색 하는 쿼리를 만드는 방법

두 번째 문제는 원격 클라이언트 응용 프로그램에서 통신이 자주는 microservices를 방지 하는 동안 여러 microservices에서 데이터를 검색 하는 쿼리를 구현 하는 방법입니다. 예를 바구니, 카탈로그 및 identity microservices 사용자가 소유 하는 사용자 정보를 표시 하는 모바일 앱에서 단일 화면 수 있습니다. 또 다른 예로 여러 microservices에 있는 여러 테이블을 포함 하는 복잡 한 보고서는 것입니다. 적합 한 솔루션은 한 엔터티의 복잡성에 따라 달라 집니다. 하지만 어떤 경우 든, 시스템의 통신에서 효율성을 개선 하려면 정보를 집계 하는 방법을 해야 합니다. 가장 인기 있는 솔루션에는 다음과 같습니다.

**API 게이트웨이**합니다. 서로 다른 데이터베이스를 소유 하는 여러 microservices에서 단순 데이터 집계를 위한 API 게이트웨이 라고 하는 집계 마이크로 서비스는 방법이 권장된 합니다. 그러나 시스템 좁게 지점이 될 수 있습니다 및 마이크로 서비스 자치의 원칙을 위반 하 게 수 때문에이 패턴을 구현 하는 방법에 대 한 주의를 기울여야 할 수도 있습니다. 이러한 가능성을 줄이려면 여러 정교한 API 게이트웨이 "조각 이었습니다" 세로 또는 시스템의 비즈니스 영역에 하나의 집중 각 있을 수 있습니다. API 게이트웨이 패턴 사용의 섹션에서 자세히 설명 되어 나중에 프로그램 API 게이트웨이 합니다.

**쿼리/reads 테이블 CQRS**합니다. 여러 microservices에서 데이터를 집계 하기 위한 다른 방법은 [구체화 된 뷰 패턴](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)합니다. 이 방법에서는 생성 하면 미리 (실제 쿼리의 발생 전에 비 정규화 된 데이터 준비), 여러 microservices가 소유 하는 데이터와 읽기 전용 테이블입니다. 테이블에는 형식으로 클라이언트 응용 프로그램의 요구에 부합 합니다.

모바일 앱에 대 한 화면와 같은 것이 좋습니다. 단일 데이터베이스를 설정한 경우 있습니다 수 모아 여러 테이블을 포함 하는 복잡 한 조인을 수행 하는 SQL 쿼리를 사용 하 여 해당 화면에 대 한 데이터입니다. 그러나 여러 데이터베이스 있고 각 데이터베이스는 다른 마이크로 서비스를 소유한 경우 해당 데이터베이스를 쿼리할 수 없으며 SQL 조인을 만듭니다. 복잡 한 쿼리는 것이 어려울 수 있습니다. CQRS 접근 방식을 사용 하는 요구 사항을 해결할 수 있습니다-쿼리에 대해서만 사용 되는 다른 데이터베이스에 정규화 되지 않은 테이블을 만듭니다. 특히 복잡 한 쿼리를 응용 프로그램의 화면 및 쿼리 테이블의 열에 필요한 필드 간의 한 일 관계에 필요한 데이터에 대 한 테이블을 디자인할 수 있습니다. 보고 목적으로 사용 될 수도 수 있습니다.

이 방법은 뿐만 아니라 (쿼리 및 microservices 간에 조인 하는 방법); 원래 문제를 해결 쿼리 테이블에는 응용 프로그램에서 필요로 하는 데이터에 이미 있기 때문에 훨씬 복잡 한 조인와 비교 했을 때 성능이 향상 됩니다. 물론, 명령 및 쿼리 책임 분리 CQRS ()를 사용 하 여 쿼리/reads 테이블이 포함 된 추가 개발 작업을 의미 하 고 결과적 일관성을 수용 해야 합니다. 그럼에도 불구 하 고 성능 및 확장성에 대 한 요구 사항을 [공동 작업 시나리오](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/) (또는 관점에 따라 경쟁 시나리오)가 있는 여러 데이터베이스가 있는 CQRS를 적용 해야 합니다.

**"콜드" 데이터베이스의에서 데이터를 중앙**합니다. 복잡 한 보고서 및 실시간 데이터는 필요 하지 않을 수도 있는 쿼리를 실행 하는 것에 대 한 일반적인 방법은 내보낼 프로그램 "핫 데이터" (트랜잭션 데이터는 microservices에서) 보고에 사용 되는 대형 데이터베이스에 "콜드 데이터"로 합니다. 해당 중앙 데이터베이스 시스템 빅 데이터 기반 시스템에서 Hadoop, Azure SQL 데이터 웨어하우스 또는 심지어 단일 SQL 데이터베이스 (크기 문제가 되지 것입니다) 하는 경우 보고서에 대 한 사용에 따라 같은 데이터 웨어하우스 같이 될 수 있습니다.

쿼리 및 실시간 데이터는 필요 하지 않는 보고서에 대해서만이 중앙 집중식된 데이터베이스를 사용할 수는 염두에서에 둬야 합니다. 원래 업데이트 및 사실의 원본으로 트랜잭션을 microservices 데이터에서 되어야 할입니다. 데이터를 동기화 하는 방법은 (다음 섹션에 포함 됨) 하는 이벤트 기반 통신을 사용 하거나 다른 데이터베이스 인프라 가져오기/내보내기 도구를 사용 하 여 것입니다. 이벤트 기반 통신을 사용 하는 경우 해당 통합 프로세스 CQRS 쿼리 테이블에 대 한 앞에서 설명한 대로 데이터를 전파 하는 방법에 유사 합니다.

그러나 응용 프로그램 디자인에서 여러 microservices 복잡 한 쿼리에 대 한 정보를 지속적으로 집계 있을 경우 잘못 된 디자인의 증상 수 있습니다-는 마이크로 서비스를 다른 microservices에서 최대한으로 격리 되어야 합니다. (보고서/분석 항상 콜드 데이터 중앙 데이터베이스를 사용 해야 하는 제외 합니다.) 이 문제가 자주 발생 microservices 병합 하는 이유를 수 있습니다. 진화 자율성 및 강력한 종속성, 응집력, 데이터 집계와 각 마이크로 서비스의 배포 균형을 유지 해야 합니다.

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>챌린지 \#3: 여러 microservices 간에 일관성을 위해 하는 방법

앞서 설명한 것 처럼 각 마이크로 서비스를 소유한 데이터는 해당 마이크로 서비스에 전용 포트 이며 해당 마이크로 서비스 API를 사용 하 여 액세스할 수만 있습니다. 따라서 표시 되는 것이 어려울은 여러 microservices 간에 일관성을 유지 하면서 종단 간 비즈니스 프로세스를 구현 하는 방법.

이 문제를 분석 하려면 살펴보겠습니다의 한 예는 [eShopOnContainers 응용 프로그램 참조](http://aka.ms/eshoponcontainers)합니다. 카탈로그 마이크로 서비스 스톡 수준별로 포함 하 여 모든 제품에 대 한 정보를 유지 관리 합니다. Ordering 마이크로 서비스 주문을 관리 하 고 새 주문을 사용 가능한 카탈로그 제품 재고를 초과 하지 않는 확인 해야 합니다. 또는 시나리오 미처리 제품을 처리 하는 논리를 수행할 수 있습니다. 이 응용 프로그램의 가상 모놀리식 버전에서는 정렬 하위 시스템 수을 사용 하 여 트랜잭션의 ACID 트랜잭션의 재고를 확인 순서 Orders 테이블에서 만들고 Products 테이블의 재고를 업데이트 합니다.

그러나 microservices 기반 응용 프로그램에서는 주문 및 제품 테이블의 각 microservices에 의해 소유 됩니다. 적이 없는 마이크로 서비스는 그림 4-9와 같이 데이터베이스의 자체 트랜잭션을 또는 쿼리를 다른 마이크로 서비스를 소유한을 포함 해야 합니다.

![](./media/image9.PNG)

**그림 4-9**합니다. 마이크로 서비스는 다른 마이크로 서비스의 테이블에 직접 액세스할 수 없습니다.

Products 테이블 카탈로그 마이크로 서비스에서 소유 있으므로 Ordering 마이크로 서비스 Products 테이블을 직접 업데이트 하지 해야 합니다. 카탈로그 마이크로 서비스를 업데이트 하려면 Ordering 마이크로 서비스 통합 이벤트 (메시지 및 이벤트 기반 통신)와 같은 비동기 통신을만 사용 해야 합니다. 이것은 방법을 [eShopOnContainers](http://aka.ms/eshoponcontainers) 참조 응용 프로그램이이 유형의 업데이트를 수행 합니다.

에 명시 된 대로 [CAP 정리](https://en.wikipedia.org/wiki/CAP_theorem), 가용성 및 ACID 강력한 일관성 중 하나를 선택 해야 합니다. 마이크로 서비스 기반 시나리오의 대부분에 강력한 일관성 달리 높은 확장성 및 가용성 요구합니다. 중요 응용 프로그램 위로 유지 되 고 실행 중 이며 개발자는 작업 약하거나 최종 일관성을 위한 기술을 사용 하 여 강력한 일관성 하지 않을 수 있습니다. 이것이 대부분 마이크로 서비스 기반 아키텍처에서 사용 하는 접근 방식입니다.

또한 ACID 스타일 또는 2 단계 커밋 트랜잭션이 없는 microservices 원칙; 대상으로 한 대부분의 NoSQL 데이터베이스 (예: Azure Cosmos DB, MongoDB, 등)는 2 단계 커밋 트랜잭션을 지원 하지 않습니다. 그러나 데이터는 그대로 유지 서비스 및 데이터베이스 간 일관성 반드시 필요 합니다. 이러한 문제는 특정 데이터 중복을 해야 할 때 여러 microservices 변경 내용을 전파 하는 방법에 대 한 질문도 관련이-제품의 이름 또는 설명을 카탈로그 마이크로 서비스 및 바구니 해야 경우 예를 들어 마이크로 서비스입니다.

이 문제에 대 한 적합 한 솔루션 간의 이벤트 기반 통신, 게시 및 구독 시스템을 통해 명시 microservices 결과적 일관성을 사용 하는 것입니다. 섹션에서 다루는 이러한 항목은 [이벤트 구동 비동기 통신](#async_event_driven_communication) 이 가이드의 뒷부분에 나오는 합니다.

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>챌린지 \#4: 마이크로 서비스 경계 간에 통신을 디자인 하는 방법

마이크로 서비스 간에 통신 경계는 실제 하기가 어렵습니다. 이 컨텍스트에서 통신을 참조 하지 않습니다 (HTTP 및 나머지 부분에서는 AMQP, 메시징 및 등)를 사용 해야 하면 프로토콜입니다. 대신, 어떤 통신 스타일을 사용 해야 하며 특히 결합 된 방식을 프로그램 microservices 해야 해결 합니다. 결합 수준에 따라 오류가 발생할 경우 시스템에서 해당 오류의 영향이 달라 집니다 크게.

microservices 기반 응용 프로그램을 이동 하는 여러 아티팩트 및 여러 서버 또는 호스트에 걸쳐 분산된 된 서비스와 같은 분산된 시스템에서 구성 요소 결국 실패 합니다. 부분 실패 및 이상이 중단 고려 위험 일반적인 이러한 유형의 분산된 시스템 간에 프로그램 microservices와의 통신을 디자인 해야 하므로 발생 합니다.

HTTP (REST)를 구현 하는 인기 있는 방법입니다-그 단순 함으로 인해 microservices를 기반으로 합니다. HTTP 기반 접근 방법은; 완벽 하 게 허용 됩니다. 이 경우 문제는 사용 하는 방법을 관련이 있습니다. API 게이트웨이 또는 클라이언트 응용 프로그램에서 프로그램 microservices와 상호 작용에 HTTP 요청 및 응답을 사용 하는 문제가 없습니다. 하지만 microservices에서 HTTP에 대 한 동기 호출은 긴 체인을 만들 경우 해당 경계에 걸쳐 통신 하는 microservices 개체 모놀리식 응용 프로그램에서는 마치 처럼 응용 프로그램이 결국 실행 문제를 합니다.

예를 들어, 클라이언트 응용 프로그램가 Ordering 마이크로 서비스와 같은 마이크로 개별 서비스에 대 한 HTTP API 호출 한다고 가정해 보세요. Ordering 마이크로 서비스 호출 하 여 추가 microservices 동일한 요청/응답 내에서 HTTP를 사용 하 여 순환, HTTP 호출 체인을 만드는 합니다. 수 나요 합리적인 처음 합니다. 그러나이 경로 중지 될 때 고려해 야 할 중요 한 사항이 있습니다.

-   차단 및 낮은 성능입니다. 동기 HTTP 특성상 내부 HTTP 호출을 모두 완료 될 때까지 답변해를 원래 요청이 드립니다. 이러한 호출 수가 크게 향상 동시는 마이크로 서비스를 호출 하는 중간 HTTP 중 하나에 차단 된 경우 한다고 가정 합니다. 결과는 성능이 저하 되어 및 추가 HTTP 요청 증가으로 전반적인 확장성 기하급수적 영향입니다.

-   Microservices HTTP 연결입니다. 비즈니스 microservices 다른 비즈니스 microservices와 연결 해서는 안됩니다. 이상적으로 이러한 하지 ""에 대해 알아야 다른 microservices 존재 합니다. 응용 프로그램 예제와 같이 microservices 결합을 사용 하는 경우 마이크로 서비스 당 자치를 달성 됩니다 하지 거의 불가능 합니다.

-   모든 하나의 마이크로 서비스 오류가 발생 했습니다. microservices 중 하나라도 (및 실패 결국 합니다) microservices의 전체 체인 때 HTTP 호출에 의해 연결 된 microservices의 체인을 구현 하는 경우 실패 합니다. 마이크로 서비스 기반 시스템 부분 실패 하는 동안 가능한 뿐만 아니라 작업을 계속 하려면 설계 되어야 합니다. 지 수 백오프 또는 회로 차단기 메커니즘에 다시 시도 횟수를 사용 하는 클라이언트 논리를 구현 하는 경우에 더 복잡 한 HTTP 호출 체인은 HTTP 기반 오류 전략을 구현 하는 것 보다 복잡 한입니다.

사실, 내부 microservices에 설명 된 대로 체인의 HTTP 요청을 만들어와 통신 하는 경우 주장할 intraprocess 통신 메커니즘 대신 프로세스 간 HTTP 기반 하나만 제외 하 고 모놀리식 응용 프로그램이 있다고 합니다.

따라서 자율성 마이크로 서비스를 강제 적용 하 고 더 나은 복원 력 있는 microservices에서 체인의 요청/응답 통신의 사용을 최소화 해야 있습니다. 비동기 메시지 및 이벤트 기반 통신을 사용 하 여 나 HTTP 폴링 원래 HTTP 요청/응답 주기와 별도로 사용 하 여 마이크로 서비스 간 통신에 대 한 비동기만 상호 작용을 사용 하는 것이 좋습니다.

비동기 통신을 사용 하는 섹션에이 가이드의 뒷부분에 나오는 추가 세부 정보와 함께 설명 [비동기 마이크로 서비스 마이크로 서비스의 자치 성을 적용](#asynchronous-microservice-integration-enforce-microservices-autonomy) 및 [비동기 메시지 기반 통신](#asynchronous-message-based-communication)합니다.

## <a name="additional-resources"></a>추가 리소스

-   **단면 정리**
    [*https://en.wikipedia.org/wiki/CAP\_정리*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **결과적 일관성**
    [*https://en.wikipedia.org/wiki/Eventual\_일관성*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **데이터 일관성 입문**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)

-   **Martin Fowler. CQRS (명령 및 쿼리 책임 분리)**
    [*http://martinfowler.com/bliki/CQRS.html*](http://martinfowler.com/bliki/CQRS.html)

-   **뷰를 구체화**
    [*https://docs.microsoft.com/azure/architecture/patterns/materialized-view*](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

-   **Charles 행입니다. ACID vs입니다. 기준: 데이터베이스 트랜잭션 처리의 Shifting pH**
    [*http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/*](http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/)

-   **트랜잭션을 보정**
    [*https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction*](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

-   **Udi Dahan 합니다. 서비스 지향 컴퍼지션**
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)


>[!div class="step-by-step"]
[이전] (논리적-대-물리적-architecture.md) [다음] (식별-마이크로 서비스-도메인-모델-boundaries.md)
