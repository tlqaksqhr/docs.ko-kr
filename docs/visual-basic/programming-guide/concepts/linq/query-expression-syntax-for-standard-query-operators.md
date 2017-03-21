---
title: "쿼리 식 구문에 대 한 표준 쿼리 연산자 (Visual Basic) | Microsoft 문서"
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
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 53f975855c4d740e0b0373d384a9383ded410bd9
ms.lasthandoff: 03/13/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문
더 자주 사용 되는 표준 쿼리 연산자 중 일부는 전용의 일부로 호출할 수 있도록 하는 Visual Basic 언어 키워드 구문이 *쿼리 식*합니다. 쿼리 식 방식은 서로 다른, 가독성이 더 우수한 쿼리 표현 해당 *메서드 기반* 동일 합니다. 쿼리 식 절은 컴파일 타임에 쿼리 메서드 호출로 변환됩니다.  
  
## <a name="query-expression-syntax-table"></a>쿼리 식 구문 표  
 다음 표에서 해당 쿼리 식 절이 있는 표준 쿼리 연산자를 나열 합니다.  
  
|메서드|Visual Basic 쿼리 식 구문|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A></xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Any%2A></xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Average%2A></xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Cast%2A></xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> (자세한 내용은 참조 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Count%2A></xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29></xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> (자세한 내용은 참조 [Distinct 절](../../../../visual-basic/language-reference/queries/distinct-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A></xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> (자세한 내용은 참조 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29></xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> (자세한 내용은 참조 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29></xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> 또는<br /><br /> `Join … [As …]In … On …`<br /><br /> (자세한 내용은 참조 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md).)|  
|<xref:System.Linq.Enumerable.LongCount%2A></xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Max%2A></xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Min%2A></xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> (자세한 내용은 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> (자세한 내용은 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A></xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (자세한 내용은 참조 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A></xref:System.Linq.Enumerable.SelectMany%2A>|여러 `From` 절<br /><br /> (자세한 내용은 참조 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Skip%2A></xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> (자세한 내용은 참조 [Skip 절](../../../../visual-basic/language-reference/queries/skip-clause.md).)|  
|<xref:System.Linq.Enumerable.SkipWhile%2A></xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> (자세한 내용은 참조 [Skip While 절](../../../../visual-basic/language-reference/queries/skip-while-clause.md).)|  
|<xref:System.Linq.Enumerable.Sum%2A></xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> (자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Take%2A></xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> (자세한 내용은 참조 [Take 절](../../../../visual-basic/language-reference/queries/take-clause.md).)|  
|<xref:System.Linq.Enumerable.TakeWhile%2A></xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> (자세한 내용은 참조 [걸릴 While 절](../../../../visual-basic/language-reference/queries/take-while-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> (자세한 내용은 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> (자세한 내용은 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A></xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> (자세한 내용은 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md).)|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable></xref:System.Linq.Queryable>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [실행 (Visual Basic) 방식에 따라 표준 쿼리 연산자 분류](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
