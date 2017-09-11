---
title: "집계 작업(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6c453bdccdb3af026fe4f4fb79c6e33e44e7a8f0
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="aggregation-operations-c"></a><span data-ttu-id="a1b1b-102">집계 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="a1b1b-102">Aggregation Operations (C#)</span></span>
<span data-ttu-id="a1b1b-103">집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="a1b1b-104">예를 들어 1달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="a1b1b-105">다음 그림은 숫자 시퀀스에 대한 두 가지 집계 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="a1b1b-106">첫 번째 작업은 숫자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-106">The first operation sums the numbers.</span></span> <span data-ttu-id="a1b1b-107">두 번째 작업은 시퀀스의 최대 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="a1b1b-108">![LINQ 집계 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="a1b1b-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="a1b1b-109">다음 섹션에는 집계 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1b1b-110">메서드</span><span class="sxs-lookup"><span data-stu-id="a1b1b-110">Methods</span></span>  
  
|<span data-ttu-id="a1b1b-111">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="a1b1b-111">Method Name</span></span>|<span data-ttu-id="a1b1b-112">설명</span><span class="sxs-lookup"><span data-stu-id="a1b1b-112">Description</span></span>|<span data-ttu-id="a1b1b-113">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="a1b1b-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="a1b1b-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a1b1b-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="a1b1b-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="a1b1b-115">Aggregate</span></span>|<span data-ttu-id="a1b1b-116">컬렉션 값에 대해 사용자 지정 집계 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="a1b1b-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-118">평균</span><span class="sxs-lookup"><span data-stu-id="a1b1b-118">Average</span></span>|<span data-ttu-id="a1b1b-119">값 컬렉션의 평균 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-119">Calculates the average value of a collection of values.</span></span>|<span data-ttu-id="a1b1b-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-121">개수</span><span class="sxs-lookup"><span data-stu-id="a1b1b-121">Count</span></span>|<span data-ttu-id="a1b1b-122">컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="a1b1b-123">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="a1b1b-124">LongCount</span></span>|<span data-ttu-id="a1b1b-125">큰 컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-125">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="a1b1b-126">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-127">최대</span><span class="sxs-lookup"><span data-stu-id="a1b1b-127">Max</span></span>|<span data-ttu-id="a1b1b-128">컬렉션의 최대값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-128">Determines the maximum value in a collection.</span></span>|<span data-ttu-id="a1b1b-129">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-130">최소</span><span class="sxs-lookup"><span data-stu-id="a1b1b-130">Min</span></span>|<span data-ttu-id="a1b1b-131">컬렉션의 최소값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-131">Determines the minimum value in a collection.</span></span>|<span data-ttu-id="a1b1b-132">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|<span data-ttu-id="a1b1b-133">Sum</span><span class="sxs-lookup"><span data-stu-id="a1b1b-133">Sum</span></span>|<span data-ttu-id="a1b1b-134">컬렉션에 있는 값의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-134">Calculates the sum of the values in a collection.</span></span>|<span data-ttu-id="a1b1b-135">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a1b1b-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="a1b1b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b1b-136">See Also</span></span>  
 <span data-ttu-id="a1b1b-137"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="a1b1b-137"><xref:System.Linq></span></span>   
 <span data-ttu-id="a1b1b-138">[표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="a1b1b-138">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="a1b1b-139">[방법: CSV 텍스트 파일의 열 값 계산(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span><span class="sxs-lookup"><span data-stu-id="a1b1b-139">[How to: Compute Column Values in a CSV Text File (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span></span>  
 <span data-ttu-id="a1b1b-140">[방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span><span class="sxs-lookup"><span data-stu-id="a1b1b-140">[How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span></span>  
 [<span data-ttu-id="a1b1b-141">방법: 폴더 집합의 전체 바이트 수 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="a1b1b-141">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)

