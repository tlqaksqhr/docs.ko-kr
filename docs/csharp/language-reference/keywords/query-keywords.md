---
title: "쿼리 키워드(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 30526e7bc4f99110d421855866381d9b7934d31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="0fb03-102">쿼리 키워드(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0fb03-102">Query Keywords (C# Reference)</span></span>
<span data-ttu-id="0fb03-103">이 섹션에는 쿼리 식에 사용되는 상황별 키워드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-103">This section contains the contextual keywords used in query expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fb03-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="0fb03-104">In This Section</span></span>  
  
|<span data-ttu-id="0fb03-105">절</span><span class="sxs-lookup"><span data-stu-id="0fb03-105">Clause</span></span>|<span data-ttu-id="0fb03-106">설명</span><span class="sxs-lookup"><span data-stu-id="0fb03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0fb03-107">from</span><span class="sxs-lookup"><span data-stu-id="0fb03-107">from</span></span>](../../../csharp/language-reference/keywords/from-clause.md)|<span data-ttu-id="0fb03-108">데이터 소스와 범위 변수(반복 변수와 유사함)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|  
|[<span data-ttu-id="0fb03-109">where</span><span class="sxs-lookup"><span data-stu-id="0fb03-109">where</span></span>](../../../csharp/language-reference/keywords/where-clause.md)|<span data-ttu-id="0fb03-110">논리적 AND 및 OR 연산자(`&&` 또는 <code>&#124;&#124;</code>)로 구분된 하나 이상의 부울 식을 기준으로 소스 요소를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|  
|[<span data-ttu-id="0fb03-111">select</span><span class="sxs-lookup"><span data-stu-id="0fb03-111">select</span></span>](../../../csharp/language-reference/keywords/select-clause.md)|<span data-ttu-id="0fb03-112">쿼리를 실행할 때 반환된 시퀀스의 요소에 사용할 형식 및 모양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|  
|[<span data-ttu-id="0fb03-113">group</span><span class="sxs-lookup"><span data-stu-id="0fb03-113">group</span></span>](../../../csharp/language-reference/keywords/group-clause.md)|<span data-ttu-id="0fb03-114">지정된 키 값에 따라 쿼리 결과를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-114">Groups query results according to a specified key value.</span></span>|  
|[<span data-ttu-id="0fb03-115">into</span><span class="sxs-lookup"><span data-stu-id="0fb03-115">into</span></span>](../../../csharp/language-reference/keywords/into.md)|<span data-ttu-id="0fb03-116">join, group 또는 select 절의 결과에 대한 참조로 사용할 수 있는 식별자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|  
|[<span data-ttu-id="0fb03-117">orderby</span><span class="sxs-lookup"><span data-stu-id="0fb03-117">orderby</span></span>](../../../csharp/language-reference/keywords/orderby-clause.md)|<span data-ttu-id="0fb03-118">요소 형식에 대한 기본 비교자에 따라 오름차순 또는 내림차순으로 쿼리 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|  
|[<span data-ttu-id="0fb03-119">join</span><span class="sxs-lookup"><span data-stu-id="0fb03-119">join</span></span>](../../../csharp/language-reference/keywords/join-clause.md)|<span data-ttu-id="0fb03-120">지정한 두 일치 조건 간의 같음 비교를 기반으로 하여 두 데이터 소스를 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|  
|[<span data-ttu-id="0fb03-121">let</span><span class="sxs-lookup"><span data-stu-id="0fb03-121">let</span></span>](../../../csharp/language-reference/keywords/let-clause.md)|<span data-ttu-id="0fb03-122">쿼리 식에 하위 식 결과를 저장할 범위 변수를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|  
|[<span data-ttu-id="0fb03-123">in</span><span class="sxs-lookup"><span data-stu-id="0fb03-123">in</span></span>](../../../csharp/language-reference/keywords/in.md)|<span data-ttu-id="0fb03-124">[join](../../../csharp/language-reference/keywords/join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-124">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0fb03-125">on</span><span class="sxs-lookup"><span data-stu-id="0fb03-125">on</span></span>](../../../csharp/language-reference/keywords/on.md)|<span data-ttu-id="0fb03-126">[join](../../../csharp/language-reference/keywords/join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-126">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0fb03-127">equals</span><span class="sxs-lookup"><span data-stu-id="0fb03-127">equals</span></span>](../../../csharp/language-reference/keywords/equals.md)|<span data-ttu-id="0fb03-128">[join](../../../csharp/language-reference/keywords/join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-128">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0fb03-129">by</span><span class="sxs-lookup"><span data-stu-id="0fb03-129">by</span></span>](../../../csharp/language-reference/keywords/by.md)|<span data-ttu-id="0fb03-130">[group](../../../csharp/language-reference/keywords/group-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-130">Contextual keyword in a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0fb03-131">ascending</span><span class="sxs-lookup"><span data-stu-id="0fb03-131">ascending</span></span>](../../../csharp/language-reference/keywords/ascending.md)|<span data-ttu-id="0fb03-132">[orderby](../../../csharp/language-reference/keywords/orderby-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-132">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0fb03-133">descending</span><span class="sxs-lookup"><span data-stu-id="0fb03-133">descending</span></span>](../../../csharp/language-reference/keywords/descending.md)|<span data-ttu-id="0fb03-134">[orderby](../../../csharp/language-reference/keywords/orderby-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb03-134">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fb03-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fb03-135">See Also</span></span>  
 [<span data-ttu-id="0fb03-136">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="0fb03-136">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0fb03-137">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="0fb03-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="0fb03-138">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="0fb03-138">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="0fb03-139">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="0fb03-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
