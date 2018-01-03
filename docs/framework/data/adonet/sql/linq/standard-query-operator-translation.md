---
title: "표준 쿼리 연산자 변환"
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
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a30adbc060ead6eb1805f85bd563021ba7530c36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="bb1ee-102">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-102">Standard Query Operator Translation</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-103">에서는 표준 쿼리 연산자를 SQL 명령으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-103"> translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="bb1ee-104">데이터베이스의 쿼리 프로세서는 SQL 변환에 대 한 실행 의미 체계를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>  
  
 <span data-ttu-id="bb1ee-105">표준 쿼리 연산자에 대해 정의 된 *시퀀스*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="bb1ee-106">시퀀스는 *정렬* 시퀀스의 각 요소에 대 한 참조 id에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="bb1ee-107">자세한 내용은 참조 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-107">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="bb1ee-108">SQL 다루는 주로 *값 집합을 순서 없이*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="bb1ee-109">순서 지정은 일반적으로 명시적으로 지정되는 후처리 작업으로 쿼리의 중간 결과가 아닌 최종 결과에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="bb1ee-110">ID는 값으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-110">Identity is defined by values.</span></span> <span data-ttu-id="bb1ee-111">이러한 이유로 SQL 쿼리는 다중 집합을 다루는 데 인식 (*백*) 대신 *설정*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>  
  
 <span data-ttu-id="bb1ee-112">다음 단락에서는 표준 쿼리 연산자와 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 SQL 서버 공급자에 대한 해당 SQL 변환 사이의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="operator-support"></a><span data-ttu-id="bb1ee-113">연산자 지원</span><span class="sxs-lookup"><span data-stu-id="bb1ee-113">Operator Support</span></span>  
  
### <a name="concat"></a><span data-ttu-id="bb1ee-114">Concat</span><span class="sxs-lookup"><span data-stu-id="bb1ee-114">Concat</span></span>  
 <span data-ttu-id="bb1ee-115"><xref:System.Linq.Enumerable.Concat%2A> 메서드는 수신자 순서와 인수 순서가 동일한 순서 있는 다중 집합에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="bb1ee-116"><xref:System.Linq.Enumerable.Concat%2A>는 공통 순서 이전에 다중 집합에 대해 `UNION ALL`로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>  
  
 <span data-ttu-id="bb1ee-117">최종 단계는 결과가 생성되기 전에 SQL에서 순서를 지정하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="bb1ee-118"><xref:System.Linq.Enumerable.Concat%2A>에서는 해당 인수의 순서를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="bb1ee-119">순서가 적절하게 지정되게 하려면 <xref:System.Linq.Enumerable.Concat%2A>에 대한 결과의 순서를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
### <a name="intersect-except-union"></a><span data-ttu-id="bb1ee-120">Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="bb1ee-120">Intersect, Except, Union</span></span>  
 <span data-ttu-id="bb1ee-121"><xref:System.Linq.Enumerable.Intersect%2A> 및 <xref:System.Linq.Enumerable.Except%2A> 메서드는 집합에 대해서만 잘 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="bb1ee-122">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-122">The semantics for multisets is undefined.</span></span>  
  
 <span data-ttu-id="bb1ee-123"><xref:System.Linq.Enumerable.Union%2A> 메서드는 다중 집합에 대해 순서 없는 다중 집합의 연결로 정의됩니다(사실상 SQL UNION ALL 절의 결과와 같음).</span><span class="sxs-lookup"><span data-stu-id="bb1ee-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>  
  
### <a name="take-skip"></a><span data-ttu-id="bb1ee-124">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="bb1ee-124">Take, Skip</span></span>  
 <span data-ttu-id="bb1ee-125"><xref:System.Linq.Enumerable.Take%2A>및 <xref:System.Linq.Enumerable.Skip%2A> 에 대해서만 잘 정의 된 메서드는 *순서 있는 집합*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="bb1ee-126">순서 없는 집합이나 다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-126">The semantics for unordered sets or multisets are undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb1ee-127"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>에는 SQL Server 2000에 대한 쿼리에서 사용할 경우 몇 가지 제한이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="bb1ee-128">자세한 내용은 "Skip 및 Take 예외 SQL Server 2000에서 에서" 항목을 참조 하십시오. [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 <span data-ttu-id="bb1ee-129">SQL의 순서 지정에 대한 제한 사항 때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 이러한 메서드의 인수에 대한 순서 지정 작업을 메서드의 결과로 이동하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="bb1ee-130">예를 들어 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
 [!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]  
  
 <span data-ttu-id="bb1ee-131">이 코드에 대해 생성된 SQL은 다음과 같이 순서 지정 작업을 맨 뒤로 옮깁니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="bb1ee-132"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>을 연결할 때 지정한 모든 순서가 일치해야 함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="bb1ee-133">그렇지 않으면 결과가 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-133">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="bb1ee-134"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>은 모두 표준 쿼리 연산자 사양을 기반으로 하는 음수가 아닌 정수 계열 상수 인수에 대해 잘 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>  
  
### <a name="operators-with-no-translation"></a><span data-ttu-id="bb1ee-135">변환이 없는 연산자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-135">Operators with No Translation</span></span>  
 <span data-ttu-id="bb1ee-136">다음 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="bb1ee-137">가장 일반적인 이유는 순서 없는 다중 집합과 시퀀스 간의 차이 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-137">The most common reason is the difference between unordered multisets and sequences.</span></span>  
  
|<span data-ttu-id="bb1ee-138">연산자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-138">Operators</span></span>|<span data-ttu-id="bb1ee-139">설명</span><span class="sxs-lookup"><span data-stu-id="bb1ee-139">Rationale</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="bb1ee-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="bb1ee-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="bb1ee-141">SQL 쿼리는 다중 집합에 대해서는 작동하지만 시퀀스에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="bb1ee-142">`ORDER BY`는 결과에 적용되는 마지막 절이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="bb1ee-143">따라서 이러한 두 메서드에 대한 일반 용도 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|  
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="bb1ee-144">순서 있는 집합에 대해 이 메서드의 변환이 가능하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 현재 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="bb1ee-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="bb1ee-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="bb1ee-146">순서 있는 집합에 대해 이러한 메서드의 변환이 가능하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 현재 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="bb1ee-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="bb1ee-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="bb1ee-148">SQL 쿼리는 다중 집합에 대해서는 작동하지만 인덱싱 가능한 시퀀스에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|  
|<span data-ttu-id="bb1ee-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A>(기본 인수로 오버로드)</span><span class="sxs-lookup"><span data-stu-id="bb1ee-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="bb1ee-150">일반적으로 임의의 튜플에 대해 기본값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="bb1ee-151">일부 경우 외부 조인을 통해 튜플에 null 값을 지정할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-151">Null values for tuples are possible in some cases through outer joins.</span></span>|  
  
## <a name="expression-translation"></a><span data-ttu-id="bb1ee-152">식 변환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-152">Expression Translation</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="bb1ee-153">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="bb1ee-153">Null semantics</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-154">에서는 null 비교 의미 체계를 SQL에 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-154"> does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="bb1ee-155">비교 연산자는 구문상 동등한 SQL 항목으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="bb1ee-156">이러한 이유로 의미 체계는 서버 또는 연결 설정에 의해 정의 된 SQL 의미 체계를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="bb1ee-157">예를 들어 두 개의 null 값 기본 SQL Server 설정 같지 않은지 있지만 의미 체계를 변경 하려면 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-158">에서는 쿼리를 변환할 때 서버 설정을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-158"> does not consider server settings when it translates queries.</span></span>  
  
 <span data-ttu-id="bb1ee-159">리터럴 null을 사용한 비교는 해당 SQL 버전(`is null` 또는 `is not null`)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="bb1ee-160">데이터 정렬의 `null` 값은 SQL Server에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-161">에서는 데이터 정렬을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-161"> does not change the collation.</span></span>  
  
### <a name="aggregates"></a><span data-ttu-id="bb1ee-162">집합체</span><span class="sxs-lookup"><span data-stu-id="bb1ee-162">Aggregates</span></span>  
 <span data-ttu-id="bb1ee-163">표준 쿼리 연산자의 집계 메서드 <xref:System.Linq.Enumerable.Sum%2A>은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="bb1ee-164">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 SQL의 의미 체계는 변경되지 않은 상태로 유지되고 <xref:System.Linq.Enumerable.Sum%2A>은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0이 아닌 `null`로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
 <span data-ttu-id="bb1ee-165">중간 결과에 대한 SQL 제한은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 집계에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="bb1ee-166">32비트 정수 수량의 <xref:System.Linq.Enumerable.Sum%2A>은 64비트 결과를 사용하여 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="bb1ee-167">표준 쿼리 연산자 구현이 메모리 내의 해당 시퀀스에 대해 오버플로를 발생시키지 않는 경우에도 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 <xref:System.Linq.Enumerable.Sum%2A> 변환에 대해 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
 <span data-ttu-id="bb1ee-168">마찬가지로 정수 값의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 <xref:System.Linq.Enumerable.Average%2A> 변환은 `integer`이 아닌 `double`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>  
  
### <a name="entity-arguments"></a><span data-ttu-id="bb1ee-169">엔터티 인수</span><span class="sxs-lookup"><span data-stu-id="bb1ee-169">Entity Arguments</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-170">에서는 엔터티 형식을 <xref:System.Linq.Enumerable.GroupBy%2A> 및 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-170"> enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="bb1ee-171">이러한 연산자 변환에서 형식 인수를 사용하는 것은 해당 형식의 모든 멤버를 지정하는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="bb1ee-172">예를 들어 다음 코드는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-172">For example, the following code is equivalent:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
 [!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]  
  
### <a name="equatable--comparable-arguments"></a><span data-ttu-id="bb1ee-173">같을 수 있는/비교 가능한 인수</span><span class="sxs-lookup"><span data-stu-id="bb1ee-173">Equatable / Comparable Arguments</span></span>  
 <span data-ttu-id="bb1ee-174">인수의 같음은 다음과 같은 메서드의 구현에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-174">Equality of arguments is required in the implementation of the following methods:</span></span>  
  
 <xref:System.Linq.Enumerable.Contains%2A>  
  
 <xref:System.Linq.Enumerable.Skip%2A>  
  
 <xref:System.Linq.Enumerable.Union%2A>  
  
 <xref:System.Linq.Enumerable.Intersect%2A>  
  
 <xref:System.Linq.Enumerable.Except%2A>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-175">같음 및 비교에 대 한 지원 *플랫* 인수는 이거나 시퀀스를 포함 하는 인수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-175"> supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="bb1ee-176">단순 인수는 SQL 행에 매핑될 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="bb1ee-177">시퀀스를 포함하지 않는 것으로 정적으로 확인할 수 있는 하나 이상의 엔터티 형식에 대한 프로젝션은 단순 인수인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>  
  
 <span data-ttu-id="bb1ee-178">다음은 단순 인수의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-178">Following are examples of flat arguments:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
 [!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]  
  
 <span data-ttu-id="bb1ee-179">다음은 단순이 아닌(계층적) 인수의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-179">The following are examples of non-flat (hierarchical) arguments.</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
 [!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]  
  
### <a name="visual-basic-function-translation"></a><span data-ttu-id="bb1ee-180">Visual Basic 함수 변환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-180">Visual Basic Function Translation</span></span>  
 <span data-ttu-id="bb1ee-181">Visual Basic 컴파일러에서 사용하는 다음과 같은 도우미 함수는 해당하는 SQL 연산자 및 함수로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>  
  
 `CompareString`  
  
 `DateTime.Compare`  
  
 `Decimal.Compare`  
  
 `IIf (in Microsoft.VisualBasic.Interaction)`  
  
 <span data-ttu-id="bb1ee-182">변환 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-182">Conversion methods:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="bb1ee-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="bb1ee-183">ToBoolean</span></span>|<span data-ttu-id="bb1ee-184">ToSByte</span><span class="sxs-lookup"><span data-stu-id="bb1ee-184">ToSByte</span></span>|<span data-ttu-id="bb1ee-185">ToByte</span><span class="sxs-lookup"><span data-stu-id="bb1ee-185">ToByte</span></span>|<span data-ttu-id="bb1ee-186">ToChar</span><span class="sxs-lookup"><span data-stu-id="bb1ee-186">ToChar</span></span>|  
|<span data-ttu-id="bb1ee-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="bb1ee-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="bb1ee-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="bb1ee-188">ToDate</span></span>|<span data-ttu-id="bb1ee-189">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="bb1ee-189">ToDecimal</span></span>|<span data-ttu-id="bb1ee-190">ToDouble</span><span class="sxs-lookup"><span data-stu-id="bb1ee-190">ToDouble</span></span>|  
|<span data-ttu-id="bb1ee-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="bb1ee-191">ToInteger</span></span>|<span data-ttu-id="bb1ee-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="bb1ee-192">ToUInteger</span></span>|<span data-ttu-id="bb1ee-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="bb1ee-193">ToLong</span></span>|<span data-ttu-id="bb1ee-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="bb1ee-194">ToULong</span></span>|  
|<span data-ttu-id="bb1ee-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="bb1ee-195">ToShort</span></span>|<span data-ttu-id="bb1ee-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="bb1ee-196">ToUShort</span></span>|<span data-ttu-id="bb1ee-197">ToSingle</span><span class="sxs-lookup"><span data-stu-id="bb1ee-197">ToSingle</span></span>|<span data-ttu-id="bb1ee-198">ToString</span><span class="sxs-lookup"><span data-stu-id="bb1ee-198">ToString</span></span>|  
  
## <a name="inheritance-support"></a><span data-ttu-id="bb1ee-199">상속 지원</span><span class="sxs-lookup"><span data-stu-id="bb1ee-199">Inheritance Support</span></span>  
  
### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="bb1ee-200">상속 매핑 제한</span><span class="sxs-lookup"><span data-stu-id="bb1ee-200">Inheritance Mapping Restrictions</span></span>  
 <span data-ttu-id="bb1ee-201">자세한 내용은 참조 [하는 방법: 상속 계층 구조 매핑](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-201">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
### <a name="inheritance-in-queries"></a><span data-ttu-id="bb1ee-202">쿼리의 상속</span><span class="sxs-lookup"><span data-stu-id="bb1ee-202">Inheritance in Queries</span></span>  
 <span data-ttu-id="bb1ee-203">C# 캐스트는 프로젝션에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="bb1ee-204">다른 위치에 사용된 캐스트는 변환되지 않고 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="bb1ee-205">SQL 함수 이름을 제외하고는 SQL에서는 사실상 CLR <xref:System.Convert>와 동일한 기능만 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="bb1ee-206">즉, SQL에서는 한 형식의 값을 다른 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="bb1ee-207">다른 형식과 동일한 비트를 재해석하는 개념이 없으므로 CLR 캐스트와 동일한 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="bb1ee-208">이 때문에 C# 캐스트는 로컬에서만 작동하며</span><span class="sxs-lookup"><span data-stu-id="bb1ee-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="bb1ee-209">원격으로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-209">It is not remoted.</span></span>  
  
 <span data-ttu-id="bb1ee-210">`is` 및 `as` 연산자와 `GetType` 메서드는 `Select` 연산자뿐 아니라</span><span class="sxs-lookup"><span data-stu-id="bb1ee-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="bb1ee-211">다른 쿼리 연산자에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-211">They can be used in other query operators also.</span></span>  
  
## <a name="sql-server-2008-support"></a><span data-ttu-id="bb1ee-212">SQL Server 2008 지원</span><span class="sxs-lookup"><span data-stu-id="bb1ee-212">SQL Server 2008 Support</span></span>  
 <span data-ttu-id="bb1ee-213">.NET Framework 3.5 SP1부터 LINQ to SQL에서는 SQL Server 2008에 새로 도입된 날짜 및 시간 형식에 대한 매핑이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="bb1ee-214">그러나 이러한 새로운 형식에 매핑된 값에 대한 연산을 수행할 때는 LINQ to SQL 쿼리 연산자에 대해 몇 가지 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>  
  
### <a name="unsupported-query-operators"></a><span data-ttu-id="bb1ee-215">지원되지 않는 쿼리 연산자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-215">Unsupported Query Operators</span></span>  
 <span data-ttu-id="bb1ee-216">다음 쿼리 연산자는 `DATETIME2`, `DATE`, `TIME` 및 `DATETIMEOFFSET` 등의 새로운 SQL Server 날짜 및 시간 형식에 매핑된 값에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>  
  
-   `Aggregate`  
  
-   `Average`  
  
-   `LastOrDefault`  
  
-   `OfType`  
  
-   `Sum`  
  
 <span data-ttu-id="bb1ee-217">이러한 SQL Server 날짜 및 시간 형식에 대 한 매핑에 대 한 자세한 내용은 참조 [SQL-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
## <a name="sql-server-2005-support"></a><span data-ttu-id="bb1ee-218">SQL Server 2005 지원</span><span class="sxs-lookup"><span data-stu-id="bb1ee-218">SQL Server 2005 Support</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-219">에서는 다음과 같은 SQL Server 2005 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-219"> does not support the following SQL Server 2005 features:</span></span>  
  
-   <span data-ttu-id="bb1ee-220">SQL CLR용으로 작성된 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="bb1ee-220">Stored procedures written for SQL CLR.</span></span>  
  
-   <span data-ttu-id="bb1ee-221">사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="bb1ee-221">User-defined type.</span></span>  
  
-   <span data-ttu-id="bb1ee-222">XML 쿼리 기능</span><span class="sxs-lookup"><span data-stu-id="bb1ee-222">XML query features.</span></span>  
  
## <a name="sql-server-2000-support"></a><span data-ttu-id="bb1ee-223">SQL Server 2000 지원</span><span class="sxs-lookup"><span data-stu-id="bb1ee-223">SQL Server 2000 Support</span></span>  
 <span data-ttu-id="bb1ee-224">[!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]와 달리 다음과 같은 [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)] 제한 사항이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-224">The following [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] limitations (compared to [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="bb1ee-225">Cross Apply 및 Outer Apply 연산자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-225">Cross Apply and Outer Apply Operators</span></span>  
 <span data-ttu-id="bb1ee-226">이러한 연산자는 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-226">These operators are not available in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bb1ee-227">에서는 일련의 다시 쓰기를 시도하여 해당 연산자를 적절한 조인으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-227"> tries a series of rewrites to replace them with appropriate joins.</span></span>  
  
 <span data-ttu-id="bb1ee-228">`Cross Apply` 및 `Outer Apply`는 관계 탐색을 위해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="bb1ee-229">이러한 다시 쓰기가 가능한 쿼리 집합은 잘 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="bb1ee-230">따라서 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]에서 지원되는 최소 쿼리 집합은 관계 탐색을 포함하지 않는 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-230">For this reason, the minimal set of queries that is supported for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] is the set that does not involve relationship navigation.</span></span>  
  
### <a name="text--ntext"></a><span data-ttu-id="bb1ee-231">text/ntext</span><span class="sxs-lookup"><span data-stu-id="bb1ee-231">text / ntext</span></span>  
 <span data-ttu-id="bb1ee-232">데이터 형식 `text`  /  `ntext` 에 대 한 특정 쿼리 작업에 사용할 수 없습니다 `varchar(max)`  /  `nvarchar(max)`에서 지원 되는 [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span></span>  
  
 <span data-ttu-id="bb1ee-233">이 제한에 대한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="bb1ee-234">특히 `Distinct()` 또는 `text` 열에 매핑된 멤버가 들어 있는 결과에서는 `ntext`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>  
  
### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="bb1ee-235">중첩된 쿼리에 의해 트리거되는 동작</span><span class="sxs-lookup"><span data-stu-id="bb1ee-235">Behavior Triggered by Nested Queries</span></span>  
 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]<span data-ttu-id="bb1ee-236">(SP4 이하) 바인더에는 중첩된 쿼리에 의해 트리거되는 몇 가지 고유한 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-236"> (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="bb1ee-237">이러한 작업을 트리거하는 SQL 쿼리 집합 제대로 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="bb1ee-238">따라서 SQL Server 예외를 일으킬 수 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 집합을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>  
  
### <a name="skip-and-take-operators"></a><span data-ttu-id="bb1ee-239">Skip 및 Take 연산자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-239">Skip and Take Operators</span></span>  
 <span data-ttu-id="bb1ee-240"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>에는 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]에 대한 쿼리에서 사용할 경우 몇 가지 제한이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> <span data-ttu-id="bb1ee-241">자세한 내용은 "Skip 및 Take 예외 SQL Server 2000에서 에서" 항목을 참조 하십시오. [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="object-materialization"></a><span data-ttu-id="bb1ee-242">개체 구체화</span><span class="sxs-lookup"><span data-stu-id="bb1ee-242">Object Materialization</span></span>  
 <span data-ttu-id="bb1ee-243">구체화에서는 하나 이상의 SQL 쿼리에서 반환한 행을 사용하여 CLR 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>  
  
-   <span data-ttu-id="bb1ee-244">다음과 같은 호출이 *로컬로 실행* 구체화의 일부로:</span><span class="sxs-lookup"><span data-stu-id="bb1ee-244">The following calls are *executed locally* as a part of materialization:</span></span>  
  
    -   <span data-ttu-id="bb1ee-245">생성자</span><span class="sxs-lookup"><span data-stu-id="bb1ee-245">Constructors</span></span>  
  
    -   <span data-ttu-id="bb1ee-246">프로젝션의 `ToString` 메서드</span><span class="sxs-lookup"><span data-stu-id="bb1ee-246">`ToString` methods in projections</span></span>  
  
    -   <span data-ttu-id="bb1ee-247">프로젝션의 형식 캐스트</span><span class="sxs-lookup"><span data-stu-id="bb1ee-247">Type casts in projections</span></span>  
  
-   <span data-ttu-id="bb1ee-248">다음 방법의 <xref:System.Linq.Enumerable.AsEnumerable%2A> 메서드가 *로컬로 실행*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="bb1ee-249">이 메서드는 즉시 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-249">This method does not cause immediate execution.</span></span>  
  
-   <span data-ttu-id="bb1ee-250">`struct`를 쿼리 결과의 반환 형식이나 결과 형식의 멤버로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="bb1ee-251">엔터티는 클래스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-251">Entities are required to be classes.</span></span> <span data-ttu-id="bb1ee-252">익명 형식은 클래스 인스턴스로 구체화되지만 명명된 구조체(비엔터티)는 프로젝션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>  
  
-   <span data-ttu-id="bb1ee-253">쿼리 결과에 대한 반환 형식의 멤버는 <xref:System.Linq.IQueryable%601> 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="bb1ee-254">이 멤버는 로컬 컬렉션으로 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb1ee-254">It is materialized as a local collection.</span></span>  
  
-   <span data-ttu-id="bb1ee-255">다음 메서드는 *즉시 구체화* 메서드에 적용 되는 시퀀스의:</span><span class="sxs-lookup"><span data-stu-id="bb1ee-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>  
  
    -   <xref:System.Linq.Enumerable.ToList%2A>  
  
    -   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
    -   <xref:System.Linq.Enumerable.ToArray%2A>  
  
## <a name="see-also"></a><span data-ttu-id="bb1ee-256">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb1ee-256">See Also</span></span>  
 [<span data-ttu-id="bb1ee-257">참조</span><span class="sxs-lookup"><span data-stu-id="bb1ee-257">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="bb1ee-258">시퀀스에서 요소 반환 또는 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="bb1ee-258">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 [<span data-ttu-id="bb1ee-259">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="bb1ee-259">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 [<span data-ttu-id="bb1ee-260">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-260">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 [<span data-ttu-id="bb1ee-261">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-261">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 [<span data-ttu-id="bb1ee-262">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="bb1ee-262">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)
