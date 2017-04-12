---
title: "실행 (Visual Basic) 방식에 따라 표준 쿼리 연산자 분류 | Microsoft 문서"
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
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a13f2fcf33c2faacd5b2662cd96d0f962b54322f
ms.lasthandoff: 03/13/2017

---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>실행 (Visual Basic) 방식에 따라 표준 쿼리 연산자 분류
LINQ 표준 쿼리 연산자 메서드의 개체 구현에는 두 가지 주요 방법 중 하나에서 실행: 즉시 또는 지연 합니다. 지연 된 실행을 사용 하는 쿼리 연산자 또한 두 가지 범주로 나눌 수 있습니다: 스트리밍 및 비 스트리밍. 다른 쿼리 연산자가 실행 하는 방법을 알고 있는 경우에 특정 쿼리에서 얻을 수 있는 결과 이해 하면 도움이 될 것입니다. 데이터 소스가 변경 하거나 다른 쿼리를 기반으로 쿼리를 작성 하는 경우 특히 유용 합니다. 이 항목에서는 실행 방식에 따라 표준 쿼리 연산자 분류 합니다.  
  
## <a name="manners-of-execution"></a>실행 방식  
  
### <a name="immediate"></a>직접 실행  
 즉시 실행 데이터 소스는 읽기 작업을 수행할 때 코드의 지점에 있는 쿼리가 선언 된을 의미 합니다. 단일, 열거할 수 없는 결과 반환 하는 모든 표준 쿼리 연산자는 즉시 실행 됩니다.  
  
### <a name="deferred"></a>연기됨  
 지연 된 실행 작업은 수행 하지 않음을 코드의 지점에 있는 쿼리가 선언 된 것을 의미 합니다. 예를 들어을 사용 하 여 쿼리 변수 열거 되는 경우에 작업이 수행 되는 `For Each` 문입니다. 이 의미 하는 쿼리 실행의 결과에 종속 데이터 원본의 내용을 경우 쿼리가 정의 하는 대신 쿼리를 실행할 때 합니다. 쿼리 변수를 여러 번 열거할 경우 그 때마다 결과가 다를 수 있습니다. 반환 형식이 거의 모든 표준 쿼리 연산자 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IOrderedEnumerable%601>지연 된 방식에서으로 실행 합니다.</xref:System.Linq.IOrderedEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 지연 된 실행을 사용 하는 쿼리 연산자 스트리밍 또는 비 스트리밍으로 분류할 수 있습니다.  
  
#### <a name="streaming"></a>스트리밍  
 스트리밍 연산자는 요소를 생성 하기 전에 모든 원본 데이터를 읽이 필요가 없습니다. 실행 시 스트리밍 연산자는 읽기 및 적절 한 경우 요소를 생성 각 소스 요소에 대해 연산을 수행 합니다. 스트리밍 연산자에는 소스 요소가 때까지 계속 읽습니다 결과 요소를 생성할 수 있습니다. 즉, 한 결과 요소를 만드는 둘 이상의 소스 요소를 읽을 수 있습니다.  
  
#### <a name="non-streaming"></a>비 스트리밍  
 비 스트리밍 연산자 결과 요소를 생성 하기 전에 모든 원본 데이터를 읽어야 합니다. 정렬 또는 그룹화 하는 등의 작업은이 범주에 속합니다. 실행 시 비 스트리밍 쿼리 연산자 모든 원본 데이터를 읽고, 데이터 구조에 넣습니다, 그리고 작업을 수행 및 결과 요소를 생성 합니다.  
  
## <a name="classification-table"></a>분류 테이블  
 다음 표에서 실행 방식에 따라 각 표준 쿼리 연산자 메서드를 분류합니다.  
  
> [!NOTE]
>  연산자는 두 열에 표시 되 면 두 입력된 시퀀스 작업을 포함 하 고 각 시퀀스는 서로 다르게 계산 됩니다. 이러한 경우 것은 항상 평가 되는 매개 변수 목록에서 첫 번째 시퀀스에는 지연 된 스트리밍 방식으로 합니다.  
  
|표준 쿼리 연산자|반환 형식|즉시 실행|지연 된 스트리밍 실행|비 스트리밍 실행 지연|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A></xref:System.Linq.Enumerable.Aggregate%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.All%2A></xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Any%2A></xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A></xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A></xref:System.Linq.Enumerable.Average%2A>|단일 숫자 값|X|||  
|<xref:System.Linq.Enumerable.Cast%2A></xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Concat%2A></xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Contains%2A></xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Count%2A></xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32></xref:System.Int32>|X|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A></xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Distinct%2A></xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A></xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A></xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Empty%2A></xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|X|||  
|<xref:System.Linq.Enumerable.Except%2A></xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.First%2A></xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.GroupBy%2A></xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.GroupJoin%2A></xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
<xref:System.Linq.Enumerable.Intersect%2A></xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Join%2A></xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Last%2A></xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A></xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LongCount%2A></xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64></xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A></xref:System.Linq.Enumerable.Max%2A>|단일 숫자 값, TSource, 또는 TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A></xref:System.Linq.Enumerable.Min%2A>|단일 숫자 값, TSource, 또는 TResult|X|||  
|<xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.OrderBy%2A></xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A></xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Range%2A></xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Repeat%2A></xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Reverse%2A></xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Select%2A></xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SelectMany%2A></xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A></xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A></xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A></xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Skip%2A></xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SkipWhile%2A></xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A></xref:System.Linq.Enumerable.Sum%2A>|단일 숫자 값|X|||  
|<xref:System.Linq.Enumerable.Take%2A></xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
<xref:System.Linq.Enumerable.TakeWhile%2A></xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ThenBy%2A></xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A></xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A></xref:System.Linq.Enumerable.ToArray%2A>|TSource 배열|X|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A></xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602>|X|||  
|<xref:System.Linq.Enumerable.ToList%2A></xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601></xref:System.Collections.Generic.IList%601>|X|||  
|<xref:System.Linq.Enumerable.ToLookup%2A></xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602></xref:System.Linq.ILookup%602>|X|||  
|<xref:System.Linq.Enumerable.Union%2A></xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Where%2A></xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
