---
title: "실행 및 LINQ to XML (Visual Basic)에서 지연 계산을 지연 | Microsoft 문서"
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
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ecb4d18cf7c61442e17de1c0f08824b360362e1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a><span data-ttu-id="b1f99-102">지연 된 실행과 지연 계산은 linq to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1f99-102">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="b1f99-103">쿼리 및 축 연산은 흔히 지연된 실행을 사용하도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="b1f99-104">이 항목에서는 지연된 실행의 요구 사항 및 장점과 몇 가지 구현 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="b1f99-105">지연된 실행</span><span class="sxs-lookup"><span data-stu-id="b1f99-105">Deferred Execution</span></span>  
 <span data-ttu-id="b1f99-106">지연 될 때까지 식의 계산이 지연 되는 실행 의미의 *실현* 값이 실제로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="b1f99-107">지연된 실행은 특히 일련의 연결된 쿼리나 조작이 포함된 프로그램에서 큰 데이터 컬렉션을 조작해야 하는 경우 성능을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="b1f99-108">최상의 경우에는 지연된 실행을 통해 소스 컬렉션을 한 번만 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="b1f99-109">LINQ 기술은 광범위 하 게 사용 지연 된 실행의 핵심 멤버에서 <xref:System.Linq?displayProperty=fullName>클래스 <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</xref:System.Xml.Linq.Extensions?displayProperty=fullName> 등 다양 한 LINQ 네임 스페이스의 확장 메서드와</xref:System.Linq?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b1f99-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=fullName> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="b1f99-110">즉시 계산과 지연 계산 비교</span><span class="sxs-lookup"><span data-stu-id="b1f99-110">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="b1f99-111">지연된 실행을 구현하는 메서드를 작성하는 경우 지연 계산이나 즉시 계산 중에서 메서드 구현에 사용할 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-111">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="b1f99-112">*지연 평가*, 소스 컬렉션의 단일 요소가 반복기를 호출할 때마다 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-112">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="b1f99-113">이것이 반복기가 구현되는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-113">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="b1f99-114">*즉시 평가*, 반복기를 처음으로 호출 하면 전체 컬렉션이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-114">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="b1f99-115">소스 컬렉션의 임시 복사본도 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-115">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="b1f99-116">예를 들어는 <xref:System.Linq.Enumerable.OrderBy%2A>메서드에 첫 번째 요소를 반환 하기 전에 전체 컬렉션을 정렬 하는.</xref:System.Linq.Enumerable.OrderBy%2A></span><span class="sxs-lookup"><span data-stu-id="b1f99-116">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="b1f99-117">지연 계산은 컬렉션의 계산 전반에 오버헤드 처리를 균일하게 분산시키고 임시 데이터를 최소한으로 사용하기 때문에 대개 성능이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-117">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="b1f99-118">물론 중간 결과를 구체화해야만 하는 연산도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-118">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b1f99-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b1f99-119">Next Steps</span></span>  
 <span data-ttu-id="b1f99-120">이 자습서의 다음 항목에서는 지연된 실행을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1f99-120">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="b1f99-121">지연된 실행 예제 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1f99-121">Deferred Execution Example (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1f99-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1f99-122">See Also</span></span>  
 <span data-ttu-id="b1f99-123">[자습서: 지연 된 실행 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md) </span><span class="sxs-lookup"><span data-stu-id="b1f99-123">[Tutorial: Deferred Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md) </span></span>  
<span data-ttu-id="b1f99-124"> [개념 및 용어 (함수 변환) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b1f99-124"> [Concepts and Terminology (Functional Transformation) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span></span>  
<span data-ttu-id="b1f99-125"> [집계 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)</span><span class="sxs-lookup"><span data-stu-id="b1f99-125"> [Aggregation Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)</span></span>
