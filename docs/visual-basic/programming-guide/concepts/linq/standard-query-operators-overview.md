---
title: "표준 쿼리 연산자 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
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
ms.openlocfilehash: eb28988ef49e0583fb7e9197c4e13c84665074ac
ms.lasthandoff: 03/13/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a>표준 쿼리 연산자 개요 (Visual Basic)
*표준 쿼리 연산자* 메서드를 LINQ 패턴을 형성 합니다. 이러한 메서드의 대부분 시퀀스, 여기서 시퀀스는 형식이 구현 하는 개체에서 동작의 <xref:System.Collections.Generic.IEnumerable%601>인터페이스 또는 <xref:System.Linq.IQueryable%601>인터페이스.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 표준 쿼리 연산자는 필터링, 프로젝션, 집계, 정렬 등을 포함 하 여 쿼리 기능을 제공 합니다.  
  
 형식 <xref:System.Collections.Generic.IEnumerable%601>및 기타 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> 유형의 개체에서 작동 하</xref:System.Collections.Generic.IEnumerable%601> 는 개체에 대해 작동 하는 LINQ 표준 쿼리 연산자의 두 집합이 각 집합을 구성 하는 메서드는 정적 멤버는 <xref:System.Linq.Enumerable>및 <xref:System.Linq.Queryable>클래스 각각.</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable> 로 정의 된 *확장 메서드* 에서 동작 하는 형식입니다. 즉, 정적 메서드 구문 또는 인스턴스 메서드 구문을 사용 하 여 호출할 수 있습니다.  
  
 여러 표준 쿼리 연산자 메서드 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 기반 하는 것 이외의 형식에서 작동 하는 또한 <xref:System.Linq.Enumerable>이러한 두 메서드를 정의 하는 형식 <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> 유형의 개체에서 동작 하는</xref:System.Linq.Enumerable> 이러한 메서드를 <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>및 <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>를 LINQ 패턴에서 쿼리할 매개 변수가 없는, 또는 제네릭이 아닌 컬렉션을 사용 하도록 설정 합니다.</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> 이렇게 강력한 형식의 개체 컬렉션을 작성 합니다. <xref:System.Linq.Queryable>클래스 <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>및 <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> <xref:System.Linq.Queryable>.</xref:System.Linq.Queryable> 유형의 개체에서 작동 하</xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> 는 유사한 메서드를 정의 합니다.</xref:System.Linq.Queryable>  
  
 표준 쿼리 연산자에서 반환 된 단일 값 또는 값의 시퀀스에 따라 해당 실행의 타이밍 다릅니다. Singleton 값을 반환 하는 이러한 메서드 (예를 들어 <xref:System.Linq.Enumerable.Average%2A>및 <xref:System.Linq.Enumerable.Sum%2A>) 쿼리는 즉시 실행 합니다.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A> 시퀀스를 반환 하는 메서드는 쿼리 실행을 지연 하 고 열거 가능한 개체를 반환 합니다.  
  
 즉, 이러한 메서드를 확장 하는 메모리 내 컬렉션에 대해 작동 하는 방법의 경우 <xref:System.Collections.Generic.IEnumerable%601>, 반환된 된 열거 가능한 개체를 메서드에 전달 된 인수를 캡처합니다.</xref:System.Collections.Generic.IEnumerable%601> 해당 개체를 열거 하는 경우 쿼리 연산자의 논리는 사용 하 고 쿼리 결과가 반환 됩니다.  
  
 반면, 확장 하는 메서드 <xref:System.Linq.IQueryable%601>는 쿼리 동작을 구현 하지 않는 하지만 수행할 쿼리를 나타내는 식 트리를 빌드합니다.</xref:System.Linq.IQueryable%601> 쿼리 처리는 소스에서 처리 <xref:System.Linq.IQueryable%601>개체.</xref:System.Linq.IQueryable%601>  
  
 쿼리 메서드를 호출 하는 쿼리를 훨씬 더 복잡 해질 수 있는 한 쿼리에서 연결할 수 있습니다.  
  
 다음 코드 예제에서는 시퀀스에 대 한 정보는 표준 쿼리 연산자를 사용할 수 있는 방법을 보여 줍니다.  
  
```vb  
Dim sentence = "the quick brown fox jumps over the lazy dog"  
' Split the string into individual words to create a collection.  
Dim words = sentence.Split(" "c)  
  
Dim query = From word In words   
            Group word.ToUpper() By word.Length Into gr = Group   
            Order By Length _  
            Select Length, GroupedWords = gr  
  
Dim output As New System.Text.StringBuilder  
For Each obj In query  
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))  
    For Each word As String In obj.GroupedWords  
        output.AppendLine(word)  
    Next  
Next  
  
'Display the output  
MsgBox(output.ToString())  
  
' This code example produces the following output:  
'  
' Words of length 3:  
' THE  
' FOX  
' THE  
' DOG  
' Words of length 4:  
' OVER  
' LAZY  
' Words of length 5:  
' QUICK  
' BROWN  
' JUMPS   
```  
  
## <a name="query-expression-syntax"></a>쿼리 식 구문  
 더 자주 사용 되는 표준 쿼리 연산자 중 일부는 전용의 일부로 호출할 수 있도록 하는 C# 및 Visual Basic 언어 키워드 구문이 *쿼리* *식*합니다. 표준 쿼리 연산자가 있는 전용 키워드와 해당 구문에 대 한 자세한 내용은 참조 [표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문을](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)합니다.  
  
## <a name="extending-the-standard-query-operators"></a>표준 쿼리 연산자 확장  
 대상 도메인 또는 기술에 대 한 적절 한 만드는 도메인 관련 메서드를 통해 표준 쿼리 연산자 집합을 강화할 수 있습니다. 또한 원격 평가, 쿼리 변환 및 최적화와 같은 추가 서비스를 제공 하는 고유한 구현으로 표준 쿼리 연산자를 바꿀 수 있습니다. 참조 <xref:System.Linq.Enumerable.AsEnumerable%2A>예제를 보려면.</xref:System.Linq.Enumerable.AsEnumerable%2A>  
  
## <a name="related-sections"></a>관련 단원  
 다음 링크 기능에 따라 다양 한 표준 쿼리 연산자에 대 한 추가 정보를 제공 하는 항목으로 이동 합니다.  
  
 [데이터 정렬](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [집합 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [데이터 필터링 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [수량자 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [프로젝션 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [데이터 분할 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [조인 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [데이터 그룹화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [생성 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [같음 연산 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [요소 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [데이터 형식 (Visual Basic) 변환](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [연결 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [집계 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable></xref:System.Linq.Queryable>   
 [LINQ (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)   
 [표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [실행 (Visual Basic) 방식에 따라 표준 쿼리 연산자 분류](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)   
 [확장명 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
