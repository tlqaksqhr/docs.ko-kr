---
title: "DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: d81091bf09d690f5d57ad9a30b5f16de1358ede6
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리

*비즈니스 도메인에 대한 이해를 반영하는 각 마이크로 서비스 또는 제한된 컨텍스트를 위한 도메인 모델을 디자인하세요.*

이 섹션에서는 복잡한 하위 시스템 또는 끊임없이 변화하는 비즈니스 규칙을 사용하는 도메인 전문가의 지식에서 파생된 마이크로 서비스를 처리해야 할 때 구현하는 고급 마이크로 서비스에 중점을 둡니다. 이 섹션에 사용된 아키텍처 패턴은 그림 9-1에 나와 있는 것처럼 DDD(도메인 기반 디자인) 및 CQRS(Command and Query Responsibility Segregation) 접근 방식을 기반으로 합니다.

![](./media/image1.png)

**그림 9-1**. 각 마이크로 서비스에 대한 외부 마이크로 서비스 아키텍처 및 내부 아키텍처 패턴

그러나 ASP.NET Core Web API 서비스를 구현하는 방법 또는 Swashbuckle을 사용하여 Swagger 메타데이터를 표시하는 방법과 같은 대부분의 데이터 기반 마이크로 서비스 기술은 DDD 패턴을 사용하여 내부적으로 구현된 고급 마이크로 서비스에도 적용할 수 있습니다. 이 섹션은 이전 섹션의 확장입니다. 이전에 설명한 대부분의 방법이 여기 또는 모든 종류의 마이크로 서비스에도 적용되기 때문입니다.

이 섹션에서는 먼저 eShopOnContainers 참조 응용 프로그램에 사용되는 간소화된 CQRS 패턴에 대한 세부 정보를 제공합니다. 이후에는 응용 프로그램에서 다시 사용할 수 있는 일반적인 패턴을 찾을 수 있도록 지원하는 DDD 기술에 대해 간략히 설명합니다.

DDD는 다양한 학습 리소스 집합이 있는 큰 주제입니다. Eric Evans의 [Domain-Driven Design](https://domainlanguage.com/ddd/)과 같은 서적 및 Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard와 그 밖의 여러 DDD/CQRS 전문가의 추가 자료로 시작할 수 있습니다. 그러나 무엇보다도 구체적인 비즈니스 도메인 전문가와 함께 하는 대화, 화이트 보드 및 도메인 모델링 세션에서 DDD 기술을 적용하는 방법을 알아보려고 노력해야 합니다.

#### <a name="additional-resources"></a>추가 리소스

##### <a name="ddd-domain-driven-design"></a>DDD(도메인 기반 디자인)

-   **Eric Evans. Domain Language**
    [*http://domainlanguage.com/*](http://domainlanguage.com/)

-   **Martin Fowler. 도메인 기반 디자인**
    [*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)

-   **Jimmy Bogard. Strengthening your domain: a primer**(도메인 강화: 입문서)
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)

##### <a name="ddd-books"></a>DDD 서적

-   **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)

-   **Vaughn Vernon. Implementing Domain-Driven Design**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Vaughn Vernon. Domain-Driven Design Distilled**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)

-   **Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)

-   **Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)

-   **Abel Avram 및 Floyd Marinescu. Domain-Driven Design Quickly**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)

DDD 교육

-   **Julie Lerman 및 Steve Smith. Domain-Driven Design Fundamentals**(도메인 기반 디자인 기본 사항)
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)


>[!div class="step-by-step"]
[이전](../multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md) [다음](apply-simplified-microservice-cqrs-ddd-patterns.md)

