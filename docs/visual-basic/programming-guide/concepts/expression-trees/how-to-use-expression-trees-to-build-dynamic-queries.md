---
title: "방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic) 빌드 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="304f1-102">방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic) 빌드</span><span class="sxs-lookup"><span data-stu-id="304f1-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>
<span data-ttu-id="304f1-103">Linq에서는 식 트리는 소스를 나타내는 구조화 된 쿼리를 해당 대상 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> 를 구현 하는 데이터의 사용</span><span class="sxs-lookup"><span data-stu-id="304f1-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="304f1-104">예를 들어, LINQ 공급자 구현에서 <xref:System.Linq.IQueryable%601>관계형 데이터 저장소를 쿼리 하기 위한 인터페이스입니다.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="304f1-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="304f1-105">Visual Basic 컴파일러는 런타임에 식 트리를 작성 하는 코드에 이러한 데이터 소스를 대상으로 하는 쿼리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="304f1-106">그런 다음 쿼리 공급자 식 트리 데이터 구조를 탐색 하 고 데이터 원본에 대 한 적절 한 쿼리 언어로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="304f1-107"><xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> 형식의 변수에 할당 된 람다 식을 나타내는 데 LINQ 식 트리는 또한 사용</span><span class="sxs-lookup"><span data-stu-id="304f1-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="304f1-108">이 항목에서는 동적 LINQ 쿼리를 만드는 식 트리를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="304f1-109">동적 쿼리는 컴파일 시 쿼리의 세부 사항을 알 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="304f1-110">예를 들어, 응용 프로그램은 최종 사용자는 데이터를 필터링 하는 하나 이상의 조건자를 지정할 수 있게 하는 사용자 인터페이스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="304f1-111">LINQ 쿼리를 사용 하려면 이러한 유형의 응용 프로그램에서 런타임에 LINQ 쿼리를 만드는 식 트리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="304f1-112">예제</span><span class="sxs-lookup"><span data-stu-id="304f1-112">Example</span></span>  
 <span data-ttu-id="304f1-113">다음 예제에서는 식 트리 생성에 대 한 쿼리를 사용 하는 방법을 보여 줍니다.는 `IQueryable` 데이터 소스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="304f1-114">코드는 다음 쿼리를 나타내는 식 트리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 <span data-ttu-id="304f1-115">팩터리 메서드는 <xref:System.Linq.Expressions>네임 스페이스는 전체 쿼리를 구성 하는 식을 나타내는 식 트리를 만드는 데 사용 됩니다.</xref:System.Linq.Expressions></span><span class="sxs-lookup"><span data-stu-id="304f1-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="304f1-116">표준 쿼리 연산자 메서드 호출을 나타내는 식 참조는 <xref:System.Linq.Queryable>이러한 메서드의 구현입니다.</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="304f1-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="304f1-117">최종 식 트리가 전달 되는 <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>의 공급자 구현에서 `IQueryable` 형식의 실행 가능한 쿼리를 만들 때 데이터 원본 `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29></span><span class="sxs-lookup"><span data-stu-id="304f1-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="304f1-118">결과 해당 쿼리 변수를 열거 하 여 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-118">The results are obtained by enumerating that query variable.</span></span>  
  
<span data-ttu-id="304f1-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="304f1-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="304f1-120">이 코드는 고정된 된 수의 식에 전달 되는 조건자에 사용 하 여는 `Queryable.Where` 메서드.</span><span class="sxs-lookup"><span data-stu-id="304f1-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="304f1-121">그러나 사용자 입력에 의존 하는 조건자 식의 변수 숫자를 결합 하는 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="304f1-122">사용자의 입력에 따라 쿼리에서 호출 된 표준 쿼리 연산자를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="304f1-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="304f1-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="304f1-124">새 **콘솔 응용 프로그램** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-124">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="304f1-125">아직 참조 하지 않는 경우 System.Core.dll에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-125">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="304f1-126">System.Linq.Expressions 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-126">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="304f1-127">이 예제에서 코드를 복사 하 고 붙여 넣습니다는 `Main` `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="304f1-127">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304f1-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="304f1-128">See Also</span></span>  
 <span data-ttu-id="304f1-129">[식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="304f1-129">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="304f1-130"> [방법: 식 트리 (Visual Basic)를 실행 합니다.](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="304f1-130"> [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
