---
title: "데이터 형식 (Visual Basic) 변환 | Microsoft 문서"
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
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
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
ms.openlocfilehash: 53d8ad292891a567e13ec8a5396bcc114b379351
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-visual-basic"></a>데이터 형식 (Visual Basic) 변환
변환 메서드는 입력된 개체의 형식을 변경합니다.  
  
 LINQ 쿼리에서 변환 작업은 다양 한 응용 프로그램에에서 유용 합니다. 다음은 몇 가지 예입니다.  
  
-   <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>메서드는 표준 쿼리 연산자의 형식의 사용자 지정 구현을 숨길 데 사용할 수 있습니다.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>  
  
-   <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>LINQ 쿼리에 대 한 매개 변수가 없는 컬렉션을 사용 하도록 설정 하려면 메서드를 사용할 수 있습니다.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, 및 <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>쿼리 열거 될 때까지 연기 하는 대신 쿼리를 즉시 실행 하려면 메서드를 사용할 수 있습니다.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>  
  
## <a name="methods"></a>메서드  
 다음 표에서 데이터 형식 변환을 수행 하는 표준 쿼리 연산자 메서드를 보여 줍니다.  
  
 이름이 "As"로 시작 합니다.이 테이블의 변환 메서드는 소스 컬렉션의 정적 형식을 바뀌지만 열거 하지는 않습니다. 이름이 "소스 컬렉션을 열거 하 고 해당 컬렉션에 항목을 추가"를로 시작 하는 메서드를 입력 합니다.  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|AsEnumerable|<xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 로 형식화 된 입력을 반환 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|(일반) <xref:System.Collections.IEnumerable>(일반) <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> 에</xref:System.Collections.IEnumerable> 변환|해당 사항 없음.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Cast|지정 된 형식 컬렉션의 요소를 캐스팅합니다.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|지정된 된 형식으로 캐스팅할 수에 따라 값을 필터링 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|배열에 컬렉션으로 변환 합니다. 이 메서드는 쿼리 실행이 되도록합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|에 요소 배치는 <xref:System.Collections.Generic.Dictionary%602>키 선택기 함수에 따라.</xref:System.Collections.Generic.Dictionary%602> 이 메서드는 쿼리 실행이 되도록합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|<xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> 컬렉션으로 변환 이 메서드는 쿼리 실행이 되도록합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|에 요소 배치는 <xref:System.Linq.Lookup%602>키 선택기 함수에 따라 (예: 일 대 다 사전).</xref:System.Linq.Lookup%602> 이 메서드는 쿼리 실행이 되도록합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>쿼리 식 구문 예제  
 다음 코드 예제에서는 `From As` 절은 하위 형식 에서만 사용할 수 있는 멤버에 액세스 하기 전에 하위 형식에 형식을 캐스팅 합니다.  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [From 절](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
