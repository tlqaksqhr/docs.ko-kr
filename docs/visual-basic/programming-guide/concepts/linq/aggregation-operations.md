---
title: "집계 작업 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d4b07eeb1d09d7db0f75d96629c816f66dbb128
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="e0e10-102">집계 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0e10-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="e0e10-103">집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="e0e10-104">예를 들어 1달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="e0e10-105">다음 그림은 숫자 시퀀스에 대한 두 가지 집계 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="e0e10-106">첫 번째 작업은 숫자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-106">The first operation sums the numbers.</span></span> <span data-ttu-id="e0e10-107">두 번째 작업은 시퀀스의 최대 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="e0e10-108">![LINQ 집계 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="e0e10-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="e0e10-109">다음 섹션에는 집계 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0e10-110">메서드</span><span class="sxs-lookup"><span data-stu-id="e0e10-110">Methods</span></span>  
  
|<span data-ttu-id="e0e10-111">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="e0e10-111">Method Name</span></span>|<span data-ttu-id="e0e10-112">설명</span><span class="sxs-lookup"><span data-stu-id="e0e10-112">Description</span></span>|<span data-ttu-id="e0e10-113">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="e0e10-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e0e10-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e0e10-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e0e10-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="e0e10-115">Aggregate</span></span>|<span data-ttu-id="e0e10-116">컬렉션 값에 대해 사용자 지정 집계 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="e0e10-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="e0e10-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-118">평균</span><span class="sxs-lookup"><span data-stu-id="e0e10-118">Average</span></span>|<span data-ttu-id="e0e10-119">값 컬렉션의 평균 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-120">개수</span><span class="sxs-lookup"><span data-stu-id="e0e10-120">Count</span></span>|<span data-ttu-id="e0e10-121">컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="e0e10-122">LongCount</span></span>|<span data-ttu-id="e0e10-123">큰 컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-124">최대</span><span class="sxs-lookup"><span data-stu-id="e0e10-124">Max</span></span>|<span data-ttu-id="e0e10-125">컬렉션의 최대값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-126">최소</span><span class="sxs-lookup"><span data-stu-id="e0e10-126">Min</span></span>|<span data-ttu-id="e0e10-127">컬렉션의 최소값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0e10-128">Sum</span><span class="sxs-lookup"><span data-stu-id="e0e10-128">Sum</span></span>|<span data-ttu-id="e0e10-129">컬렉션에 있는 값의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e0e10-130">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="e0e10-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="e0e10-131">Average</span><span class="sxs-lookup"><span data-stu-id="e0e10-131">Average</span></span>  
 <span data-ttu-id="e0e10-132">다음 코드 예제에서는 `Aggregate Into Average` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 기온을 나타내는 숫자의 배열에서 평균 기온을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-132">The following code example uses the `Aggregate Into Average` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a><span data-ttu-id="e0e10-133">개수</span><span class="sxs-lookup"><span data-stu-id="e0e10-133">Count</span></span>  
 <span data-ttu-id="e0e10-134">다음 코드 예제에서는 `Aggregate Into Count` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 80 보다 크거나 있는 배열에 있는 값의 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-134">The following code example uses the `Aggregate Into Count` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a><span data-ttu-id="e0e10-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="e0e10-135">LongCount</span></span>  
 <span data-ttu-id="e0e10-136">다음 코드 예제에서는 `Aggregate Into LongCount` 절 배열에 있는 값의 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a><span data-ttu-id="e0e10-137">최대</span><span class="sxs-lookup"><span data-stu-id="e0e10-137">Max</span></span>  
 <span data-ttu-id="e0e10-138">다음 코드 예제에서는 `Aggregate Into Max` 절 기온을 나타내는 숫자의 배열에서 최대 기온을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e10-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a><span data-ttu-id="e0e10-139">최소</span><span class="sxs-lookup"><span data-stu-id="e0e10-139">Min</span></span>  
 <span data-ttu-id="e0e10-140">다음 코드 예제에서는 `Aggregate Into Min` 기온을 나타내는 숫자의 배열에 최소 온도 계산 하는 절.</span><span class="sxs-lookup"><span data-stu-id="e0e10-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a><span data-ttu-id="e0e10-141">Sum</span><span class="sxs-lookup"><span data-stu-id="e0e10-141">Sum</span></span>  
 <span data-ttu-id="e0e10-142">다음 코드 예제에서는 `Aggregate Into Sum` 비용을 나타내는 값의 배열에서 총 비용 금액을 계산 하는 절.</span><span class="sxs-lookup"><span data-stu-id="e0e10-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e0e10-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0e10-143">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="e0e10-144">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0e10-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="e0e10-145">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="e0e10-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="e0e10-146">방법: CSV 텍스트 파일 (LINQ) (Visual Basic)의 열 값 계산</span><span class="sxs-lookup"><span data-stu-id="e0e10-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 [<span data-ttu-id="e0e10-147">방법: 데이터 개수, 합 또는 평균 계산</span><span class="sxs-lookup"><span data-stu-id="e0e10-147">How to: Count, Sum, or Average Data</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)  
 [<span data-ttu-id="e0e10-148">방법: 쿼리 결과의 최소값 또는 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="e0e10-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
 [<span data-ttu-id="e0e10-149">방법: 파일 또는 파일 (LINQ) (Visual Basic) 디렉터리 트리에서 가장 큰 값에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="e0e10-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 [<span data-ttu-id="e0e10-150">방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="e0e10-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
