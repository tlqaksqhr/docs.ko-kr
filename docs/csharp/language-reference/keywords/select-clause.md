---
title: select 절(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: 6e7277b5d714e48059fe1ed7e8b85e46a14a840c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279986"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="28239-102">select 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="28239-102">select clause (C# Reference)</span></span>
<span data-ttu-id="28239-103">쿼리 식에서 `select` 절은 쿼리를 실행할 때 생성되는 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="28239-104">결과는 모든 이전 절의 평가와 `select` 절 자체의 모든 계산을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="28239-105">쿼리 식은 `select` 절이나 [group](../../../csharp/language-reference/keywords/group-clause.md) 절로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="28239-106">다음 예제에서는 쿼리 식의 간단한 `select` 절을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28239-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 <span data-ttu-id="28239-107">`select` 절에서 생성된 시퀀스의 형식에 따라 쿼리 변수 `queryHighScores`의 형식이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="28239-107">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="28239-108">가장 단순한 경우에서는 `select` 절이 범위 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-108">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="28239-109">이렇게 하면 반환된 시퀀스에 데이터 소스와 동일한 형식의 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28239-109">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="28239-110">자세한 내용은 [LINQ 쿼리 작업의 형식 관계](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28239-110">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="28239-111">그러나 `select` 절은 소스 데이터를 새 형식으로 변환(또는 *프로젝션*)하기 위한 강력한 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-111">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="28239-112">자세한 내용은 [LINQ를 통한 데이터 변환(C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28239-112">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28239-113">예</span><span class="sxs-lookup"><span data-stu-id="28239-113">Example</span></span>  
 <span data-ttu-id="28239-114">다음 예제에서는 `select` 절에 사용할 수 있는 모든 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28239-114">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="28239-115">각 쿼리에서 `select` 절과 *쿼리 변수* 형식(`studentQuery1`, `studentQuery2` 등) 간의 관계를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28239-115">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 <span data-ttu-id="28239-116">앞의 예제에서 `studentQuery8`에 표시된 대로 반환된 시퀀스의 요소에 소스 요소의 속성 하위 집합만 포함하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28239-116">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="28239-117">반환된 시퀀스를 최대한 작게 유지하면 메모리 요구 사항을 줄이고 쿼리 실행 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28239-117">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="28239-118">`select` 절에서 무명 형식을 만들고 개체 이니셜라이저를 사용하여 소스 요소의 적절한 속성으로 초기화하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28239-118">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="28239-119">이 작업을 수행하는 방법의 예를 보려면 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28239-119">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28239-120">설명</span><span class="sxs-lookup"><span data-stu-id="28239-120">Remarks</span></span>  
 <span data-ttu-id="28239-121">컴파일 시간에 `select` 절은 <xref:System.Linq.Enumerable.Select%2A> 표준 쿼리 연산자에 대한 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="28239-121">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28239-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28239-122">See Also</span></span>  
 [<span data-ttu-id="28239-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="28239-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="28239-124">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="28239-124">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="28239-125">from 절</span><span class="sxs-lookup"><span data-stu-id="28239-125">from clause</span></span>](../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="28239-126">partial(메서드)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="28239-126">partial (Method) (C# Reference)</span></span>](../../../csharp/language-reference/keywords/partial-method.md)  
 [<span data-ttu-id="28239-127">익명 형식</span><span class="sxs-lookup"><span data-stu-id="28239-127">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="28239-128">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="28239-128">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="28239-129">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="28239-129">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
