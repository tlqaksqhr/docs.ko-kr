---
title: "방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가 | Microsoft 문서"
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
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
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
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가
확장 메서드를 추가 하 여 LINQ 쿼리에 사용할 수 있는 메서드 집합을 확장할 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601> 예를 들어 표준 평균 또는 최대 작업 외에 값의 시퀀스에서 단일 값을 계산 하는 사용자 지정 집계 메서드를 만들 수 있습니다. 사용자 지정 필터 또는 값의 시퀀스에 대 한 특정 데이터 변환을로 작동 하 고 새 시퀀스를 반환 하는 메서드를 만들 수 있습니다. 이러한 메서드의 예로 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, 및 <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A>  
  
 확장 하는 경우는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스, 열거형 컬렉션에 사용자 지정 메서드를 적용할 수 있습니다.</xref:System.Collections.Generic.IEnumerable%601> 자세한 내용은 참조 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)합니다.  
  
## <a name="adding-an-aggregate-method"></a>집계 메서드를 추가합니다.  
 집계 메서드는 값 집합에서 단일 값을 계산합니다. 포함 하는 여러 집계 메서드를 제공 하는 LINQ <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, 및 <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A> 확장 메서드를 추가 하 여 사용자 고유의 집계 메서드를 만들 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601>  
  
 다음 코드 예제에는 확장 메서드를 만드는 방법을 보여 줍니다 `Median` 일련의 숫자 형식에 대 한 중앙값을 계산 하 `double`합니다.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 다른 집계 메서드를 호출 하면 동일한 방식으로 열거 가능한 컬렉션에 대 한이 확장 메서드를 호출는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  Visual Basic에서 사용 하거나 메서드 호출 또는 표준 쿼리 구문에는 `Aggregate` 또는 `Group By` 절. 자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md) 및 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.  
  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `Median` 형식의 배열에 대 한 메서드 `double`합니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>다양 한 형식에 적용할 집계 메서드를 오버 로드  
 다양 한 형식의 시퀀스를 수락 하 여 집계 메서드를 오버 로드할 수 있습니다. 각 형식에 대 한 오버 로드를 만들 하는 표준 방법이입니다. 또 다른 방법은 제네릭 형식을 하는 대리자를 사용 하 여 특정 형식으로 변환 하는 오버 로드를 만드는 것입니다. 두 방법 모두를 결합할 수 있습니다.  
  
#### <a name="to-create-an-overload-for-each-type"></a>각 형식에 대 한 오버 로드를 만들려면  
 지원 하려는 각 형식에 대 한 특정 오버 로드를 만들 수 있습니다. 다음 코드 예제에서는 오버 로드는 `Median` 에 대 한 메서드는 `integer` 유형입니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 이제 호출할 수는 `Median` 둘 다에 대해 오버 로드 `integer` 및 `double` 형식, 다음 코드에 나와 있는 것 처럼:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
#### <a name="to-create-a-generic-overload"></a>제네릭 오버 로드를 만들려면  
 일반 개체의 시퀀스를 받아들이는 오버 로드를 만들 수 있습니다. 이 오버 로드는 대리자를 매개 변수로 제네릭 형식의 개체 시퀀스의 특정 형식으로 변환 하려면 사용 합니다.  
  
 다음 코드에서는 오버 로드는 `Median` 를 받는 메서드에 <xref:System.Func%602>대리자를 매개 변수로.</xref:System.Func%602> 이 대리자는 제네릭 형식 T의 개체는 개체를 반환 형식의 `double`합니다.  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 이제 호출할 수는 `Median` 모든 형식의 개체의 시퀀스에 대 한 메서드. 형식에 고유한 메서드 오버 로드가 없는 경우는 대리자 매개 변수를 전달 해야 합니다. Visual Basic의 람다 식을이 용도로 사용할 수 있습니다. 또한 사용 하는 경우는 `Aggregate` 또는 `Group By` 메서드를 호출 하는 대신 절 임의의 값 또는이 절은 범위 내에 있는 식을 전달할 수 있습니다.  
  
 다음 예제 코드를 호출 하는 방법을 보여 줍니다는 `Median` 정수의 배열 및 문자열의 배열에 대 한 메서드. 문자열, 배열에 문자열의 길이 대 한 중앙값을 계산 됩니다. 전달 하는 방법을 보여 주는 예제는는 <xref:System.Func%602>대리자를 매개 변수는 `Median` 각 사례에 대 한 메서드.</xref:System.Func%602>  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
## <a name="adding-a-method-that-returns-a-collection"></a>컬렉션을 반환 하는 메서드 추가  
 확장할 수는 <xref:System.Collections.Generic.IEnumerable%601>값의 시퀀스를 반환 하는 사용자 지정 쿼리 메서드로 인터페이스.</xref:System.Collections.Generic.IEnumerable%601> 메서드 이름 필드에 <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 의 컬렉션을 반환 해야이 경우 값의 시퀀스에 필터 또는 데이터 변환을 적용 하려면 이러한 메서드를 사용할 수 있습니다.  
  
 다음 예제에 라는 확장 메서드를 만드는 방법을 보여 줍니다 `AlternateElements` 첫 번째 요소에서 시작 하 여 컬렉션의 다른 모든 요소를 반환 하는 합니다.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 다른 메서드를 호출 하는 것 처럼 모든 열거 가능한 컬렉션에 대 한이 확장 메서드를 호출할 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스에 다음 코드에 나와 있는 것 처럼:</xref:System.Collections.Generic.IEnumerable%601>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [확장명 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
