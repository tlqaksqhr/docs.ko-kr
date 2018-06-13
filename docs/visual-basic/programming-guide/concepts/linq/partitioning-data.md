---
title: 데이터 분할 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 17e929d3c95e079a0a73b8e8cadf51d3ece6f5f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645914"
---
# <a name="partitioning-data-visual-basic"></a>데이터 분할 (Visual Basic)
LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.  
  
 다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다. 첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다. 두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다. 세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.  
  
 ![LINQ 분할 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.  
  
## <a name="operators"></a>연산자  
  
|연산자 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|시퀀스에서 지정한 위치까지 요소를 건너뜁니다.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|시퀀스에서 지정된 위치까지 요소를 사용합니다.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="skip"></a>Skip  
 다음 코드 예제에서는 `Skip` 절에 나머지를 반환 하기 전에 문자열의 배열에서 처음 4 개의 문자열을 건너뛰도록 Visual Basic의 배열에 있는 문자열입니다.  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 다음 코드 예제에서는 `Skip While` 절에는 문자열의 첫 번째 문자는 배열에서 문자열을 건너뛰도록 Visual Basic의 "a"입니다. 배열에서 나머지 문자열이 반환 됩니다.  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 다음 코드 예제에서는 `Take` 절 Visual basic의 문자열의 배열에서 처음 두 개의 문자열을 반환 합니다.  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 다음 코드 예제에서는 `Take While` Visual basic의 문자열의 길이 5 개 이하의 배열에서 문자열을 반환 하는 절.  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq>  
 [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Skip 절](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Skip While 절](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take 절](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [Take While 절](../../../../visual-basic/language-reference/queries/take-while-clause.md)
