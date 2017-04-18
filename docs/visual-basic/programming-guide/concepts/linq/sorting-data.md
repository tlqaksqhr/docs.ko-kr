---
title: "데이터 정렬 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
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
ms.openlocfilehash: d6a009573f9ff3eba71875945128ee6cd37ac37b
ms.lasthandoff: 03/13/2017

---
# <a name="sorting-data-visual-basic"></a>데이터 정렬 (Visual Basic)
정렬 작업에는 하나 이상의 특성에 따라 시퀀스의 요소를 정렬 합니다. 첫 번째 정렬 기준은 요소에 대해 기본 정렬을 수행합니다. 두 번째 정렬 기준을 지정하면 각 기본 정렬 그룹 내의 요소를 정렬할 수 있습니다.  
  
 다음 그림에서는 문자 시퀀스에서 사전순 정렬 작업의 결과 보여 줍니다.  
  
 ![LINQ 정렬 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")  
  
 데이터를 정렬 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|OrderBy|값을 오름차순으로 정렬 합니다.|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|OrderByDescending|값을 내림차순으로 정렬 합니다.|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|ThenBy|오름차순 보조 정렬을 수행 합니다.|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|ThenByDescending|내림차순으로 정렬 한 보조 정렬을 수행 합니다.|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|Reverse|컬렉션에 있는 요소의 순서를 반대로 바꿉니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="primary-sort-examples"></a>기본 정렬 예제  
  
#### <a name="primary-ascending-sort"></a>기본 오름차순 정렬  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By` 배열에서 문자열 문자열 길이 오름차순으로 정렬 하는 LINQ 쿼리에서 절.  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a>기본 내림차순 정렬  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By Descending` 해당 첫 문자를 내림차순으로 정렬 하 여 문자열을 정렬 하는 LINQ 쿼리 절.  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a>2 차 정렬 예제  
  
#### <a name="secondary-ascending-sort"></a>2 차 오름차순 정렬  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By` 배열에는 문자열의 기본 및 보조 정렬을 수행 하는 LINQ 쿼리에서 절. 문자열에는 기본적으로 길이 및 차적 모두 오름차순 문자열의 첫 글자를 기준으로 정렬 됩니다.  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a>2 차 내림차순 정렬  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By Descending` 오름차순으로 정렬 순서 및 내림차순의&2; 차 정렬 기본 정렬을 수행 하는 LINQ 쿼리에서 절. 문자열에는 기본적으로 길이 및 차적 문자열의 첫 글자를 기준으로 정렬 됩니다.  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [방법: 쿼리 결과 정렬](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)   
 [방법: 데이터 정렬 또는 필터링 텍스트에서 단어 또는 필드 (Visual Basic) (LINQ)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
