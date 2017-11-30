---
title: "지 속성 계층 인프라를 디자인합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 지 속성 계층 인프라를 디자인합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a>지 속성 계층 인프라를 디자인합니다.

데이터 지 속성 구성 요소는 마이크로 서비스 (즉, 마이크로 서비스의 데이터베이스)의 경계 내에서 호스팅되는 데이터에 대 한 액세스를 제공 합니다. 실제 구현은 저장소 등의 구성 요소로 포함 및 [작업 단위](http://martinfowler.com/eaaCatalog/unitOfWork.html) 사용자 지정 EF DBContexts 같은 클래스.

## <a name="the-repository-pattern"></a>리포지토리 패턴

저장소는 클래스 또는 데이터 원본에 액세스 하는 데 필요한 논리를 캡슐화 하는 구성 요소. 이러한 공통 데이터 액세스 기능을 유지 관리 작업이 편리를 제공 하 고 인프라 또는 도메인 모델 계층에서 데이터베이스에 액세스 하는 데 사용 되는 기술 분리 중앙 집중화 합니다. Entity Framework와 같은 ORM을 사용 하면 LINQ 및 강력한 형식 지정 덕분에 구현 해야 하는 코드 간소화 됩니다. 이 데이터 보다 데이터 지 속성 논리에 집중할 수 있도록 내부 작업에 액세스 합니다.

저장소 패턴은 데이터 원본으로 작업의 자세한 설명이 포함된 하는 방법. 책에 [엔터프라이즈 응용 프로그램 아키텍처 패턴](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler 다음과 같이 저장소를 설명 합니다.

저장소는 중간자 도메인 모델 계층 및 데이터 매핑 비슷한 방식으로 메모리에 대 한 도메인 개체의 집합에 속하는 작업을 수행 합니다. 선언적으로 클라이언트 개체 쿼리를 작성 하 대답에 대 한 저장소로 보내야 합니다. 개념적으로, 저장소 데이터베이스 및 지 속성 계층에 가까운 방법을 제공 하 여 수행할 수 있는 작업에 저장 된 개체의 집합을 캡슐화 합니다. 버전 저장소는 또한 명확 하 고 한 방향으로 작업 도메인 및 데이터 할당 간 종속성 구분 기호 또는 매핑을의 목적을 지원 합니다.

### <a name="define-one-repository-per-aggregate"></a>집계 마다 리포지토리가 한 개를 정의 합니다.

각 집계 또는 집계 루트에 대 한 하나의 저장소 클래스를 만들어야 합니다. 도메인 기반 디자인 패턴을 기반으로 하는 마이크로 서비스를 사용 하 여 데이터베이스를 업데이트 해야 하는 유일한 채널 리포지토리 되어야 합니다. 즉, 집계의 고정 항목과 트랜잭션 일관성을 제어 하는 집계 루트와 일대일 관계를 갖습니다. 통해 다른 데이터베이스를 쿼리할 수 채널 (CQRS 방법은 다음을 수행할 수 있습니다)으로, 쿼리 데이터베이스의 상태는 변경 되지 않습니다. 그러나 트랜잭션 영역-업데이트-저장소 및 집계 루트에 의해 제어 항상 해야 합니다.

기본적으로, 저장소 도메인 엔터티의 형태로 데이터베이스에서 제공 되는 메모리의 데이터를 채울 수 있습니다. 엔터티를 메모리에 있는, 변경 하 고 수 트랜잭션을 통해 데이터베이스에 다시 적용 합니다.

앞에서 설명한 대로, CQS/CQRS 아키텍처 패턴을 사용 하는 경우 초기 쿼리 Dapper를 사용 하 여 간단한 SQL 문을 수행한 도메인 모델에서 쪽 쿼리에 의해 수행 됩니다. 이 방법은 해야 쿼리 하 고 모든 테이블을 조인할 수 있으므로 저장소 보다 유연 하 고 이러한 쿼리는의 제한을 받지 규칙에 따라 집계에서 훨씬 더 합니다. 해당 데이터 프레젠테이션 계층 또는 클라이언트 응용 프로그램으로 이동 합니다.

사용자를 변경 하면 경우에 응용 프로그램 계층 (예: 웹 API 서비스)에 데이터를 업데이트할 수는 클라이언트 응용 프로그램 또는 프레젠테이션 계층에서 제공 됩니다. 명령 처리기에는 명령 (데이터)를 받으면 데이터베이스에서 업데이트할 데이터를 가져올 저장소를 사용 합니다. 명령을 전달 되는 정보를 메모리에 업데이트 하 고을 추가 하거나 (도메인 엔터티) 트랜잭션을 통해 데이터베이스의 데이터를 업데이트 합니다.

해야 내용을 강조 다시는 그림 9-17과 같이 각 집계 루트에 대해 하나의 저장소를 정의 해야 합니다. 집계 내 모든 개체 간에 트랜잭션 일관성을 유지 하기 위해 집계 루트의 목표를 달성 하기를 만들지 마십시오 각 테이블에 대 한 저장소 데이터베이스에 있습니다.

![](./media/image18.png)

**그림 9-17**합니다. 저장소, 집계 및 데이터베이스 테이블 간의 관계

### <a name="enforcing-one-aggregate-root-per-repository"></a>저장소당 하나의 집계 루트를 적용합니다.

만 집계 루트 저장소에 있어야 하는 규칙을 적용 하는 방식으로 저장소 디자인을 구현 하려면 유용할 수 있습니다. IAggregateRoot 표시 인터페이스 갖도록와 함께 작동 하는 엔터티 형식을 제한 하는 제네릭 또는 기본 저장소 유형을 만들 수 있습니다.

따라서 각 저장소 인프라 계층에서 구현 또는 구현 하는 자체 계약 인터페이스를 다음 코드에 나와 있는 것 처럼:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

각 특정 리포지토리 인터페이스 제네릭 IRepository 인터페이스를 구현합니다.

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

그러나 하는 규칙을 적용 하는 코드에 더 좋은 방법은 명시적 특정 집계를 대상으로 하는 데 저장소를 사용 하는 일반 저장소 유형을 구현 하는 것 단일 집계를 각 저장소는 관련 되어야 합니다. 하는 다음 코드 에서처럼 IRepository 기본 인터페이스에서 해당 제네릭을 구현 하 여 쉽게 설정할 수 있습니다.

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>리포지토리 패턴을 사용 하면 쉽게 응용 프로그램 논리를 테스트 하려면

리포지토리 패턴을 사용 하면 단위 테스트 응용 프로그램을 쉽게 테스트할 수 있습니다. 단위 테스트만 테스트 코드, 인프라가 아니라 때문에 저장소 추상화 쉽게 이러한 작업을 수행 해야 합니다.

이전 단원에서 설명 했 듯이 것이 좋습니다 정의 하 고 배치 리포지토리 인터페이스 도메인 모델 계층에서 응용 프로그램 계층 (사용자 웹 API 마이크로 서비스 예를 들어,) 인프라 계층 직접에 종속 되지 않아야 하므로 있는 경우 실제 저장소 클래스를 구현 합니다. 이 작업을 수행 하 고 Web API 컨트롤러의 종속성 주입을 사용 하 여 데이터베이스에서 데이터 대신 가짜 데이터를 반환 하는 모의 리포지토리를 구현할 수 있습니다. 분리 된 접근 방식을 통해 만들 수 있습니다 및 실행된 단위 테스트는 데이터베이스에 연결 하지 않고도 응용 프로그램 논리를 테스트할 수입니다.

데이터베이스에 대 한 연결이 실패할 수 하며, 무엇 보다도 데이터베이스에 대해 수백 번의 테스트를 실행 합니다. 잘못 된 두 가지 이유로 합니다. 먼저, 테스트 수가 많은 때문에 시간이 많이 걸릴 수 있습니다. 둘째, 데이터베이스 레코드 변경 하 고 일관 되지 않을 수도 있습니다 수 있도록 테스트, 결과 영향을 줄 수 있습니다. 데이터베이스에 대해 테스트가 단위 테스트 하지만 통합 테스트 하지 않습니다. 많은 단위 테스트를 신속 하 고 실행 해야 하지만 더 적은 통합 데이터베이스에 대해 테스트 합니다.

단위 테스트에 대 한 문제의 분리, 측면에서 논리에는 메모리의 엔터티를 도메인에서 작동합니다. 저장소 클래스가 전달한 것을 가정 합니다. 도메인 엔터티를 수정 하는 논리 되 면 저장소 클래스 올바르게 저장할 됩니다 가정 합니다. 여기서 중요 한 점은 도메인 모델 및 해당 도메인 논리에 대 한 단위 테스트를 만드는 것입니다. 집계 루트는 ddd에서 주 일관성 경계입니다.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>리포지토리 패턴 및 레거시 데이터 액세스 클래스 (DAL 클래스) 패턴의 차이

데이터 액세스 개체는 직접 데이터 액세스 및 지 속성 저장소에 대 한 작업을 수행합니다. 작업 개체 (예: EF DbContext를 사용 하는 경우), 하지만 이러한 업데이트는 단위의 메모리에서 수행 하려는 작업을 사용 하 여 데이터를 즉시 수행 하지 것입니다. 리포지토리 표시 합니다.

작업의 단위를 단일 트랜잭션으로 여러 insert와 관련 된 업데이트 또는 삭제 작업 이라고 합니다. 간단히 말해서에서는 특정 사용자 동작 (예를 들어 웹 사이트에서 등록)에 대 한 모든 삽입, 업데이트 및 삭제 트랜잭션이 처리 단일 트랜잭션에서 의미 합니다. 이것이 chattier 방식으로 여러 데이터베이스 트랜잭션 처리 보다 더 효율적입니다.

이 코드는 응용 프로그램 계층에서 명령 시 이러한 여러 지 속성 작업에서는 단일 작업에서 나중에 수행 됩니다. 에 따라 일반적으로 실제 데이터베이스 저장소에 메모리에 변경 내용을 적용 하는 방법에 대 한 결정은 [작업 단위로 패턴](http://martinfowler.com/eaaCatalog/unitOfWork.html)합니다. EF, 작업 단위로 패턴으로 DBContext 구현 됩니다.

대부분의 경우에서이 패턴 또는 저장소에 대 한 작업을 적용 한 방식으로 응용 프로그램 성능을 향상 하 고 불일치 가능성을 줄일 수 있습니다. 또한, 의도 된 모든 작업은 한 트랜잭션으로의 일부로 커밋할 때문에 트랜잭션 데이터베이스 테이블에 차단 줄어듭니다. 이 데이터베이스에 대해 많은 격리 된 작업 실행에 비해 더 효율적입니다. 따라서 선택한 ORM 많은 소형 및 별도 트랜잭션 실행 하는 대신 동일한 트랜잭션 내에서 여러 가지 업데이트 작업을 그룹화 하 여 데이터베이스에 대해 실행을 최적화할 수 됩니다.

### <a name="repositories-should-not-be-mandatory"></a>저장소를 필수적 이어야 합니다.

사용자 지정 저장소는 앞에서 언급 된 이유로 유용 있고 eShopOnContainers에 정렬 마이크로 서비스에 대 한 접근 방식입니다. 그러나 DDD 디자인에서 구현 하거나 일반적에.NET에서 개발 하는 필수 패턴 않습니다.

예를 들어, Jimmy Bogard이이 가이드에 대 한 직접적인 피드백을 제공 하는 경우 다음 말합니다.

이 가장 큰 의견 되었을 수 있습니다. 실제로 하지 않겠습니다 리포지토리의 팬 기본 지 속성 메커니즘의 중요 한 세부 정보를 숨기려면 기능이 있기 때문에 있습니다. 그 이유를 얻을 수 MediatR 명령에 대 한 너무 합니다. 지 속성 계층의 모든 기능을 사용할 수 있으며 모든 도메인 동작 내 집계 루트에 밀어 I. 내 저장소의 모의 알림 않으려는 일반적으로 – 여전히 해당 통합에 필요한 실제 항목을 사용 하 여 테스트 합니다. CQRS 라인으로 전환 하지 않은 실제로 있는지 저장소에 대 한 요구가 더 이상 사용 됩니다.

저장소 유용 하 게 알 승인할 우리는 프로그램 DDD, 집계 패턴 및 풍부한 도메인 모델은 하는 방식에 중요 하지 않습니다. 따라서 리포지토리 패턴 사용할지, 나와 있는 것 처럼 적합 합니다.

#### <a name="additional-resources"></a>추가 리소스

##### <a name="the-repository-pattern"></a>리포지토리 패턴

-   **Edward Hieatt 및 Rob me입니다. 리포지토리 패턴입니다. ** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)

-   **리포지토리 패턴**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)

-   **리포지토리 패턴: 데이터 지 속성 추상화**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)

-   **Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성을 다루는 합니다.** (예약; 리포지토리 패턴에 대 한 설명이 포함) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

##### <a name="unit-of-work-pattern"></a>작업 패턴의 단위

-   **Martin Fowler. 단위 작업 패턴입니다. ** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)

<!-- -->

-   **ASP.NET MVC 응용 프로그램에서 저장소 및 단위 작업 패턴의 구현은**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)


>[!div class="step-by-step"]
[이전] (도메인-이벤트-디자인-implementation.md) [다음] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
