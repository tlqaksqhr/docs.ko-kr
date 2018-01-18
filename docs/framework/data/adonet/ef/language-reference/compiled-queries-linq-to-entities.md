---
title: "컴파일된 쿼리 (LINQ to Entities)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c13450a7f05efd188607c80b920616f532f745d4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="compiled-queries--linq-to-entities"></a><span data-ttu-id="8ee9e-102">컴파일된 쿼리 (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="8ee9e-102">Compiled Queries  (LINQ to Entities)</span></span>
<span data-ttu-id="8ee9e-103">구조적으로 비슷한 쿼리를 Entity Framework에서 여러 차례 실행하는 응용 프로그램이 있는 경우, 쿼리를 한 번 컴파일한 후 매개 변수를 다르게 하여 여러 차례 실행하는 방법을 통해 성능을 높일 수 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-103">When you have an application that executes structurally similar queries many times in the Entity Framework, you can frequently increase performance by compiling the query one time and executing it several times with different parameters.</span></span> <span data-ttu-id="8ee9e-104">예를 들어, 응용 프로그램에서 특정 도시의 모든 고객을 검색해야 하며 사용자가 런타임에 양식에서 도시를 지정하는 경우를 생각해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-104">For example, an application might have to retrieve all the customers in a particular city; the city is specified at runtime by the user in a form.</span></span> <span data-ttu-id="8ee9e-105">LINQ to Entities에서는 컴파일된 쿼리를 이 용도로 사용할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-105">LINQ to Entities supports using compiled queries for this purpose.</span></span>  
  
 <span data-ttu-id="8ee9e-106">.NET Framework 4.5부터 시작하여 LINQ 쿼리가 자동으로 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-106">Starting with the .NET Framework 4.5, LINQ queries are cached automatically.</span></span> <span data-ttu-id="8ee9e-107">그러나, 여전히 컴파일된 LINQ 쿼리를 사용하여 나중에 실행할 때 이러한 비용을 줄일 수 있으며 컴파일된 쿼리는 자동으로 캐시되는 LINQ 쿼리에서보다 효율적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-107">However, you can still use compiled LINQ queries to reduce this cost in later executions and compiled queries can be more efficient than LINQ queries that are automatically cached.</span></span> <span data-ttu-id="8ee9e-108">메모리 내 컬렉션에 `Enumerable.Contains` 연산자를 적용하는 LINQ to Entities 쿼리는 자동으로 캐시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-108">Note that LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="8ee9e-109">또한 메모리 내 컬렉션은 컴파일된 LINQ 쿼리에서 매개 변수화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-109">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
 <span data-ttu-id="8ee9e-110"><xref:System.Data.Objects.CompiledQuery> 클래스는 쿼리를 재사용할 수 있도록 컴파일하고 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-110">The <xref:System.Data.Objects.CompiledQuery> class provides compilation and caching of queries for reuse.</span></span> <span data-ttu-id="8ee9e-111">개념상 이 클래스에는 다수의 오버로드가 있는 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-111">Conceptually, this class contains a <xref:System.Data.Objects.CompiledQuery>'s `Compile` method with several overloads.</span></span> <span data-ttu-id="8ee9e-112">이 `Compile` 메서드를 호출하여 컴파일된 쿼리를 나타내는 새 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-112">Call the `Compile` method to create a new delegate to represent the compiled query.</span></span> <span data-ttu-id="8ee9e-113">`Compile` 및 매개 변수 값과 함께 제공된 <xref:System.Data.Objects.ObjectContext> 메서드는 <xref:System.Linq.IQueryable%601> 인스턴스와 같이 결과를 생성하는 대리자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-113">The `Compile` methods, provided with a <xref:System.Data.Objects.ObjectContext> and parameter values, return a delegate that produces some result (such as an <xref:System.Linq.IQueryable%601> instance).</span></span> <span data-ttu-id="8ee9e-114">쿼리는 첫 번째 실행 중에만 한 번 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-114">The query compiles once during only the first execution.</span></span> <span data-ttu-id="8ee9e-115">컴파일 시에 쿼리에 대해 설정된 병합 옵션은 나중에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-115">The merge options set for the query at the time of the compilation cannot be changed later.</span></span> <span data-ttu-id="8ee9e-116">쿼리가 컴파일되면 기본 형식의 매개 변수만 제공할 수 있지만 생성된 SQL을 변경할 쿼리의 부분을 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-116">Once the query is compiled you can only supply parameters of primitive type but you cannot replace parts of the query that would change the generated SQL.</span></span> <span data-ttu-id="8ee9e-117">자세한 내용은 참조 [Entity Framework 병합 옵션 및 컴파일된 쿼리](http://go.microsoft.com/fwlink/?LinkId=199591)</span><span class="sxs-lookup"><span data-stu-id="8ee9e-117">For more information, see [Entity Framework Merge Options and Compiled Queries](http://go.microsoft.com/fwlink/?LinkId=199591)</span></span>  
  
 <span data-ttu-id="8ee9e-118">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 식 하는 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드가 컴파일하는 제네릭의 하나로 표현 됩니다 `Func` 대리자와 같은 <xref:System.Func%605>합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-118">The [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query expression that the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method compiles is represented by one of the generic `Func` delegates, such as <xref:System.Func%605>.</span></span> <span data-ttu-id="8ee9e-119">쿼리 식은 최대로 `ObjectContext` 매개 변수 1개, 반환 매개 변수 1개 및 쿼리 매개 변수 16개를 캡슐화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-119">At most, the query expression can encapsulate an `ObjectContext` parameter, a return parameter, and 16 query parameters.</span></span> <span data-ttu-id="8ee9e-120">쿼리 매개 변수가 17개 이상 필요한 경우 속성으로 쿼리 매개 변수를 나타내는 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-120">If more than 16 query parameters are required, you can create a structure whose properties represent query parameters.</span></span> <span data-ttu-id="8ee9e-121">속성을 설정한 후 쿼리 식에서 구조의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-121">You can then use the properties on the structure in the query expression after you set the properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ee9e-122">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-122">Example</span></span>  
 <span data-ttu-id="8ee9e-123">다음 예제에서는 <xref:System.Decimal> 입력 매개 변수를 사용하고 총 금액이 200달러 이상인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-123">The following example compiles and then invokes a query that accepts a <xref:System.Decimal> input parameter and returns a sequence of orders where the total due is greater than or equal to $200.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-124">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-124">Example</span></span>  
 <span data-ttu-id="8ee9e-125">다음 예제에서는 <xref:System.Data.Objects.ObjectQuery%601> 인스턴스를 반환하는 쿼리를 컴파일한 후 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-125">The following example compiles and then invokes a query that returns an <xref:System.Data.Objects.ObjectQuery%601> instance:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-126">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-126">Example</span></span>  
 <span data-ttu-id="8ee9e-127">다음 예제에서는 제품 가격의 평균을 <xref:System.Decimal> 값 형태로 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-127">The following example compiles and then invokes a query that returns the average of the product list prices as a <xref:System.Decimal> value:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-128">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-128">Example</span></span>  
 <span data-ttu-id="8ee9e-129">다음 예제에서는 <xref:System.String> 입력 매개 변수를 사용하고 전자 메일 주소가 지정 문자열로 시작되는 `Contact`를 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-129">The following example compiles and then invokes a query that accepts a <xref:System.String> input parameter and then returns a `Contact` whose e-mail address starts with the specified string:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-130">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-130">Example</span></span>  
 <span data-ttu-id="8ee9e-131">다음 예제에서는 <xref:System.DateTime> 및 <xref:System.Decimal> 입력 매개 변수를 사용하고 주문 날짜가 2003년 3월 8일 이후이고 합계 $300 미만인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-131">The following example compiles and then invokes a query that accepts <xref:System.DateTime> and <xref:System.Decimal> input parameters and returns a sequence of orders where the order date is later than March 8, 2003, and the total due is less than $300.00:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-132">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-132">Example</span></span>  
 <span data-ttu-id="8ee9e-133">다음 예제에서는 <xref:System.DateTime> 입력 매개 변수를 사용하고 주문 날짜가 2004년 3월 8일 이후인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-133">The following example compiles and then invokes a query that accepts a <xref:System.DateTime> input parameter and returns a sequence of orders where the order date is later than March 8, 2004.</span></span> <span data-ttu-id="8ee9e-134">이 쿼리는 주문 정보를 일련의 익명 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-134">This query returns the order information as a sequence of anonymous types.</span></span> <span data-ttu-id="8ee9e-135">익명 형식은 컴파일러에서 유추됩니다. 따라서 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드에서 형식 매개 변수를 지정할 수 없으며, 형식은 쿼리 자체에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-135">Anonymous types are inferred by the compiler, so you cannot specify type parameters in the <xref:System.Data.Objects.CompiledQuery>'s `Compile` method and the type is defined in the query itself.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## <a name="example"></a><span data-ttu-id="8ee9e-136">예제</span><span class="sxs-lookup"><span data-stu-id="8ee9e-136">Example</span></span>  
 <span data-ttu-id="8ee9e-137">다음 예제에서는 사용자 정의 구조 입력 매개 변수를 사용하고 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-137">The following example compiles and then invokes a query that accepts a user-defined structure input parameter and returns a sequence of orders.</span></span> <span data-ttu-id="8ee9e-138">이 구조는 시작 날짜, 종료 날짜 및 수수료 합계 쿼리 매개 변수를 정의하고, 2003년 3월 3일에서 3월 8일 사이에 배송되었으며 수수료 합계가 $700.00보다 큰 주문을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-138">The structure defines start date, end date, and total due query parameters, and the query returns orders shipped between March 3 and March 8, 2003 with a total due greater than $700.00.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 <span data-ttu-id="8ee9e-139">쿼리 매개 변수를 정의하는 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9e-139">The structure that defines the query parameters:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## <a name="see-also"></a><span data-ttu-id="8ee9e-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ee9e-140">See Also</span></span>  
 [<span data-ttu-id="8ee9e-141">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8ee9e-141">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="8ee9e-142">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8ee9e-142">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [<span data-ttu-id="8ee9e-143">Entity Framework 병합 옵션 및 컴파일된 쿼리</span><span class="sxs-lookup"><span data-stu-id="8ee9e-143">Entity Framework Merge Options and Compiled Queries</span></span>](http://go.microsoft.com/fwlink/?LinkId=199591)
