---
title: "LINQ to XML에서 지연된 실행 및 지연 계산(C#)"
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
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10ecebc2563df5a12b71a743727b1be21b19b671
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a><span data-ttu-id="d0902-102">LINQ to XML에서 지연된 실행 및 지연 계산(C#)</span><span class="sxs-lookup"><span data-stu-id="d0902-102">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>
<span data-ttu-id="d0902-103">쿼리 및 축 연산은 흔히 지연된 실행을 사용하도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="d0902-104">이 항목에서는 지연된 실행의 요구 사항 및 장점과 몇 가지 구현 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="d0902-105">지연된 실행</span><span class="sxs-lookup"><span data-stu-id="d0902-105">Deferred Execution</span></span>  
 <span data-ttu-id="d0902-106">지연된 실행은 *실현된* 값이 실제로 필요할 때까지 식의 계산이 지연되는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="d0902-107">지연된 실행은 특히 일련의 연결된 쿼리나 조작이 포함된 프로그램에서 큰 데이터 컬렉션을 조작해야 하는 경우 성능을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="d0902-108">최상의 경우에는 지연된 실행을 통해 소스 컬렉션을 한 번만 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="d0902-109">LINQ 기술은 <xref:System.Linq?displayProperty=fullName>와 같은 다양한 LINQ 네임스페이스의 확장 메서드와 핵심 <xref:System.Xml.Linq.Extensions?displayProperty=fullName> 클래스의 멤버에서 지연된 실행을 광범위하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=fullName> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="d0902-110">지연된 실행은 반복기 블록에서 사용될 때 C# 언어에서 [yield](../../../../csharp/language-reference/keywords/yield.md) 키워드(`yield-return` 문의 형태)로 직접 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-110">Deferred execution is supported directly in the C# language by the [yield](../../../../csharp/language-reference/keywords/yield.md) keyword (in the form of the `yield-return` statement) when used within an iterator block.</span></span> <span data-ttu-id="d0902-111">이러한 반복기는 <xref:System.Collections.IEnumerator> 또는 <xref:System.Collections.Generic.IEnumerator%601> 형식(또는 파생 형식)의 컬렉션을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-111">Such an iterator must return a collection of type <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> (or a derived type).</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="d0902-112">즉시 계산과 지연 계산 비교</span><span class="sxs-lookup"><span data-stu-id="d0902-112">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="d0902-113">지연된 실행을 구현하는 메서드를 작성하는 경우 지연 계산이나 즉시 계산 중에서 메서드 구현에 사용할 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-113">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="d0902-114">*지연 계산(lazy evaluation)*에서는 소스 컬렉션의 단일 요소가 반복기를 호출할 때마다 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-114">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="d0902-115">이것이 반복기가 구현되는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-115">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="d0902-116">*즉시 계산(eager evaluation)*에서는 반복기를 처음 호출할 때 전체 컬렉션이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-116">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="d0902-117">소스 컬렉션의 임시 복사본도 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-117">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="d0902-118">예를 들어, <xref:System.Linq.Enumerable.OrderBy%2A> 메서드는 첫 번째 요소를 반환하기 전에 전체 컬렉션을 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-118">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="d0902-119">지연 계산은 컬렉션의 계산 전반에 오버헤드 처리를 균일하게 분산시키고 임시 데이터를 최소한으로 사용하기 때문에 대개 성능이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-119">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="d0902-120">물론 중간 결과를 구체화해야만 하는 연산도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-120">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d0902-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d0902-121">Next Steps</span></span>  
 <span data-ttu-id="d0902-122">이 자습서의 다음 항목에서는 지연된 실행을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0902-122">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="d0902-123">지연 실행 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="d0902-123">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0902-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0902-124">See Also</span></span>  
 <span data-ttu-id="d0902-125">[자습서: 여러 쿼리 연결(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span><span class="sxs-lookup"><span data-stu-id="d0902-125">[Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span></span>  
 <span data-ttu-id="d0902-126">[개념과 용어(함수 변환)(C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d0902-126">[Concepts and Terminology (Functional Transformation) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span></span>  
 <span data-ttu-id="d0902-127">[집계 작업(C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span><span class="sxs-lookup"><span data-stu-id="d0902-127">[Aggregation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span></span>  
 [<span data-ttu-id="d0902-128">yield</span><span class="sxs-lookup"><span data-stu-id="d0902-128">yield</span></span>](../../../../csharp/language-reference/keywords/yield.md)

