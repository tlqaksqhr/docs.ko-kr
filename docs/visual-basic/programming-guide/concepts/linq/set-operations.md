---
title: "집합 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
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
ms.openlocfilehash: e835737b388427445a15b6658c7d148801f29b79
ms.lasthandoff: 03/13/2017

---
# <a name="set-operations-visual-basic"></a>집합 작업 (Visual Basic)
LINQ의 set 작업은 동일 하거나 별도 컬렉션 (또는 집합)에 동등한 요소가 있는지 여부를 기반으로 하는 결과 집합을 생성 하는 쿼리 작업을 가리킵니다.  
  
 집합 작업을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Distinct|컬렉션에서 값 중복을 제거 합니다.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|제외|차집합 즉, 두 번째 컬렉션에 표시 되지 않는 한 컬렉션의 요소를 반환 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|교차|두 컬렉션의 각 항목에 표시 되는 요소를 의미는 교집합을 반환 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|공용 구조체|즉, 두 컬렉션 중 하나에 있는 고유 요소가 합집합을 반환 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a>집합 작업의 비교  
  
### <a name="distinct"></a>Distinct  
 다음 그림의 동작을 보여 줍니다.는 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>메서드 문자 시퀀스를.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> 반환 된 시퀀스는 입력된 시퀀스에서 고유 요소를 포함합니다.  
  
 ![Distinct ()의 동작을 보여 주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "고유")  
  
### <a name="except"></a>제외  
 다음 그림 <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName> 의 동작을 보여 줍니다. 반환 된 시퀀스는 두 번째 입력된 시퀀스에 있지 않은 첫 번째 입력된 시퀀스에서 요소만 포함 합니다.  
  
 ![Except ()의 동작을 보여 주는 그래픽입니다. ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")  
  
### <a name="intersect"></a>교차  
 다음 그림 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName> 의 동작을 보여 줍니다. 반환 된 시퀀스는 입력된 시퀀스의 양쪽에 공통 된 요소를 포함 합니다.  
  
 ![두 시퀀스의 교집합을 보여 주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "교차")  
  
### <a name="union"></a>공용 구조체  
 다음 그림은 문자 두 시퀀스에 대해 union 연산을 보여 줍니다. 반환 된 시퀀스는 두 입력된 시퀀스에서 고유 요소를 포함합니다.  
  
 ![두 시퀀스의 결합을 보여주는 그래픽입니다. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="query-expression-syntax-example"></a>쿼리 식 구문 예제  
 다음 예제에서는 `Distinct` 정수 목록에서 고유한 숫자를 반환 하는 LINQ 쿼리에서 절.  
  
 [!code-vb[CsLINQSetOps #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Distinct 절](../../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [방법: 문자열 컬렉션 (Visual Basic) (LINQ) 결합 및 비교](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)   
 [방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
