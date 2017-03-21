---
title: "집계 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
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
ms.openlocfilehash: 17d1f18f9acc2f3a62c106f7cff2cf68f8f58a07
ms.lasthandoff: 03/13/2017

---
# <a name="aggregation-operations-visual-basic"></a>집계 작업 (Visual Basic)
집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다. 예를 들어&1;달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.  
  
 다음 그림에서는 숫자 시퀀스에서 두 개의 다른 집계 작업의 결과 보여 줍니다. 첫 번째 작업의 합계를 구합니다. 두 번째 작업 시퀀스의 최대값을 반환 합니다.  
  
 ![LINQ 집계 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 집계 작업을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregate|컬렉션의 값에 사용자 지정 집계 연산을 수행합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|평균|값의 컬렉션의 평균 값을 계산합니다.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName></xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|개수|필요에 따라 해당 요소만 조건자 함수를 충족 하는 요소 컬렉션을 계산 합니다.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName></xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|LongCount|큰 컬렉션에서 요소 필요에 따라 요소에 대해서만 계산 수를 계산 합니다.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|최대|컬렉션의 최대값을 결정합니다.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName></xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|최소|컬렉션의 최소값을 결정합니다.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName></xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|Sum|컬렉션에 있는 값의 합계를 계산합니다.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName></xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="average"></a>Average  
 다음 코드 예제에서는 `Aggregate Into Average` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 기온을 나타내는 숫자의 배열에서 평균 기온을 계산 합니다.  
  
 [!code-vb[CsLINQAggregating #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a>개수  
 다음 코드 예제에서는 `Aggregate Into Count` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 80 보다 크거나 있는 배열에 있는 값의 수를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a>LongCount  
 다음 코드 예제에서는 `Aggregate Into LongCount` 절을 배열에 있는 값의 수를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a>최대  
 다음 코드 예제에서는 `Aggregate Into Max` 절 기온을 나타내는 숫자의 배열에서 최대 기온을 계산 합니다.  
  
 [!code-vb[CsLINQAggregating #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a>최소  
 다음 코드 예제에서는 `Aggregate Into Min` 기온을 나타내는 숫자의 배열에 최소 온도 계산 하는 절.  
  
 [!code-vb[CsLINQAggregating #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a>Sum  
 다음 코드 예제에서는 `Aggregate Into Sum` 비용을 나타내는 값의 배열에서 총 비용 금액을 계산 하는 절.  
  
 [!code-vb[CsLINQAggregating #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [방법: CSV 텍스트 파일 (Visual Basic) (LINQ)의 열 값 계산](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)   
 [방법: 개수, 합 또는 평균 데이터](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)   
 [방법: 쿼리 결과의 최소값 또는 최대값 찾기](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)   
 [방법: 파일 또는 디렉터리 트리 (LINQ) (Visual Basic)에서 파일에 대 한 가장 큰 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)   
 [방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
