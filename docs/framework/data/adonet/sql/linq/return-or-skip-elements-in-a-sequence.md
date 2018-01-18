---
title: "시퀀스에서 요소 반환 또는 건너뛰기"
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
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b5d52fd3326448c428dac16c210321889f83ea23
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="return-or-skip-elements-in-a-sequence"></a><span data-ttu-id="4f3b4-102">시퀀스에서 요소 반환 또는 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="4f3b4-102">Return Or Skip Elements in a Sequence</span></span>
<span data-ttu-id="4f3b4-103"><xref:System.Linq.Queryable.Take%2A> 연산자를 사용하여 지정된 수의 시퀀스 요소를 반환한 다음 나머지는 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-103">Use the <xref:System.Linq.Queryable.Take%2A> operator to return a given number of elements in a sequence and then skip over the remainder.</span></span>  
  
 <span data-ttu-id="4f3b4-104"><xref:System.Linq.Queryable.Skip%2A> 연산자를 사용하여 지정된 수의 시퀀스 요소를 건너뛴 다음 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-104">Use the <xref:System.Linq.Queryable.Skip%2A> operator to skip over a given number of elements in a sequence and then return the remainder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f3b4-105"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A>에는 SQL Server 2000에 대한 쿼리에서 사용할 경우 몇 가지 제한이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-105"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="4f3b4-106">자세한 내용은 "Skip 및 Take 예외 SQL Server 2000에서 에서" 항목을 참조 하십시오. [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-106">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f3b4-107">에서는 하위 쿼리와 함께 SQL <xref:System.Linq.Queryable.Skip%2A> 절을 사용하여 `NOT EXISTS`을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-107"> translates <xref:System.Linq.Queryable.Skip%2A> by using a subquery with the SQL `NOT EXISTS` clause.</span></span> <span data-ttu-id="4f3b4-108">이 변환에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-108">This translation has the following limitations:</span></span>  
  
-   <span data-ttu-id="4f3b4-109">인수는 집합이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-109">The argument must be a set.</span></span> <span data-ttu-id="4f3b4-110">다중 집합은 정렬된 경우에도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-110">Multisets are not supported, even if ordered.</span></span>  
  
-   <span data-ttu-id="4f3b4-111">생성된 쿼리는 <xref:System.Linq.Queryable.Skip%2A>이 적용된 기본 쿼리에 대해 생성된 쿼리보다 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-111">The generated query can be much more complex than the query generated for the base query on which <xref:System.Linq.Queryable.Skip%2A> is applied.</span></span> <span data-ttu-id="4f3b4-112">이러한 복잡성은 성능을 감소시키거나 시간이 초과될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-112">This complexity can cause decrease in performance or even a time-out.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f3b4-113">예</span><span class="sxs-lookup"><span data-stu-id="4f3b4-113">Example</span></span>  
 <span data-ttu-id="4f3b4-114">다음 예제에서는 `Take`를 사용하여 고용된 처음 다섯 명의 `Employees`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-114">The following example uses `Take` to select the first five `Employees` hired.</span></span> <span data-ttu-id="4f3b4-115">컬렉션은 우선 `HireDate`로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-115">Note that the collection is first sorted by `HireDate`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="4f3b4-116">예</span><span class="sxs-lookup"><span data-stu-id="4f3b4-116">Example</span></span>  
 <span data-ttu-id="4f3b4-117">다음 예제에서는 <xref:System.Linq.Queryable.Skip%2A>을 사용하여 10개의 가장 비싼 `Products`를 제외한 모두를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-117">The following example uses <xref:System.Linq.Queryable.Skip%2A> to select all except the 10 most expensive `Products`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="4f3b4-118">예</span><span class="sxs-lookup"><span data-stu-id="4f3b4-118">Example</span></span>  
 <span data-ttu-id="4f3b4-119">다음 예제에서는 <xref:System.Linq.Queryable.Skip%2A>과 <xref:System.Linq.Queryable.Take%2A> 메서드를 결합하여 처음 50개의 레코드를 건너뛴 다음 그 이후 10개의 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-119">The following example combines the <xref:System.Linq.Queryable.Skip%2A> and <xref:System.Linq.Queryable.Take%2A> methods to skip the first 50 records and then return the next 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 <span data-ttu-id="4f3b4-120"><xref:System.Linq.Queryable.Take%2A> 및 <xref:System.Linq.Queryable.Skip%2A> 작업은 정렬된 집합에 대해서만 제대로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-120"><xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> operations are well defined only against ordered sets.</span></span> <span data-ttu-id="4f3b4-121">정렬되지 않는 집합 또는 다중 집합에 대한 의미는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-121">The semantics for unordered sets or multisets is undefined.</span></span>  
  
 <span data-ttu-id="4f3b4-122">SQL의 정렬에 대한 제한 사항 때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 <xref:System.Linq.Queryable.Take%2A> 또는 <xref:System.Linq.Queryable.Skip%2A> 연산자의 정렬 인수가 연산자의 결과로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-122">Because of the limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of the <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> operator to the result of the operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f3b4-123">[!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]과 [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)]의 변환은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-123">Translation is different for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] and [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span> <span data-ttu-id="4f3b4-124">복잡한 쿼리와 함께 <xref:System.Linq.Queryable.Skip%2A>을 사용하려면 [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)]를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-124">If you plan to use <xref:System.Linq.Queryable.Skip%2A> with a query of any complexity, use [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span>  
  
 <span data-ttu-id="4f3b4-125">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대해 다음 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] 쿼리를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-125">Consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f3b4-126">에서는 다음과 같이 정렬을 SQL 코드의 끝 부분으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-126"> moves the ordering to the end in the SQL code, as follows:</span></span>  
  
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
  
 <span data-ttu-id="4f3b4-127"><xref:System.Linq.Queryable.Take%2A>과 <xref:System.Linq.Queryable.Skip%2A>을 함께 연결하면 모든 지정된 정렬이 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-127">When <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are chained together, all the specified ordering must be consistent.</span></span> <span data-ttu-id="4f3b4-128">그렇지 않으면 결과가 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-128">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="4f3b4-129">SQL 사양을 기반으로 하는 정수 계열 상수 인수로 음수가 아닌 경우 <xref:System.Linq.Queryable.Take%2A>과 <xref:System.Linq.Queryable.Skip%2A>은 제대로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f3b4-129">For non-negative, constant integral arguments based on the SQL specification, both <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are well-defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3b4-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f3b4-130">See Also</span></span>  
 [<span data-ttu-id="4f3b4-131">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="4f3b4-131">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="4f3b4-132">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="4f3b4-132">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
