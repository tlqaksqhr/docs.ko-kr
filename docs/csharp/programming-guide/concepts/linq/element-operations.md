---
title: "요소 작업(C#)"
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
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
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
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a><span data-ttu-id="ba52a-102">요소 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="ba52a-102">Element Operations (C#)</span></span>
<span data-ttu-id="ba52a-103">요소 작업은 시퀀스에서 특정 단일 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-103">Element operations return a single, specific element from a sequence.</span></span>  
  
 <span data-ttu-id="ba52a-104">다음 섹션에는 요소 작업을 수행하는 표준 쿼리 연산자 메서드가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-104">The standard query operator methods that perform element operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba52a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ba52a-105">Methods</span></span>  
  
|<span data-ttu-id="ba52a-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="ba52a-106">Method Name</span></span>|<span data-ttu-id="ba52a-107">설명</span><span class="sxs-lookup"><span data-stu-id="ba52a-107">Description</span></span>|<span data-ttu-id="ba52a-108">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="ba52a-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="ba52a-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ba52a-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ba52a-110">ElementAt</span><span class="sxs-lookup"><span data-stu-id="ba52a-110">ElementAt</span></span>|<span data-ttu-id="ba52a-111">컬렉션의 지정된 인덱스에 있는 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-111">Returns the element at a specified index in a collection.</span></span>|<span data-ttu-id="ba52a-112">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-113">ElementAtOrDefault</span><span class="sxs-lookup"><span data-stu-id="ba52a-113">ElementAtOrDefault</span></span>|<span data-ttu-id="ba52a-114">컬렉션의 지정된 인덱스에 있는 요소를 반환하거나 인덱스가 범위를 벗어나면 기본값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-114">Returns the element at a specified index in a collection or a default value if the index is out of range.</span></span>|<span data-ttu-id="ba52a-115">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-116">First</span><span class="sxs-lookup"><span data-stu-id="ba52a-116">First</span></span>|<span data-ttu-id="ba52a-117">컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-117">Returns the first element of a collection, or the first element that satisfies a condition.</span></span>|<span data-ttu-id="ba52a-118">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-119">FirstOrDefault</span><span class="sxs-lookup"><span data-stu-id="ba52a-119">FirstOrDefault</span></span>|<span data-ttu-id="ba52a-120">컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-120">Returns the first element of a collection, or the first element that satisfies a condition.</span></span> <span data-ttu-id="ba52a-121">이러한 요소가 없으면 기본값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-121">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="ba52a-122">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-123">마지막</span><span class="sxs-lookup"><span data-stu-id="ba52a-123">Last</span></span>|<span data-ttu-id="ba52a-124">컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-124">Returns the last element of a collection, or the last element that satisfies a condition.</span></span>|<span data-ttu-id="ba52a-125">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-126">LastOrDefault</span><span class="sxs-lookup"><span data-stu-id="ba52a-126">LastOrDefault</span></span>|<span data-ttu-id="ba52a-127">컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-127">Returns the last element of a collection, or the last element that satisfies a condition.</span></span> <span data-ttu-id="ba52a-128">이러한 요소가 없으면 기본값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-128">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="ba52a-129">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-130">Single</span><span class="sxs-lookup"><span data-stu-id="ba52a-130">Single</span></span>|<span data-ttu-id="ba52a-131">컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-131">Returns the only element of a collection, or the only element that satisfies a condition.</span></span>|<span data-ttu-id="ba52a-132">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|<span data-ttu-id="ba52a-133">SingleOrDefault</span><span class="sxs-lookup"><span data-stu-id="ba52a-133">SingleOrDefault</span></span>|<span data-ttu-id="ba52a-134">컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-134">Returns the only element of a collection, or the only element that satisfies a condition.</span></span> <span data-ttu-id="ba52a-135">이러한 요소가 없거나 컬렉션에 정확히 하나의 요소가 포함되지 않은 경우 기본값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba52a-135">Returns a default value if no such element exists or the collection does not contain exactly one element.</span></span>|<span data-ttu-id="ba52a-136">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ba52a-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="ba52a-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba52a-137">See Also</span></span>  
 <span data-ttu-id="ba52a-138"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="ba52a-138"><xref:System.Linq></span></span>   
 <span data-ttu-id="ba52a-139">[표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ba52a-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="ba52a-140">방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="ba52a-140">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

