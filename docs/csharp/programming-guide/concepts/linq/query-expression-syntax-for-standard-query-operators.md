---
title: "표준 쿼리 연산자의 쿼리 식 구문(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f662f23948f5d18c31a981a2f46d78f382ff5c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a><span data-ttu-id="12c09-102">표준 쿼리 연산자의 쿼리 식 구문(C#)</span><span class="sxs-lookup"><span data-stu-id="12c09-102">Query Expression Syntax for Standard Query Operators (C#)</span></span>
<span data-ttu-id="12c09-103">자주 사용되는 표준 쿼리 연산자 중 일부에는 *쿼리 식*의 일부로 호출할 수 있는 전용 C# 언어 키워드 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12c09-103">Some of the more frequently used standard query operators have dedicated C# language keyword syntax that enables them to be called as part of a *query expression*.</span></span> <span data-ttu-id="12c09-104">쿼리 식은 *메서드 기반* 양식과는 다른, 가독성이 더 우수한 쿼리 표현 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="12c09-104">A query expression is a different, more readable form of expressing a query than its *method-based*  equivalent.</span></span> <span data-ttu-id="12c09-105">쿼리 식 절은 컴파일 시간에 쿼리 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="12c09-105">Query expression clauses are translated into calls to the query methods at compile time.</span></span>  
  
## <a name="query-expression-syntax-table"></a><span data-ttu-id="12c09-106">쿼리 식 구문 표</span><span class="sxs-lookup"><span data-stu-id="12c09-106">Query Expression Syntax Table</span></span>  
 <span data-ttu-id="12c09-107">다음 표에는 동등한 쿼리 식 절이 있는 표준 쿼리 연산자가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12c09-107">The following table lists the standard query operators that have equivalent query expression clauses.</span></span>  
  
|<span data-ttu-id="12c09-108">메서드</span><span class="sxs-lookup"><span data-stu-id="12c09-108">Method</span></span>|<span data-ttu-id="12c09-109">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="12c09-109">C# Query Expression Syntax</span></span>|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|<span data-ttu-id="12c09-110">예를 들어 명시적으로 형식화된 범위 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12c09-110">Use an explicitly typed range variable, for example:</span></span><br /><br /> `from int i in numbers`<br /><br /> <span data-ttu-id="12c09-111">자세한 내용은 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-111">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> <span data-ttu-id="12c09-112">또는</span><span class="sxs-lookup"><span data-stu-id="12c09-112">-or-</span></span><br /><br /> `group … by … into …`<br /><br /> <span data-ttu-id="12c09-113">자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-113">(For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> <span data-ttu-id="12c09-114">자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-114">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> <span data-ttu-id="12c09-115">자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-115">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> <span data-ttu-id="12c09-116">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-116">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> <span data-ttu-id="12c09-117">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-117">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> <span data-ttu-id="12c09-118">자세한 내용은 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-118">(For more information, see [select clause](../../../../csharp/language-reference/keywords/select-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<span data-ttu-id="12c09-119">여러 `from` 절.</span><span class="sxs-lookup"><span data-stu-id="12c09-119">Multiple `from` clauses.</span></span><br /><br /> <span data-ttu-id="12c09-120">자세한 내용은 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-120">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> <span data-ttu-id="12c09-121">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-121">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> <span data-ttu-id="12c09-122">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-122">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> <span data-ttu-id="12c09-123">자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c09-123">(For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12c09-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12c09-124">See Also</span></span>  
 <xref:System.Linq.Enumerable>  
 <xref:System.Linq.Queryable>  
 [<span data-ttu-id="12c09-125">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="12c09-125">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="12c09-126">실행 방식에 따라 표준 쿼리 연산자 분류(C#)</span><span class="sxs-lookup"><span data-stu-id="12c09-126">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
