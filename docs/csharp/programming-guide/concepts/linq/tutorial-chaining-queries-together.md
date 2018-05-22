---
title: '자습서: 여러 쿼리 연결(C#)'
ms.date: 07/20/2015
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
ms.openlocfilehash: 8411d8577c192e2aa1a43bea47644fe6bdc09e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="868f5-102">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="868f5-103">이 자습서에서는 쿼리를 연결할 때의 처리 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="868f5-104">쿼리 연결은 함수 변환을 작성할 때 핵심 부분을 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="868f5-105">연결된 쿼리의 작동 방식을 정확히 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="868f5-106">Office Open XML 문서를 처리하는 쿼리는 이 기법을 광범위하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="868f5-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="868f5-107">In This Section</span></span>  
  
|<span data-ttu-id="868f5-108">항목</span><span class="sxs-lookup"><span data-stu-id="868f5-108">Topic</span></span>|<span data-ttu-id="868f5-109">설명</span><span class="sxs-lookup"><span data-stu-id="868f5-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="868f5-110">LINQ to XML에서 지연 실행 및 지연 계산(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="868f5-111">지연된 실행과 지연 계산의 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|[<span data-ttu-id="868f5-112">지연 실행 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-112">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)|<span data-ttu-id="868f5-113">지연된 실행의 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-113">Provides an example of deferred execution.</span></span>|  
|[<span data-ttu-id="868f5-114">연결 쿼리 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-114">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)|<span data-ttu-id="868f5-115">쿼리를 연결할 때 지연된 실행이 작동하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|[<span data-ttu-id="868f5-116">중간 구체화(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-116">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)|<span data-ttu-id="868f5-117">중간 구체화의 의미를 식별하고 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|[<span data-ttu-id="868f5-118">여러 표준 쿼리 연산자 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-118">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)|<span data-ttu-id="868f5-119">표준 쿼리 연산자의 지연 의미에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="868f5-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="868f5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="868f5-120">See Also</span></span>  
 [<span data-ttu-id="868f5-121">XML의 순수 함수 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="868f5-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
