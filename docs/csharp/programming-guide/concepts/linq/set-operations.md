---
title: 집합 작업(C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 45b828f89b380b2649ab5ee80f5438d822de9443
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="set-operations-c"></a><span data-ttu-id="3e662-102">집합 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="3e662-102">Set Operations (C#)</span></span>
<span data-ttu-id="3e662-103">LINQ의 집합 작업은 동일 컬렉션이나 별개 컬렉션(또는 집합)에 동등한 요소가 있는지 여부에 따라 결과 집합을 생성하는 쿼리 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="3e662-104">다음 섹션에는 집합 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e662-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3e662-105">Methods</span></span>  
  
|<span data-ttu-id="3e662-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="3e662-106">Method Name</span></span>|<span data-ttu-id="3e662-107">설명</span><span class="sxs-lookup"><span data-stu-id="3e662-107">Description</span></span>|<span data-ttu-id="3e662-108">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="3e662-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="3e662-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3e662-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="3e662-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="3e662-110">Distinct</span></span>|<span data-ttu-id="3e662-111">컬렉션에서 중복 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="3e662-112">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="3e662-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3e662-113">제외</span><span class="sxs-lookup"><span data-stu-id="3e662-113">Except</span></span>|<span data-ttu-id="3e662-114">두 번째 컬렉션에 표시되지 않는 한 컬렉션의 요소를 의미하는 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="3e662-115">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="3e662-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3e662-116">교차</span><span class="sxs-lookup"><span data-stu-id="3e662-116">Intersect</span></span>|<span data-ttu-id="3e662-117">두 컬렉션에 각각 표시되는 요소를 의미하는 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="3e662-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="3e662-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3e662-119">공용 구조체</span><span class="sxs-lookup"><span data-stu-id="3e662-119">Union</span></span>|<span data-ttu-id="3e662-120">두 컬렉션 중 하나에 표시되는 고유한 요소를 의미하는 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="3e662-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="3e662-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="3e662-122">집합 작업 비교</span><span class="sxs-lookup"><span data-stu-id="3e662-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="3e662-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="3e662-123">Distinct</span></span>  
 <span data-ttu-id="3e662-124">다음 그림에서는 문자 시퀀스에 대한 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 메서드의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="3e662-125">반환된 시퀀스에는 입력 시퀀스의 고유한 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="3e662-126">![Distinct&#40;&#41;의 동작을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="3e662-126">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="3e662-127">제외</span><span class="sxs-lookup"><span data-stu-id="3e662-127">Except</span></span>  
 <span data-ttu-id="3e662-128">다음 그림에서는 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3e662-129">반환된 시퀀스에는 두 번째 입력 시퀀스에 없는 첫 번째 입력 시퀀스의 요소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="3e662-130">![Except&#40;&#41;의 작업을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="3e662-130">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="3e662-131">교차</span><span class="sxs-lookup"><span data-stu-id="3e662-131">Intersect</span></span>  
 <span data-ttu-id="3e662-132">다음 그림에서는 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3e662-133">반환된 시퀀스에는 입력 시퀀스 둘 다에 공통적으로 있는 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="3e662-134">![두 시퀀스의 교집합을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="3e662-134">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="3e662-135">공용 구조체</span><span class="sxs-lookup"><span data-stu-id="3e662-135">Union</span></span>  
 <span data-ttu-id="3e662-136">다음 그림은 두 개의 문자 시퀀스에 대한 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="3e662-137">반환된 시퀀스에는 두 입력 시퀀스의 고유한 요소가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e662-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="3e662-138">![두 시퀀스의 합집합을 보여주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="3e662-138">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e662-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e662-139">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="3e662-140">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="3e662-140">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="3e662-141">방법: 문자열 컬렉션 결합 및 비교(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="3e662-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 [<span data-ttu-id="3e662-142">방법: 두 목록 간의 차집합 구하기(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="3e662-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
