---
title: "EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="d89bc-104">EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법</span><span class="sxs-lookup"><span data-stu-id="d89bc-104">Applying CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="d89bc-105">EShopOnContainers 참조 응용 프로그램에서 주문 마이크로 서비스의 디자인 원칙 CQRS 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-105">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="d89bc-106">그러나 방금 쿼리 명령에서 분리 되 고 동일한 데이터베이스를 사용 하 여 두 가지 동작 모두에 대 한 가장 간단한 접근 방식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-106">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="d89bc-107">이러한 패턴 및 여기에서 중요 한 점은의 핵심은 쿼리 idempotent 않는다는: 해당 시스템의 상태는 시스템을 쿼리 하는 몇 번 변경 되지 않으므로 관계 없이 있습니다 사용 하 여 트랜잭션 논리 "쓰기" 보다 다른 "읽기" 데이터 모델 정렬 microservices 동일한 데이터베이스를 사용 하는 있지만 도메인 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-107">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system will not change You could even use a different “reads” data model than the transactional logic “writes” domain model, although the ordering microservices is using the same database.</span></span> <span data-ttu-id="d89bc-108">따라서 간단한 CQRS 접근 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-108">Hence this is a simplified CQRS approach.</span></span>

<span data-ttu-id="d89bc-109">반면에 명령, 트랜잭션 및 데이터 업데이트를 트리거하는 시스템의 상태를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-109">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="d89bc-110">명령, 때는 주의 해야 복잡성 및 비즈니스 규칙 끊임없이 변화를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-110">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="d89bc-111">이것은 where DDD 기술을 더 잘 모델링 된 시스템에 적용 하려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-111">This is the where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="d89bc-112">이 가이드에서 제시 DDD 패턴 보편적으로 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-112">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="d89bc-113">이러한 디자인에 대 한 제약 조건을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-113">They introduce constraints on your design.</span></span> <span data-ttu-id="d89bc-114">이러한 제약 조건을 특히 명령 및 시스템 상태를 수정 하는 다른 코드에서 시간에 따라 더 높은 품질 같은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-114">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="d89bc-115">그러나 이러한 제약 조건을 읽고 데이터를 쿼리 하기 위해 더 적은 이점의 복잡성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-115">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="d89bc-116">이러한 패턴 중 하나는 이후 섹션에서 더 검사 하는 집계 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-116">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="d89bc-117">짧게 집계 패턴에 많은 도메인 개체를 처리 도메인에서 해당 관계의 결과로 단일 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-117">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="d89bc-118">수 하지 항상 이점을 얻을 수 있습니다; 쿼리에서이 패턴에서 이 쿼리 논리의 복잡성을 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-118">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="d89bc-119">읽기 전용 쿼리에 대 한 단일 집계로 여러 개체를 처리 하는 방법의 장점은 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-119">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="d89bc-120">만 복잡성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-120">You only get the complexity.</span></span>

<span data-ttu-id="d89bc-121">그림 9-2와 같이,이 가이드는 (즉, 대로 명령을 사용 하 여 트리거) 프로그램 마이크로 서비스의 트랜잭션/업데이트 영역에만 DDD 패턴을 사용 하 여 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-121">As shown in Figure 9-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="d89bc-122">보다 간단한 방법은 따르면 쿼리와 CQRS 방식을 따릅니다 명령에서 분리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-122">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="d89bc-123">"쿼리"쪽을 구현 하기 위한 EF 코어, AutoMapper 프로젝션, 저장된 프로시저, 뷰, 구체화 된 뷰 또는 마이크로 ORM와 같은 완전 한 ORM 프로그램에서 여러 방법 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-123">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="d89bc-124">ORM 같은 및 eShopOnContainers (구체적으로 정렬 마이크로 서비스)는 마이크로 사용 하 여 직접 쿼리를 구현 하도록 선택 했으므로이 가이드에서 [Dapper](https://github.com/StackExchange/dapper-dot-net)합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-124">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="d89bc-125">이렇게 하면 매우 적은 양의 오버 헤드는 밝은 프레임 워크 덕분에 최상의 성능을 위해서는 SQL 문을 기반으로 모든 쿼리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-125">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="d89bc-126">이 방법을 사용 하면 모델에 엔터티는 SQL 데이터베이스에 유지 하는 방법에 영향을 주는 모든 업데이트에는 해야 Dapper 또는 쿼리를 별도 다른 모든 (비 EF) 방법을 사용 하는 SQL 쿼리를 별도 업데이트 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-126">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="d89bc-127">CQRS 및 DDD 패턴은 최상위 아키텍처 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-127">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="d89bc-128">해당 CQRS, 대부분 DDD 패턴 (예: DDD 레이어 또는 집계를 사용 하 여 도메인 모델) 이해 해야 하는 아키텍처 스타일 아니라만 아키텍처 패턴.</span><span class="sxs-lookup"><span data-stu-id="d89bc-128">It important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="d89bc-129">Microservices, SOA 및 이벤트 기반 아키텍처 (EDA)은 아키텍처 스타일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-129">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="d89bc-130">개체 설명 시스템 많은 microservices 등의 여러 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-130">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="d89bc-131">CQRS 및 DDD 패턴을 단일 시스템 또는 구성 요소; 내부 항목에 대해 설명 이 경우, 한 마이크로 서비스 내 항목 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-131">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="d89bc-132">서로 다른 제한 된 컨텍스트 (BCs) 서로 다른 패턴을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-132">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="d89bc-133">서로 다른 책임 있고 다양 한 솔루션으로 인해입니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-133">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="d89bc-134">것이 실패 하면 모든 범위는 같은 패턴을 강제 적용 하는 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-134">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="d89bc-135">CQRS 및 DDD 패턴을 모든 위치에서 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d89bc-135">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="d89bc-136">많은 하위 시스템, BCs, 또는 microservices 더 간단 하 고 단순 CRUD 서비스를 사용 하 여 또는 다른 방식을 사용 하 여 보다 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-136">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="d89bc-137">하나의 응용 프로그램 아키텍처 없는: 시스템 또는 종단 간 응용 프로그램의 아키텍처 디자인 하는 (예: microservices 아키텍처).</span><span class="sxs-lookup"><span data-stu-id="d89bc-137">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="d89bc-138">그러나 각 경계가 지정 된 컨텍스트 또는 해당 응용 프로그램 내의 마이크로 서비스의 디자인 자체 장단점 및 아키텍처 패턴 수준에서 내부 디자인 관련 결정을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="d89bc-138">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="d89bc-139">동일한 아키텍처 패턴 CQRS 또는 DDD 같은 everywhere 적용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d89bc-139">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

####  <a name="additional-resources"></a><span data-ttu-id="d89bc-140">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="d89bc-140">Additional resources</span></span>

-   <span data-ttu-id="d89bc-141">**Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span><span class="sxs-lookup"><span data-stu-id="d89bc-141">**Martin Fowler. CQRS**
[*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span></span>

-   <span data-ttu-id="d89bc-142">**Greg Young 합니다. CQS vs입니다. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span><span class="sxs-lookup"><span data-stu-id="d89bc-142">**Greg Young. CQS vs. CQRS**
[*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span></span>

-   <span data-ttu-id="d89bc-143">**Greg Young 합니다. CQRS 문서**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span><span class="sxs-lookup"><span data-stu-id="d89bc-143">**Greg Young. CQRS Documents**
[*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span></span>

-   <span data-ttu-id="d89bc-144">**Greg Young 합니다. CQRS 작업 기반된 Ui 및 이벤트 소싱**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span><span class="sxs-lookup"><span data-stu-id="d89bc-144">**Greg Young. CQRS, Task Based UIs and Event Sourcing**
[*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span></span>

-   <span data-ttu-id="d89bc-145">**Udi Dahan 합니다. CQRS 설명이 명확해졌습니다**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="d89bc-145">**Udi Dahan. Clarified CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="d89bc-146">**CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="d89bc-146">**CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="d89bc-147">**이벤트 소싱 (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span><span class="sxs-lookup"><span data-stu-id="d89bc-147">**Event-Sourcing (ES)**
[*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d89bc-148">[이전] [다음] (cqrs 마이크로 서비스 reads.md) (apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="d89bc-148">[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)</span></span>
