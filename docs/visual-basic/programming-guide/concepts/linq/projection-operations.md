---
title: "프로젝션 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
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
ms.openlocfilehash: 8876e65e752e0b18404ec32aecdcad7805533840
ms.lasthandoff: 03/13/2017

---
# <a name="projection-operations-visual-basic"></a>프로젝션 작업 (Visual Basic)
프로젝션 종종 나중에 사용 될 속성만 구성 된 새 폼에 개체를 변환 하는 작업을 참조 합니다. 프로젝션을 사용하면 각 개체를 기반으로 만들어지는 새 형식을 생성할 수 있습니다. 프로젝트는 속성 수 있으며에 수학 함수를 수행할 수 있습니다. 또한 변경 하지 않고 원래 개체를 프로젝션 할 수 있습니다.  
  
 프로젝션을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|선택|변환 함수를 기반으로 하는 프로젝트의 값입니다.|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></xref:System.Linq.Queryable.Select%2A?displayProperty=fullName>|  
|SelectMany|변환 함수에 기반 하 고 단일 시퀀스로 평면화 하는 값의 시퀀스를 프로젝션 합니다.|사용 하 여 `From` 절|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="select"></a>선택  
 다음 예제에서는 `Select` 문자열의 목록에서 각 문자열에서 첫 글자를 프로젝션 하는 절.  
  
```vb  
Dim words = New List(Of String) From {"an", "apple", "a", "day"}  
  
Dim query = From word In words   
            Select word.Substring(0, 1)  
  
Dim sb As New System.Text.StringBuilder()  
For Each letter As String In query  
    sb.AppendLine(letter)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' a  
' a  
' a  
' d  
```  
  
### <a name="selectmany"></a>SelectMany  
 다음 예제에서는 여러 `From` 절 문자열의 목록에서 각 문자열에서 각 단어를 프로젝션 합니다.  
  
```vb  
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}  
  
Dim query = From phrase In phrases   
            From word In phrase.Split(" "c)   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' an  
' apple  
' a  
' day  
' the  
' quick  
' brown  
' fox  
```  
  
## <a name="select-versus-selectmany"></a>SelectMany와 선택  
 역할은 모두 `Select()` 및 `SelectMany()` 결과 값 또는 값을 생성 하는 정책 원본 값에서입니다. `Select()`모든 원본 값에 대해 하나의 결과 값을 생성합니다. 전체 결과 따라서 소스 컬렉션에 동일한 수의 요소가 들어 있는 컬렉션입니다. 반면, `SelectMany()` 각 소스 값에서 연결 된 하위 컬렉션을 포함 하는 하나의 전체 결과 생성 합니다. 변환 함수에 인수로 전달 되는 `SelectMany()` 각 소스 값에 대 한 값의 열거 가능한 시퀀스를 반환 해야 합니다. 이러한 열거 가능한 시퀀스를 연결 하 여 `SelectMany()` 하나의 큰 시퀀스를 만듭니다.  
  
 다음 두 그림은 이러한 두 가지 방법의 작업 간의 개념적 차이 보여 줍니다. 각각의 경우에서 선택기 (변환) 함수 꽃의 배열을 각 소스 값에서 선택 한다고 가정 합니다.  
  
 이 그림에서는 설명 어떻게 `Select()` 소스 컬렉션에 동일한 수의 요소가 들어 있는 컬렉션을 반환 합니다.  
  
 ![Select ()의 동작에 대 한 개념적 설명](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")  
  
 이 그림에서는 설명 어떻게 `SelectMany()` 중간 배열 시퀀스에 있는 각 중간 배열에서 각 값이 포함 된 하나의 최종 결과 값으로 연결 합니다.  
  
 ![Selectmany ()의 동작을 보여주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")  
  
### <a name="code-example"></a>코드 예제  
 동작을 비교 하는 다음 예제에서는 `Select()` 및 `SelectMany()`합니다. 코드는 소스 컬렉션의 각 꽃 이름 목록에서 처음 두 항목을 수행 하 여 "축 하" 꽃을 만듭니다. 이 예제에서는 "단일 값" 하는 변환 함수 <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>사용 하 여 값의 컬렉션 자체는.</xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> 이 위해서는 추가 `For Each` 각 하위 시퀀스의 각 문자열을 열거 하기 위해 루프입니다.  
  
```vb  
Class Bouquet  
    Public Flowers As List(Of String)  
End Class  
  
Sub SelectVsSelectMany()  
    Dim bouquets = New List(Of Bouquet) From {   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}  
  
    Dim output As New System.Text.StringBuilder  
  
    ' Select()  
    Dim query1 = bouquets.Select(Function(b) b.Flowers)  
  
    output.AppendLine("Using Select():")  
    For Each flowerList In query1  
        For Each str As String In flowerList  
            output.AppendLine(str)  
        Next  
    Next  
  
    ' SelectMany()  
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)  
  
    output.AppendLine(vbCrLf & "Using SelectMany():")  
    For Each str As String In query2  
        output.AppendLine(str)  
    Next  
  
    ' Display the output  
    MsgBox(output.ToString())  
  
    ' This code produces the following output:  
    '  
    ' Using Select():  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
    ' Using SelectMany()  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
End Sub  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)   
 [방법: 조인 사용 하 여 데이터 결합](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)   
 [방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)   
 [방법: LINQ 쿼리 결과 특정 형식으로 반환](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)   
 [방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
