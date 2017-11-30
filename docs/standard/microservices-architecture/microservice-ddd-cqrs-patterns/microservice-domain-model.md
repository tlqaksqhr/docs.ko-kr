---
title: "마이크로 서비스 도메인 모델 디자인"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스 도메인 모델 디자인"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a>마이크로 서비스 도메인 모델 디자인

*각 비즈니스 마이크로 서비스 또는 컨텍스트 제한에 대 한 풍부한 도메인 모델을 정의 합니다.*

여기서의 목표는 각 비즈니스 마이크로 서비스 또는 경계가 지정 된 컨텍스트 (BC)에 대 한 단일 화합 도메인 모델을 만드는 것입니다. 그러나 염두에서에 둬야, 있는 a BC 단일 도메인 모델을 공유 하는 몇 가지 실제 서비스의 비즈니스 마이크로 서비스를 구성 될 경우에 따라 또는 합니다. 도메인 모델 규칙, 동작, 비즈니스 언어 및 단일 경계가 지정 된 컨텍스트 또는 표시 되는 비즈니스 마이크로 서비스의 제약 조건을 캡처해야 합니다.

## <a name="the-domain-entity-pattern"></a>도메인 엔터티 패턴

도메인 개체를 나타내는 엔터티와 주로 의해 정의 id, 연속성 및 시간이 지남에 따라 지 속성을 구성 하는 특성으로 뿐만 아니라 합니다. Eric Evans 라고 표시 하는 대로 "기본적으로 해당 id로 정의 하는 개체를 엔터티 라고 합니다." 이들은 모델에 대 한 기준 엔터티는 도메인 모델에서 매우 중요 합니다. 따라서 식별 하 고 해당 작업을 신중 하 게 디자인 해야 합니다.

*여러 microservices 또는 경계가 지정 된 컨텍스트는 엔터티 id 매개자 수 있습니다.*

동일한 id (경우에 같은 엔터티 하지) 여러 경계가 지정 된 컨텍스트 또는 microservices 모델링할 수 있습니다. 그러나 같은 특성 및 논리를 가진 동일한 엔터티를 제한 하는 여러 상황에서 구현 될 것과이 아닙니다. 대신, 각 경계가 지정 된 컨텍스트에서 엔터티 해당 특성 및 해당 제한 컨텍스트 도메인에 필요한 쿼리에만에 동작을 제한합니다.

예를 들어 구매자 엔터티는 대부분의 사용자 엔터티는 프로필 또는 id 마이크로 서비스를 id를 포함 하 여에 정의 되어 있는 사람의 특성의 있을 수 있습니다. 이지만 특정 buyer 데이터만 주문 프로세스는 관련이 있으므로 정렬 마이크로 서비스에서 구매자 엔터티 더 적은 수의 특성을 가질 수 있습니다. 각 마이크로 서비스의 컨텍스트 또는 제한 된 상황에 맞는 해당 도메인 모델에 영향을 줍니다.

*도메인 엔터티 데이터 특성을 구현 하는 것 외에도 동작을 구현 해야 합니다.*

Ddd에서 도메인 엔터티는 도메인 논리 또는 데이터와 관련 된 엔터티 (메모리에 액세스 하는 개체) 동작을 구현 해야 합니다. 예를 들어 order 엔터티 클래스의 일부로 있어야 비즈니스 논리 및 작업은 주문 항목, 데이터 유효성 검사 및 총 계산을 추가 하는 등 작업에 대 한 메서드로 구현 합니다. 고정 및 이러한 규칙은 응용 프로그램 계층에 분산 하는 대신 엔터티의 규칙의 엔터티 메서드 주의 해야 합니다.

그림 9-8 뿐만 아니라 데이터 특성 하지만 작업 또는 관련된 도메인 논리를 사용 하 여 메서드를 구현 하는 도메인 엔터티를 보여 줍니다.

![](./media/image9.png)

**그림 9-8**합니다. 데이터와 동작을 구현 하는 도메인 엔터티 디자인의 예

물론, 경우에 따라 엔터티 클래스의 일부로 모든 논리를 구현 하지 않는 엔터티를 포함할 수 있습니다. 이 인해 자식 엔터티가 없는 경우 특별 한 논리 집계 루트에 있는 대부분의 논리 정의 되었기 때문에 자식 엔터티 집계 내에서 발생할 수 있습니다. 도메인 엔터티 대신 서비스 클래스에 구현 된 논리가 많이 포함 하는 복잡 한 마이크로 서비스를 사용 하도록 설정한 경우 다음 섹션에 설명 된 anemic 도메인 모델에 속하는 있습니다 수 없습니다.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Anemic 도메인 모델 및 풍부한 도메인 모델

그의 게시물에 [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler이 이렇게 anemic 도메인 모델을 설명 합니다.

언뜻 보기에 같다는 실제 처럼는 하는 기본 증상은 Anemic 도메인 모델입니다. 개체가에 있는 명사 도메인 공간에 따라 명명 된 많은 및 이러한 개체의 풍부한 관계 및 true 도메인 모델에는 구조와 연결 합니다. Catch 실현할 경우에 동작을 보면 이러한 개체에서 동작은 거의 모든 봉투 getter 및 setter에 보다 좀 더 쉽게 제공 됩니다.

물론, anemic 도메인 모델을 사용 하면 이러한 데이터 모델에서에서 사용할 서비스 개체의 집합 (일반적으로 명명 된는 *비즈니스 계층*)를 캡처할 모든 도메인 또는 비즈니스 논리입니다. 비즈니스 계층 데이터 모델 위에 배치 하 고 데이터와 마찬가지로 데이터 모델을 사용 합니다.

Anemic 도메인 모델에는 절차적 스타일 노드 뿐입니다. Anemic 엔터티 개체는 동작 (메서드)를 없기 때문에 실제 개체가 아닙니다. 데이터 속성 이므로 저장 며 따라서 없습니다 개체 지향 디자인 합니다. 서비스 개체 (비즈니스 계층)에 모든 동작을 축소 입력 하 여 기본적으로 /fd [코드](https://en.wikipedia.org/wiki/Spaghetti_code) 또는 [트랜잭션 스크립트](https://martinfowler.com/eaaCatalog/transactionScript.html), 하는 장점의 손실 따라서 도메인 모델 제공합니다.

마이크로 서비스 또는 경계가 지정 된 컨텍스트는 매우 간단 하는 경우 상관 없이 (CRUD 서비스)에 데이터 속성을 사용 하 여 엔터티 개체의 형태로 anemic 도메인 모델이 적당 수 있습니다 및 더 복잡 한 DDD 패턴 구현 가치가 없을 수 있습니다. 이 경우 됩니다 단순히 지 속성 모델 엔터티 CRUD 목적에 대 한 데이터만 의도적으로 만들었기 때문에.

이 microservices 아키텍처는 각 경계가 지정 된 컨텍스트에 따라 다중 아키텍처 방법에 대 한 완벽 한 때문입니다. 예를 들어, eShopOnContainers에서 정렬 마이크로 서비스 DDD 패턴을 구현 합니다. 하지만 간단한 CRUD 서비스 카탈로그 마이크로 서비스 하지 않습니다.

일부 사용자는 안티패턴 anemic 도메인 모델을 말합니다. 실제로 구현 하는 내용에 따라 달라 집니다. 만들려는 마이크로 서비스 이면 단순 충분히 (예를 들어 CRUD 서비스의 경우)는 안티패턴 없으면 anemic 도메인 모델입니다. 그러나 끊임없이 변화 하는 비즈니스 규칙의 많은 마이크로 서비스의 도메인의 복잡성을 해결 해야 하는 경우 anemic 도메인 모델 해당 마이크로 서비스 또는 경계가 지정 된 컨텍스트는 안티패턴 수 있습니다. 이 경우 rich로 디자인 (집계, 개체 등) 추가 DDD 패턴을 구현 뿐만 아니라 데이터 형식과 동작이 포함 된 엔터티를 사용 하 여 모델에는 이러한 마이크로 서비스의 장기적인 성공에 대 한 큰 혜택이 있을 수 있습니다.

#### <a name="additional-resources"></a>추가 리소스

-   **DevIQ 합니다. 도메인 엔터티**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)

-   **Martin Fowler. 도메인 모델**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martin Fowler. Anemic 도메인 모델**

    <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>값 개체 패턴

Eric Evans 듯이 "많은 개체가 않아도 개념적 identity 됩니다. 이 개체를 설명는 작업의 일정 한 특성이 있습니다. "

엔터티 id가 필요 하지만 하지 않는 시스템에 많은 개체가 있는 값 개체 패턴을 선택 합니다. 값 개체는 도메인 측면을 설명 하는 개념 없는 id 가진 개체입니다. 이들은 일시적으로 하면 관련 된 디자인 요소를 나타내기 위해 인스턴스화하는 개체입니다. 중요 한 *어떤* 없는, *가* 됩니다. 예에는 숫자와 문자열을 제외한 특성 그룹의 같은 더 높은 수준의 개념 될 수도 있습니다.

마이크로 서비스의 엔터티를 해당 기능의 아닐 수 있습니다 다른 마이크로 서비스의 엔터티를 두 번째 경우에는 경계가 지정 된 컨텍스트는 다른 의미 있을 수 있으므로. 예를 들어 전자 상거래 응용 프로그램에 있는 주소 없을 수 있습니다는 id, 이후만 개인 또는 회사에 대 한 고객의 프로필의 특성 그룹을 나타낼 수도 있습니다. 이 경우 주소를 값 개체 분류 해야 할 합니다. 그러나 electric 전원 유틸리티 회사에 대 한 응용 프로그램에서는 고객 주소 비즈니스 도메인 중요 수 있습니다. 따라서 주소 주소에 청구 시스템을 직접 연결할 수 있도록 id가 있어야 합니다. 이 경우 주소는 도메인 엔터티로 분류 해야 할 합니다.

이름 및 성을 있는 사용자 엔터티는 일반적으로 사용자 이름 및 성을 다른 값 집합을와 일치 하는 경우에 id를 가진, 때문에 경우와 같이 해당 이름을 의미 하기도 다른 사용자에 게 있습니다.

값 개체는 문서에서 구현 하 고 사용 하 여 쉽게 데이터베이스를 지향 하지만 EF, 같은 Orm 관계형 데이터베이스에서 관리 하기가입니다.

#### <a name="additional-resources"></a>추가 리소스

-   **Martin Fowler. 값 개체 패턴**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **개체를 값**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)

-   **값 기반 개발에서 개체**
    [*https://leanpub.com/tdd-ebook/read\#leanpub 자동-값 개체*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성을 다루는 합니다.** (예약; 값 개체에 설명) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>집계 패턴

도메인 모델에 있는 다른 데이터 엔터티 및 중요 한 영역의 구매나 주문 또는 재고 등의 기능을 제어할 수 있는 프로세스의 클러스터를 포함 합니다. 좀 더 세분화 된 DDD 단위는 클러스터 또는 그룹의 엔터티 및 화합 단위로 처리 될 수 있는 동작을 설명 하는 집계입니다.

일반적으로 필요한 트랜잭션을 기반으로 집계를 정의 합니다. 전형적인 예로 주문 항목 목록이 포함 되는 순서입니다. 주문 항목은 엔터티 일반적으로 됩니다. 하지만 해당 루트 엔터티로 일반적으로 집계 루트 호출 또한 order 엔터티를 포함 하는 순서 집계 내에서 자식 엔터티가 됩니다.

집계를 식별 하는 것은 어려울 수 있습니다. 집계는 서로 일치 해야 하는 개체 그룹에 있지만 방금 개체 그룹을 선택 하 고 집계 레이블을 수 없습니다. 도메인 개념으로 시작 해야 하며 해당 개념과 관련 된 가장 일반적인 트랜잭션에서 사용 되는 엔터티를 고려해 야 합니다. 트랜잭션 측면에서 일치 해야 하는 이러한 엔터티는 집계를 형성 하는 기능입니다. 트랜잭션 작업에 대 한 집계를 식별 하는 가장 좋은 방법은 때문일 수 있습니다.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>집계 루트 또는 루트 엔터티 패턴

집계는 엔터티를 하나 이상 이루어져: 루트 엔터티 또는 기본 ientity 라고도 집계 루트입니다. 또한 여러 개의 자식 엔터티와 모든 엔터티 및 관리자와 함께 필요한 동작 및 트랜잭션을 구현 하는 개체와 함께 값 개체는 있을 수 있습니다.

집계 루트의 목적은; 집계의 일관성을 유지 하는 것 메서드를 통해 집계에 대 한 업데이트에 대 한 유일한 진입점 것 또는 작업 집계 루트 클래스입니다. 집계 루트를 통해서만 집계 내에서 엔터티를 변경 해야 합니다. 것이 집계의 일관성 보호자, 모든 고정 및 사용자 집계에 준수 해야 할 수 있습니다 일관성 규칙을 고려 합니다. 자식 엔터티 또는 값 개체를 독립적으로 변경 하면 집계 루트 집계가 유효한 상태 인지를 보장할 수 없습니다. 느슨한 레그 있는 테이블 처럼 됩니다. 유지 관리 일관성은 집계 루트의 주요 목적은입니다.

그림 9-9에서 단일 엔터티 (집계 루트 구매자)를 포함 하는 집계, 구매자와 같은 샘플 집계를 볼 수 있습니다. 순서 집계는 여러 엔터티 및 값 개체를 포함합니다.

![](./media/image10.png)

**그림 9-9**합니다. 여러 집계 예제 또는 단일 엔터티

구매자 집계 분야에 따라 추가 자식 엔터티를 가질 수 있는지와 eShopOnContainers 참조 응용 프로그램에서 주문 마이크로 서비스에서 note 합니다. 그림 9-9는 방금 구매자의 집계는 집계 루트에만 포함 된 예를 들어 하나의 항목에 지정 된 사례를 보여 줍니다.

집계의 분리를 유지 관리 하 고 간에 명확한 경계를 유지 하기 위해는 것이 좋습니다에서 구현 될 때 집계 및 외래 키 (FK) 필드를 것만 간의 직접 탐색을 허용 하지 않도록 DDD 도메인 모델에 [ 마이크로 서비스 도메인 모델 순서](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) eShopOnContainers에 있습니다. Order 엔터티만에 외래 키 필드는 구매자 하지만 하지는 EF 코어 탐색 속성에 대 한 다음 코드에 나와 있는 것 처럼:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

식별 하 고 집계 작업 연구와 경험 필요 합니다. 자세한 내용은 다음과를 같은 추가 리소스를 참조 하십시오.

#### <a name="additional-resources"></a>추가 리소스

-   **Vaughn Vernon. 1 부: 효율적인 집계 디자인-단일 집계를 모델링**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_커뮤니티\_세이\_ 집계\_부분\_1. pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon. 효율적인 집계 디자인-2 부: 만들기 집계 작업 함께**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*

-   **Vaughn Vernon. 효율적인 집계 디자인-3 부: 검색을 통해 정보를 얻고**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*

-   **Sergey Grybniak 합니다. DDD 전술적 디자인 패턴**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Richardson 합니다. 집계를 사용 하 여 트랜잭션 Microservices 개발**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ 합니다. 집계 패턴**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)


>[!div class="step-by-step"]
[이전] (ddd-지향-microservice.md) [다음] (net-코어-마이크로 서비스-도메인-model.md)
