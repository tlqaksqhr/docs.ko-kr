---
title: eShopOnContainers의 DDD 마이크로 서비스에서 CQRS 및 CQS 방법 적용
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | eShopOnContainers의 DDD 마이크로 서비스에서 CQRS 및 CQS 방법 적용
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6be8b52f42e3e37ff03e561af45c46f4dd283d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577061"
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="e875d-103">eShopOnContainers의 DDD 마이크로 서비스에서 CQRS 및 CQS 방법 적용</span><span class="sxs-lookup"><span data-stu-id="e875d-103">Applying CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="e875d-104">EShopOnContainers 참조 응용 프로그램의 주문 마이크로 서비스 설계는 CQRS 원칙을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-104">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="e875d-105">그러나 명령에서 쿼리를 분리하고 두 작업에 동일한 데이터베이스를 사용하는 가장 간단한 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-105">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="e875d-106">이러한 패턴의 핵심이자 중요한 점은 쿼리가 멱등이라는 점입니다.즉 시스템에 몇 번을 쿼리하던 시스템의 상태가 변하지 않습니다. 심지어 주문 마이크로 서비스가 같은 데이터베이스를 사용하더라도 트랜잭션 논리 "쓰기" 도메인 모델과 다른 "읽기" 데이터 모델을 사용할 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e875d-106">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system will not change You could even use a different “reads” data model than the transactional logic “writes” domain model, although the ordering microservices is using the same database.</span></span> <span data-ttu-id="e875d-107">따라서 간단한 CQRS 접근 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-107">Hence this is a simplified CQRS approach.</span></span>

<span data-ttu-id="e875d-108">반면에 트랜잭션과 데이터 업데이트를 트리거하는 명령은 시스템에서 상태를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-108">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="e875d-109">명령에서는 복잡성과 끊임없이 변화하는 비즈니스 규칙을 처리하는 데 중의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-109">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="e875d-110">이것이 더 나은 모델링 시스템을 위해 DDD 기법을 적용하는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-110">This is the where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="e875d-111">이 가이드에서 제시하는 DDD 패턴을 보편적으로 적용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-111">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="e875d-112">여기에는 설계에 제약이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-112">They introduce constraints on your design.</span></span> <span data-ttu-id="e875d-113">이러한 제약은 시간에 따른 품질 향상과 같은 장점도 있습니다. 특히 시스템 상태를 수정하는 명령 및 기타 코드에서 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-113">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="e875d-114">그러나 이러한 제약은 데이터 읽기 및 쿼리에서 장점보다는 복잡성을 더합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-114">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="e875d-115">이후의 섹션에서 상세히 다룰 집계가 바로 그러한 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-115">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="e875d-116">간략히 말해 집계 패턴에서는 도메인에서의 관계에 따른 결과로 여러 도메인 개체를 단일 단위로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-116">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="e875d-117">쿼리에서 이 패턴이 항상 장점만 있는 것은 아닙니다. 쿼리 논리의 복잡성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-117">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="e875d-118">읽기 전용 쿼리의 경우 여러 개체를 단일 집계로 취급하는 것이 장점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-118">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="e875d-119">복잡성만 커집니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-119">You only get the complexity.</span></span>

<span data-ttu-id="e875d-120">그림 9-2와 같이 이 가이드에서는 마이크로 서비스의 트랜잭션/업데이트에만 DDD 패턴 사용을 권장합니다(즉 명령으로 트리거).</span><span class="sxs-lookup"><span data-stu-id="e875d-120">As shown in Figure 9-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="e875d-121">쿼리는 더 간단한 방식을 따를 수 있고 CQRS 방식에 따라 명령과 구분될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-121">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="e875d-122">"쿼리 측" 구현을 위해 EF Core, AutoMapper 프로젝션 같은 종합 ORM, 저장 프로시저, 뷰, 구체화된 뷰나 마이크로 ORM 등, 여러 방식 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-122">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="e875d-123">이 가이드와 eShopOnContainers(특히 주문 마이크로 서비스)에서는 [Dapper](https://github.com/StackExchange/dapper-dot-net) 같은 마이크로 ORM을 사용하여 간편한 쿼리를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-123">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="e875d-124">이렇게 하면 부담이 거의 없는 가벼운 프레임워크 덕분에 SQL 문 기반의 모든 쿼리를 구현하여 최고 성능을 낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-124">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="e875d-125">이 방법을 사용할 때는 엔터티가 SQL 데이터베이스에 지속되는 방식에 영향을 미치는 모든 모델 업데이트에서 Dapper 나 기타 다른 개별(비 EF) 쿼리 방식에서 사용되는 SQL 쿼리에 대한 개별 업데이트도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-125">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="e875d-126">CQRS 및 DDD 패턴은 최상위 아키텍처가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-126">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="e875d-127">CQRS 및 대부분의 DDD 패턴(DDD 계층이나 집계가 있는 도메인 모델)은 아키텍처 스타일이 아닌 아키텍처 패턴에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-127">It important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="e875d-128">아키텍처 스타일의 예로는 마이크로 서비스, SOA 및 EDA(이벤트 중심 아키텍처)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-128">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="e875d-129">이들은 여러 마이크로 서비스와 같은 여러 구성 요소의 시스템을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-129">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="e875d-130">CQRS 및 DDD 패턴은 단일 시스템 또는 구성 요소 내 항목을 설명합니다. 이 경우에는 마이크로 서비스 내부의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-130">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="e875d-131">서로 다른 DC(경계가 있는 컨텍스트)에는 서로 다른 패턴이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-131">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="e875d-132">책임도 다르고 솔루션도 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-132">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="e875d-133">동일한 패턴을 모든 곳에 강제할 경우 실패로 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-133">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="e875d-134">CQRS 및 DDD 패턴을 모든 곳에 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-134">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="e875d-135">많은 하위 시스템, BC 또는 마이크로 서비스는 더 간단하며 간단한 CRUD 서비스 또는 다른 방식을 통해 더 간편하게 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-135">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="e875d-136">응용 프로그램 아키텍처는 하나뿐입니다. 즉 사용자가 설계하는 시스템 아키텍처 또는 종단 간 응용 프로그램입니다(예: 마이크로 서비스 아키텍처).</span><span class="sxs-lookup"><span data-stu-id="e875d-136">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="e875d-137">그러나 이 응용 프로그램 내에서 경계가 지정된 각각의 컨텍스트나 마이크로 서비스의 설계에서는 아키텍처 패턴 수준에서 자체 절충 및 내부 설계 결정을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="e875d-137">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="e875d-138">CQRS 또는 DDD처럼 동일한 아키텍처 패턴을 모든 곳에 적용해서는 안 됩니다. </span><span class="sxs-lookup"><span data-stu-id="e875d-138">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

####  <a name="additional-resources"></a><span data-ttu-id="e875d-139">추가 자료</span><span class="sxs-lookup"><span data-stu-id="e875d-139">Additional resources</span></span>

-   <span data-ttu-id="e875d-140">**Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span><span class="sxs-lookup"><span data-stu-id="e875d-140">**Martin Fowler. CQRS**
[*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span></span>

-   <span data-ttu-id="e875d-141">**Greg Young. CQS vs. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span><span class="sxs-lookup"><span data-stu-id="e875d-141">**Greg Young. CQS vs. CQRS**
[*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span></span>

-   <span data-ttu-id="e875d-142">**Greg Young. CQRS 문서**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span><span class="sxs-lookup"><span data-stu-id="e875d-142">**Greg Young. CQRS Documents**
[*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span></span>

-   <span data-ttu-id="e875d-143">**Greg Young. CQRS, 작업 기반 UI 및 이벤트 소싱**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span><span class="sxs-lookup"><span data-stu-id="e875d-143">**Greg Young. CQRS, Task Based UIs and Event Sourcing**
[*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span></span>

-   <span data-ttu-id="e875d-144">**Udi Dahan. 명확한 CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="e875d-144">**Udi Dahan. Clarified CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="e875d-145">**CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="e875d-145">**CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="e875d-146">**ES(이벤트 소싱)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span><span class="sxs-lookup"><span data-stu-id="e875d-146">**Event-Sourcing (ES)**
[*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e875d-147">[이전] (apply-simplified-microservice-cqrs-ddd-patterns.md) [다음] (cqrs-microservice-reads.md)</span><span class="sxs-lookup"><span data-stu-id="e875d-147">[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)</span></span>
