---
title: "수량자 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
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
ms.openlocfilehash: 7f69aed2e0e6791ca7f17c3420ff75a1ba220187
ms.lasthandoff: 03/13/2017

---
# <a name="quantifier-operations-visual-basic"></a>수량자 작업 (Visual Basic)
수량자 작업에서 반환 된 <xref:System.Boolean>시퀀스의 요소 중 일부 또는 모두에 조건을 만족 하는지 여부를 나타내는 값입니다.</xref:System.Boolean>  
  
 다음 그림에서는 두 개의 서로 다른 소스 시퀀스에서 두 개의 다른 수량자 작업을 보여 줍니다. 첫 번째 작업 인지 묻고 요소 중 하나 이상이 문자 'A', 결과 `true`합니다. 두 번째 작업 인지 묻고 모든 요소는 문자 'A', 결과 `true`합니다.  
  
 ![LINQ 수량자 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 수량자 작업을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|모두|시퀀스의 모든 요소가 조건을 만족 하는지 여부를 결정 합니다.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|임의의 값|시퀀스의 모든 요소가 조건을 만족 하는지 여부를 결정 합니다.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|포함|시퀀스에 지정 된 요소가 들어 있는지 여부를 결정 합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
 이 예제에서는 사용 된 `Aggregate` Visual basic LINQ 쿼리에서 필터링 조건의 일부로 절.  
  
 다음 예제에서는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.All%2A>확장 메서드를가지고 있는 애완 동물 모두 지정 된 보존 기간 보다 오래 된 사용자는 컬렉션에서 반환할.</xref:System.Linq.Enumerable.All%2A>  
  
 [!code-vb[CsLINQAnyAll #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 사용 하 여 다음 예제는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.Any%2A>하나 이상 포함 하는 사람들 있는 애완 동물을 컬렉션에서 반환할 확장 메서드는 지정 된 기간 보다 오래 된.</xref:System.Linq.Enumerable.Any%2A>  
  
 [!code-vb[CsLINQAnyAll #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
