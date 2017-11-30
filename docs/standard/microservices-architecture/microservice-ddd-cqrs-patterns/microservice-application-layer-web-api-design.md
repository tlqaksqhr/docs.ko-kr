---
title: "마이크로 서비스 응용 프로그램 계층 및 Web API 디자인"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스 응용 프로그램 계층 및 Web API 디자인"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="36ff7-104">마이크로 서비스 응용 프로그램 계층 및 Web API 디자인</span><span class="sxs-lookup"><span data-stu-id="36ff7-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="36ff7-105">단색 원칙 및 종속성 주입을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="36ff7-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="36ff7-106">단색 원칙은 현대적이 고 필수적인 같은 응용 프로그램 DDD 패턴과 마이크로 서비스를 개발에 사용할 중요 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="36ff7-107">단색는 머리글자어로 해당 5 개 그룹 원칙은:</span><span class="sxs-lookup"><span data-stu-id="36ff7-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="36ff7-108">단일 책임 원칙</span><span class="sxs-lookup"><span data-stu-id="36ff7-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="36ff7-109">열기/닫기 원칙</span><span class="sxs-lookup"><span data-stu-id="36ff7-109">Open/closed principle</span></span>

-   <span data-ttu-id="36ff7-110">Liskov 대체 원칙</span><span class="sxs-lookup"><span data-stu-id="36ff7-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="36ff7-111">반전 분리 원칙</span><span class="sxs-lookup"><span data-stu-id="36ff7-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="36ff7-112">종속성 반전 원칙</span><span class="sxs-lookup"><span data-stu-id="36ff7-112">Dependency Inversion principle</span></span>

<span data-ttu-id="36ff7-113">솔리드 응용 프로그램 또는 마이크로 서비스 내부 계층을 디자인 하는 방법에 대 한 및 이들 간의 종속성을 분리 하는 방법에 대 한 자세한입니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="36ff7-114">도메인에 있지만 응용 프로그램의 기술적 설계에는 관련 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="36ff7-115">최종 원칙 종속성 Inversion (DI) 원칙을 사용 하면 분리 된 DDD 계층을 더 잘 구현 수 있는, 계층의 나머지 부분에서 인프라 계층을 분리 하기 위한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="36ff7-116">DI는 종속성 반전 원칙을 구현 하는 한 가지 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="36ff7-117">이 개체 및 개체 종속성 간의 느슨한 결합을 실현을 위한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="36ff7-118">대신 직접 공동 작업자를 인스턴스화하거나 정적 참조를 사용 하 여, 해당 작업을 수행 하는 데 필요한 클래스는 개체는에 제공 (또는 "에 삽입")는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="36ff7-119">대부분의 경우 클래스 명시적 종속 관계 원칙에 따라 수 있으므로 해당 생성자를 통해 해당 종속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="36ff7-120">DI은 일반적으로 Inversion of Control IoC ()는 특정 컨테이너 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="36ff7-121">ASP.NET Core 간단한 기본 제공 IoC 컨테이너를 제공 하지만 Autofac 또는 Ninject 같은 즐겨 찾는 IoC 컨테이너를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="36ff7-122">단색 원칙을 따르면를 작은 하 고, 잘 구성 된 테스트를 쉽게 거친 자연스럽 게 클래스는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="36ff7-123">하지만 너무 많은 종속성은 클래스에 삽입 되는 경우 어떻게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="36ff7-124">생성자를 통해 DI를 사용 하는 경우 생성자에 대 한 매개 변수 개수 확인만 하 여 점을 감지할 쉽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="36ff7-125">너무 많은 종속성이 있는 경우이 일반적으로 기호 (한 [냄새 코드](http://deviq.com/code-smells/)) 클래스를 너무 많이 수행 하 고 아마도 단일 책임 원칙을 위반 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="36ff7-126">걸리는 자세히 단색을 포함 하는 다른 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="36ff7-127">따라서이 가이드에 다음이 항목 중 최소 지식이 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ff7-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="36ff7-128">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="36ff7-128">Additional resources</span></span>

-   <span data-ttu-id="36ff7-129">**단색: 기본 OOP 원칙**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="36ff7-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="36ff7-130">**컨트롤 컨테이너 및 종속성 주입 패턴의 반전**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="36ff7-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="36ff7-131">**Steve Smith 합니다. 새 작업은**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="36ff7-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="36ff7-132">[이전] (nosql-데이터베이스-지 속성-infrastructure.md) [다음] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="36ff7-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
