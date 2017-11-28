---
title: "쿼리 예제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e7d7a0a1f641603887675ed0c1faebd5c06b273
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="query-examples"></a><span data-ttu-id="82d32-102">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="82d32-102">Query Examples</span></span>
<span data-ttu-id="82d32-103">이 단원에서는 일반적인 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 쿼리에 대한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 및 C# 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="82d32-104">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자들은 샘플 단원에서 제공하는 샘플 솔루션에서 더 많은 예제를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="82d32-105">자세한 내용은 참조 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82d32-106">*db* 의 코드 예제에는 대개 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="82d32-107">*db* 인스턴스의 것으로 간주 되는 *Northwind* 클래스에서 상속 하는 <xref:System.Data.Linq.DataContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82d32-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="82d32-108">In This Section</span></span>  
 [<span data-ttu-id="82d32-109">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="82d32-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="82d32-110"><xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> 등의 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="82d32-111">시퀀스의 첫 번째 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="82d32-112"><xref:System.Linq.Enumerable.First%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-113">반환 또는 시퀀스의 건너뛰기 요소</span><span class="sxs-lookup"><span data-stu-id="82d32-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="82d32-114"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-115">시퀀스의 요소 정렬</span><span class="sxs-lookup"><span data-stu-id="82d32-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="82d32-116"><xref:System.Linq.Enumerable.OrderBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-117">시퀀스의 요소 그룹화</span><span class="sxs-lookup"><span data-stu-id="82d32-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="82d32-118"><xref:System.Linq.Enumerable.GroupBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-119">시퀀스에서 중복 요소 제거</span><span class="sxs-lookup"><span data-stu-id="82d32-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="82d32-120"><xref:System.Linq.Enumerable.Distinct%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-121">시퀀스의 일부 또는 모든 요소가 조건을 만족 하는 경우 확인</span><span class="sxs-lookup"><span data-stu-id="82d32-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="82d32-122"><xref:System.Linq.Enumerable.All%2A> 및 <xref:System.Linq.Enumerable.Any%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-123">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="82d32-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="82d32-124"><xref:System.Linq.Enumerable.Concat%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-125">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="82d32-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="82d32-126"><xref:System.Linq.Enumerable.Except%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-127">두 시퀀스의 교집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="82d32-128"><xref:System.Linq.Enumerable.Intersect%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-129">두 시퀀스의 합집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="82d32-130"><xref:System.Linq.Enumerable.Union%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-131">시퀀스를 배열로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="82d32-132"><xref:System.Linq.Enumerable.ToArray%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-133">제네릭 목록으로 시퀀스 변환</span><span class="sxs-lookup"><span data-stu-id="82d32-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="82d32-134"><xref:System.Linq.Enumerable.ToList%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-135">제네릭 IEnumerable로 형식 변환</span><span class="sxs-lookup"><span data-stu-id="82d32-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="82d32-136"><xref:System.Linq.Enumerable.AsEnumerable%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="82d32-137">조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="82d32-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="82d32-138">`from`, `where` 및 `select` 절에서 외래 키 탐색 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="82d32-139">프로젝션 작성</span><span class="sxs-lookup"><span data-stu-id="82d32-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="82d32-140">결합의 예제를 제공 `select` 과 기타 기능 (예를 들어 *익명 형식*) 쿼리 투영을 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82d32-141">관련 단원</span><span class="sxs-lookup"><span data-stu-id="82d32-141">Related Sections</span></span>  
 [<span data-ttu-id="82d32-142">표준 쿼리 연산자 개요</span><span class="sxs-lookup"><span data-stu-id="82d32-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="82d32-143">표준 쿼리 연산자의 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="82d32-144">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="82d32-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="82d32-145">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 개념이 쿼리에 어떻게 적용되는지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="82d32-146">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="82d32-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="82d32-147">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 관련 프로그래밍 개념을 설명하는 항목에 대한 포털을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82d32-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
