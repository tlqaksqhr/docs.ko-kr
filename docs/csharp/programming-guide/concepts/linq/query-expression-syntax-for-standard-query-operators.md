---
title: 표준 쿼리 연산자의 쿼리 식 구문(C#)
ms.date: 07/20/2015
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
ms.openlocfilehash: 48ca1173439559832ac7e578eac1e11c2bf34be2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339841"
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>표준 쿼리 연산자의 쿼리 식 구문(C#)
자주 사용되는 표준 쿼리 연산자 중 일부에는 *쿼리 식*의 일부로 호출할 수 있는 전용 C# 언어 키워드 구문이 있습니다. 쿼리 식은 *메서드 기반* 양식과는 다른, 가독성이 더 우수한 쿼리 표현 양식입니다. 쿼리 식 절은 컴파일 시간에 쿼리 메서드 호출로 변환됩니다.  
  
## <a name="query-expression-syntax-table"></a>쿼리 식 구문 표  
 다음 표에는 동등한 쿼리 식 절이 있는 표준 쿼리 연산자가 나열되어 있습니다.  
  
|메서드|C# 쿼리 식 구문|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|예를 들어 명시적으로 형식화된 범위 변수를 사용합니다.<br /><br /> `from int i in numbers`<br /><br /> 자세한 내용은 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> 또는<br /><br /> `group … by … into …`<br /><br /> 자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> 자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> 자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> 자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> 자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> 자세한 내용은 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|여러 `from` 절.<br /><br /> 자세한 내용은 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> 자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> 자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> 자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable>  
 <xref:System.Linq.Queryable>  
 [표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [실행 방식에 따라 표준 쿼리 연산자 분류(C#)](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
