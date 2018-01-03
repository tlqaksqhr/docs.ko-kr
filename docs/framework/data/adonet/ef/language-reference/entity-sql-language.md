---
title: "Entity SQL 언어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0485dc9ee1e1b6fa134e0a7518b7ae49748ae292
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="entity-sql-language"></a><span data-ttu-id="8f2db-102">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="8f2db-102">Entity SQL Language</span></span>
<span data-ttu-id="8f2db-103">Entity SQL은 SQL과 유사한 저장소 독립적 쿼리 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="8f2db-104">Entity SQL을 사용하면 엔터티 데이터를 개체 또는 테이블 형식으로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="8f2db-105">Entity SQL은 다음의 경우에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="8f2db-106">쿼리를 동적으로 런타임에 생성해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="8f2db-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="8f2db-107">이 경우에는 런타임에 Entity SQL 쿼리 문자열을 생성하는 대신 <xref:System.Data.Objects.ObjectQuery%601>의 쿼리 작성기 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="8f2db-108">쿼리를 모델 정의의 일부로 정의할 경우.</span><span class="sxs-lookup"><span data-stu-id="8f2db-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="8f2db-109">Entity SQL만 데이터 모델에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="8f2db-110">자세한 내용은 참조 [QueryView 요소 (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span><span class="sxs-lookup"><span data-stu-id="8f2db-110">For more information, see [QueryView Element (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span></span>  
  
-   <span data-ttu-id="8f2db-111">EntityClient에서 <xref:System.Data.EntityClient.EntityDataReader>를 사용하여 읽기 전용 엔터티 데이터를 행 집합으로 반환할 경우.</span><span class="sxs-lookup"><span data-stu-id="8f2db-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="8f2db-112">자세한 내용은 참조 [Entity Framework 용 EntityClient 공급자](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="8f2db-113">SQL 기반 쿼리 언어의 전문가에게는 Entity SQL이 가장 편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="8f2db-114">EntityClient 공급자와 함께 Entity SQL 사용</span><span class="sxs-lookup"><span data-stu-id="8f2db-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="8f2db-115">EntityClient 공급자와 함께 Entity SQL을 사용하려는 경우 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2db-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="8f2db-116">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="8f2db-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="8f2db-117">방법: EntityConnection 연결 문자열 작성</span><span class="sxs-lookup"><span data-stu-id="8f2db-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="8f2db-118">방법: PrimitiveType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="8f2db-119">방법: StructuralType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="8f2db-120">방법: RefType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="8f2db-121">방법: 복합 형식을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="8f2db-122">방법: 중첩된 컬렉션을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="8f2db-123">방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="8f2db-124">방법: EntityCommand를 사용하여 매개 변수가 있는 저장 프로시저 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="8f2db-125">방법: 다형 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="8f2db-126">방법: Navigate 연산자로 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="8f2db-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="8f2db-127">개체 쿼리와 함께 Entity SQL 사용</span><span class="sxs-lookup"><span data-stu-id="8f2db-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="8f2db-128">개체 쿼리와 함께 Entity SQL을 사용하려는 경우 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2db-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="8f2db-129">방법: 엔터티 형식 개체를 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](http://msdn.microsoft.com/en-us/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="8f2db-130">방법: 매개 변수가 있는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-130">How to: Execute a Parameterized Query</span></span>](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="8f2db-131">방법: 탐색 속성을 사용 하 여 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="8f2db-131">How to: Navigate Relationships Using Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="8f2db-132">방법: 사용자 정의 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-132">How to: Call a User-Defined Function</span></span>](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="8f2db-133">방법: 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="8f2db-133">How to: Filter Data</span></span>](http://msdn.microsoft.com/en-us/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="8f2db-134">방법: 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="8f2db-134">How to: Sort Data</span></span>](http://msdn.microsoft.com/en-us/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="8f2db-135">방법: 데이터 그룹화</span><span class="sxs-lookup"><span data-stu-id="8f2db-135">How to: Group Data</span></span>](http://msdn.microsoft.com/en-us/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="8f2db-136">방법: 데이터를 집계</span><span class="sxs-lookup"><span data-stu-id="8f2db-136">How to: Aggregate Data</span></span>](http://msdn.microsoft.com/en-us/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="8f2db-137">방법: 익명 형식 개체를 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](http://msdn.microsoft.com/en-us/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="8f2db-138">방법: 기본 형식의 컬렉션을 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="8f2db-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](http://msdn.microsoft.com/en-us/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="8f2db-139">방법: EntityCollection의 관련된 개체를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2db-139">How to: Query Related Objects in an EntityCollection</span></span>](http://msdn.microsoft.com/en-us/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="8f2db-140">방법: 두 개의 쿼리의 합집합을 주문</span><span class="sxs-lookup"><span data-stu-id="8f2db-140">How to: Order the Union of Two Queries</span></span>](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="8f2db-141">방법: 쿼리를 통해 페이지 결과</span><span class="sxs-lookup"><span data-stu-id="8f2db-141">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="8f2db-142">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8f2db-142">In This Section</span></span>  
 [<span data-ttu-id="8f2db-143">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="8f2db-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="8f2db-144">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="8f2db-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f2db-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f2db-145">See Also</span></span>  
 [<span data-ttu-id="8f2db-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8f2db-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="8f2db-147">언어 참조</span><span class="sxs-lookup"><span data-stu-id="8f2db-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
