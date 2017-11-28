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
ms.openlocfilehash: be2d8a2fd77d65b82574efde3b9922a1176ad2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="6073e-104">DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리</span><span class="sxs-lookup"><span data-stu-id="6073e-104">Tackling Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="6073e-105">*비즈니스 도메인에 대한 이해를 반영하는 각 마이크로 서비스 또는 제한된 컨텍스트를 위한 도메인 모델을 디자인하세요.*</span><span class="sxs-lookup"><span data-stu-id="6073e-105">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="6073e-106">이 섹션에서는 복잡한 하위 시스템 또는 끊임없이 변화하는 비즈니스 규칙을 사용하는 도메인 전문가의 지식에서 파생된 마이크로 서비스를 처리해야 할 때 구현하는 고급 마이크로 서비스에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-106">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="6073e-107">이 섹션에 사용된 아키텍처 패턴은 그림 9-1에 나와 있는 것처럼 DDD(도메인 기반 디자인) 및 CQRS(Command and Query Responsibility Segregation) 접근 방식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-107">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 9-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="6073e-108">**그림 9-1**.</span><span class="sxs-lookup"><span data-stu-id="6073e-108">**Figure 9-1**.</span></span> <span data-ttu-id="6073e-109">각 마이크로 서비스에 대한 외부 마이크로 서비스 아키텍처 및 내부 아키텍처 패턴</span><span class="sxs-lookup"><span data-stu-id="6073e-109">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="6073e-110">그러나 ASP.NET Core Web API 서비스를 구현하는 방법 또는 Swashbuckle을 사용하여 Swagger 메타데이터를 표시하는 방법과 같은 대부분의 데이터 기반 마이크로 서비스 기술은 DDD 패턴을 사용하여 내부적으로 구현된 고급 마이크로 서비스에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-110">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="6073e-111">이 섹션은 이전 섹션의 확장입니다. 이전에 설명한 대부분의 방법이 여기 또는 모든 종류의 마이크로 서비스에도 적용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-111">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="6073e-112">이 섹션에서는 먼저 eShopOnContainers 참조 응용 프로그램에 사용되는 간소화된 CQRS 패턴에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-112">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="6073e-113">이후에는 응용 프로그램에서 다시 사용할 수 있는 일반적인 패턴을 찾을 수 있도록 지원하는 DDD 기술에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-113">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="6073e-114">DDD는 다양한 학습 리소스 집합이 있는 큰 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-114">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="6073e-115">Eric Evans의 [Domain-Driven Design](https://domainlanguage.com/ddd/)과 같은 서적 및 Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard와 그 밖의 여러 DDD/CQRS 전문가의 추가 자료로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-115">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="6073e-116">그러나 무엇보다도 구체적인 비즈니스 도메인 전문가와 함께 하는 대화, 화이트 보드 및 도메인 모델링 세션에서 DDD 기술을 적용하는 방법을 알아보려고 노력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6073e-116">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="6073e-117">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="6073e-117">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="6073e-118">DDD(도메인 기반 디자인)</span><span class="sxs-lookup"><span data-stu-id="6073e-118">DDD (Domain-Driven Design)</span></span>

-   <span data-ttu-id="6073e-119">**Eric Evans. Domain Language**
    [*http://domainlanguage.com/*](http://domainlanguage.com/)</span><span class="sxs-lookup"><span data-stu-id="6073e-119">**Eric Evans. Domain Language**
[*http://domainlanguage.com/*](http://domainlanguage.com/)</span></span>

-   <span data-ttu-id="6073e-120">**Martin Fowler. 도메인 기반 디자인**
    [*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)</span><span class="sxs-lookup"><span data-stu-id="6073e-120">**Martin Fowler. Domain-Driven Design**
[*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)</span></span>

-   <span data-ttu-id="6073e-121">**Jimmy Bogard. Strengthening your domain: a primer**(도메인 강화: 입문서)
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span><span class="sxs-lookup"><span data-stu-id="6073e-121">**Jimmy Bogard. Strengthening your domain: a primer**
[*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span></span>

##### <a name="ddd-books"></a><span data-ttu-id="6073e-122">DDD 서적</span><span class="sxs-lookup"><span data-stu-id="6073e-122">DDD books</span></span>

-   <span data-ttu-id="6073e-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="6073e-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
[*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="6073e-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span><span class="sxs-lookup"><span data-stu-id="6073e-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
[*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span></span>

-   <span data-ttu-id="6073e-125">**Vaughn Vernon. Implementing Domain-Driven Design**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="6073e-125">**Vaughn Vernon. Implementing Domain-Driven Design**
[*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="6073e-126">**Vaughn Vernon. Domain-Driven Design Distilled**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span><span class="sxs-lookup"><span data-stu-id="6073e-126">**Vaughn Vernon. Domain-Driven Design Distilled**
[*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span></span>

-   <span data-ttu-id="6073e-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span><span class="sxs-lookup"><span data-stu-id="6073e-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
[*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span></span>

-   <span data-ttu-id="6073e-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span><span class="sxs-lookup"><span data-stu-id="6073e-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
[*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span></span>

-   <span data-ttu-id="6073e-129">**Abel Avram 및 Floyd Marinescu. Domain-Driven Design Quickly**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span><span class="sxs-lookup"><span data-stu-id="6073e-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
[*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span></span>

<span data-ttu-id="6073e-130">DDD 교육</span><span class="sxs-lookup"><span data-stu-id="6073e-130">DDD training</span></span>

-   <span data-ttu-id="6073e-131">**Julie Lerman 및 Steve Smith. Domain-Driven Design Fundamentals**(도메인 기반 디자인 기본 사항)
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span><span class="sxs-lookup"><span data-stu-id="6073e-131">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
[*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6073e-132">[이전](../multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md) [다음](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="6073e-132">[Previous] (../multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md) [Next] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
