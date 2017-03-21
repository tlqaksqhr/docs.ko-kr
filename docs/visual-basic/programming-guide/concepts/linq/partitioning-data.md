---
title: "(Visual Basic) 데이터 분할 | Microsoft 문서"
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
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
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
ms.openlocfilehash: a746ce3e24812d1df6b6e221cca0364bf2cc7f1c
ms.lasthandoff: 03/13/2017

---
# <a name="partitioning-data-visual-basic"></a>데이터 분할 (Visual Basic)
Linq에서 분할은 입력된 시퀀스를 요소를 다시 정렬 한 다음 섹션 중 하나를 반환 하지 않고 두 개의 섹션으로 나눈으로 작동 하는 것을 말합니다.  
  
 다음 그림에서는 세 개의 서로 다른 분할 작업 시퀀스에서 문자의 결과 보여 줍니다. 첫 번째 작업 시퀀스에서 처음 세 개의 요소를 반환합니다. 두 번째 작업에서는 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환 합니다. 세 번째 작업 시퀀스에서 처음 두 요소를 생략 하 고 세 개의 요소를 반환 합니다.  
  
 ![LINQ 분할 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 시퀀스를 분할 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="operators"></a>연산자  
  
|연산자 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|시퀀스에서 지정 된 위치까지 요소를 건너뜁니다.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|SkipWhile|요소가 조건을 만족 하지 않을 때까지 조건자 함수를 기반으로 요소를 건너뜁니다.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|Take|시퀀스에서 지정 된 위치까지 요소를 취합니다.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|TakeWhile|요소가 조건을 만족 하지 않을 때까지 조건자 함수를 기반으로 요소를 사용 합니다.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="skip"></a>Skip  
 다음 코드 예제에서는 `Skip` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 배열에서 처음&4; 개의 문자열 배열에서 나머지 문자열을 반환 하기 전에 건너뛸 수 있습니다.  
  
 [!code-vb[CsLINQPartitioning #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 다음 코드 예제에서는 `Skip While` 절에 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 를 건너 뛰 문자열의 첫 글자는 동안 배열에서 문자열은 "a"입니다. 배열에서 나머지 문자열이 반환 됩니다.  
  
 [!code-vb[CsLINQPartitioning #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 다음 코드 예제에서는 `Take` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 배열에서 처음 두 개의 문자열을 반환 합니다.  
  
 [!code-vb[CsLINQPartitioning #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 다음 코드 예제에서는 `Take While` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 길이&5; 개 이하의 배열에서 문자열을 반환 하려면.  
  
 [!code-vb[CsLINQPartitioning #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Skip 절](../../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Skip While 절](../../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take 절](../../../../visual-basic/language-reference/queries/take-clause.md)   
 [Take While 절](../../../../visual-basic/language-reference/queries/take-while-clause.md)
