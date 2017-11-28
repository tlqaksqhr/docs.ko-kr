---
title: "Order By 절(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="b3e9f-102">Order By 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e9f-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="b3e9f-103">쿼리 결과 대 한 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3e9f-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b3e9f-105">요소</span><span class="sxs-lookup"><span data-stu-id="b3e9f-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="b3e9f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-106">Required.</span></span> <span data-ttu-id="b3e9f-107">하나 이상의 필드에서 현재 쿼리 결과 반환 된 값을 정렬 하는 방법을 식별 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="b3e9f-108">필드 이름은 쉼표 (,)로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="b3e9f-109">오름차순 또는 사용 하 여 순서를 내림차순으로 정렬 되어 각 필드를 식별할 수 있습니다는 `Ascending` 또는 `Descending` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="b3e9f-110">없는 경우 `Ascending` 또는 `Descending` 키워드가 지정 되어, 기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="b3e9f-111">정렬 순서 필드에는 우선 순위가 왼쪽에서 오른쪽으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3e9f-112">설명</span><span class="sxs-lookup"><span data-stu-id="b3e9f-112">Remarks</span></span>  
 <span data-ttu-id="b3e9f-113">사용할 수는 `Order By` 절을 쿼리의 결과 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="b3e9f-114">`Order By` 절만 현재 범위에 대 한 범위 변수는 결과 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="b3e9f-115">예를 들어는 `Select` 절에는 해당 범위에 대 한 새 반복 변수를 사용 하는 쿼리 식에 새 범위를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="b3e9f-116">범위 변수 앞에 정의 된 `Select` 쿼리의 절 뒤에 사용할 수 없는 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="b3e9f-117">따라서에서 사용할 수 있는 필드를 기준으로 결과 정렬 하려는 경우는 `Select` 두어야 절은 `Order By` 하기 전에 절은 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="b3e9f-118">한 예는 쿼리 결과의 일부로 반환 되는 필드에서 정렬 하려는 경우이 작업을 수행 해야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="b3e9f-119">오름차순 또는 내림차순 키를 누른 채 필드의 구현에 의해 결정 됩니다는 <xref:System.IComparable> 필드의 데이터 형식에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="b3e9f-120">데이터 형식을 구현 하지 않는 경우는 <xref:System.IComparable> 인터페이스, 정렬 순서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e9f-121">예제</span><span class="sxs-lookup"><span data-stu-id="b3e9f-121">Example</span></span>  
 <span data-ttu-id="b3e9f-122">다음 쿼리는 사용 되는 식은 `From` 범위 변수를 선언 하는 절 `book` 에 대 한는 `books` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="b3e9f-123">`Order By` 절 오름차순 (기본값) 가격으로 쿼리 결과 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="b3e9f-124">같은 가격으로 책 제목을 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="b3e9f-125">`Select` 선택 하는 절은 `Title` 및 `Price` 쿼리에서 반환 된 값으로 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="b3e9f-126">예제</span><span class="sxs-lookup"><span data-stu-id="b3e9f-126">Example</span></span>  
 <span data-ttu-id="b3e9f-127">다음 쿼리 식에 사용 된 `Order By` 가격을 내림차순으로 쿼리 결과 정렬 하는 절.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="b3e9f-128">같은 가격으로 책 제목을 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="b3e9f-129">예제</span><span class="sxs-lookup"><span data-stu-id="b3e9f-129">Example</span></span>  
 <span data-ttu-id="b3e9f-130">다음 쿼리 식에 사용 된 `Select` 책 제목을 선택, 가격, 날짜, 게시 및 제작 하는 절.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="b3e9f-131">다음 채웁니다는 `Title`, `Price`, `PublishDate`, 및 `Author` 새 범위에 대 한 범위 변수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="b3e9f-132">`Order By` 절에 새 범위 변수 작성자 이름, 책 제목 및 price로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="b3e9f-133">각 열 (오름차순) 기본 순서로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e9f-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b3e9f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3e9f-134">See Also</span></span>  
 [<span data-ttu-id="b3e9f-135">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="b3e9f-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b3e9f-136">쿼리</span><span class="sxs-lookup"><span data-stu-id="b3e9f-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b3e9f-137">Select 절</span><span class="sxs-lookup"><span data-stu-id="b3e9f-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b3e9f-138">From 절</span><span class="sxs-lookup"><span data-stu-id="b3e9f-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
