---
title: "(Visual Basic) 데이터를 그룹화 합니다. | Microsoft 문서"
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
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
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
ms.openlocfilehash: d89ae6d155ab901b03cf92a7508261fb147b97b7
ms.lasthandoff: 03/13/2017

---
# <a name="grouping-data-visual-basic"></a>데이터 그룹화 (Visual Basic)
그룹화는 각 그룹의 요소가 공통 특성을 공유 되도록 데이터를 그룹으로 나누는 작업입니다.  
  
 다음 그림에는 문자 시퀀스를 그룹화 한 결과를 보여 줍니다. 각 그룹에 대 한 키에는 문자입니다.  
  
 ![LINQ 그룹화 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 데이터 요소를 그룹화 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|GroupBy|공통 특성을 공유 하는 요소를 그룹입니다. 각 그룹으로 표시 되는 <xref:System.Linq.IGrouping%602>개체.</xref:System.Linq.IGrouping%602>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|ToLookup|에 요소를 삽입 하는 <xref:System.Linq.Lookup%602>키 선택기 함수에 따라 (예: 일 대 다 사전).</xref:System.Linq.Lookup%602>|해당 사항 없음.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>쿼리 식 구문 예제  
 다음 코드 예제에서는 `Group By` 짝수 또는 홀수 인지 여부에 따라 목록에서 그룹 정수로 절.  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Group By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)   
 [방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)   
 [방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
