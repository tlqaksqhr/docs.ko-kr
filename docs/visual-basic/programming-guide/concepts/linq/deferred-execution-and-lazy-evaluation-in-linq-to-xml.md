---
title: "실행 및 LINQ to XML (Visual Basic)에서 지연 계산을 지연 | Microsoft 문서"
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
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3b7318eb9853d633d152b93fafcf9570ccd03835
ms.lasthandoff: 03/13/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a>지연 된 실행과 지연 계산은 linq to XML (Visual Basic)
쿼리 및 축 연산은 흔히 지연된 실행을 사용하도록 구현됩니다. 이 항목에서는 지연된 실행의 요구 사항 및 장점과 몇 가지 구현 고려 사항에 대해 설명합니다.  
  
## <a name="deferred-execution"></a>지연된 실행  
 지연 될 때까지 식의 계산이 지연 되는 실행 의미의 *실현* 값이 실제로 필요 합니다. 지연된 실행은 특히 일련의 연결된 쿼리나 조작이 포함된 프로그램에서 큰 데이터 컬렉션을 조작해야 하는 경우 성능을 크게 높일 수 있습니다. 최상의 경우에는 지연된 실행을 통해 소스 컬렉션을 한 번만 반복할 수 있습니다.  
  
 LINQ 기술은 광범위 하 게 사용 지연 된 실행의 핵심 멤버에서 <xref:System.Linq?displayProperty=fullName>클래스 <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</xref:System.Xml.Linq.Extensions?displayProperty=fullName> 등 다양 한 LINQ 네임 스페이스의 확장 메서드와</xref:System.Linq?displayProperty=fullName>  
  
## <a name="eager-vs-lazy-evaluation"></a>즉시 계산과 지연 계산 비교  
 지연된 실행을 구현하는 메서드를 작성하는 경우 지연 계산이나 즉시 계산 중에서 메서드 구현에 사용할 방법을 결정해야 합니다.  
  
-   *지연 평가*, 소스 컬렉션의 단일 요소가 반복기를 호출할 때마다 처리 됩니다. 이것이 반복기가 구현되는 일반적인 방법입니다.  
  
-   *즉시 평가*, 반복기를 처음으로 호출 하면 전체 컬렉션이 처리 됩니다. 소스 컬렉션의 임시 복사본도 필요할 수 있습니다. 예를 들어는 <xref:System.Linq.Enumerable.OrderBy%2A>메서드에 첫 번째 요소를 반환 하기 전에 전체 컬렉션을 정렬 하는.</xref:System.Linq.Enumerable.OrderBy%2A>  
  
 지연 계산은 컬렉션의 계산 전반에 오버헤드 처리를 균일하게 분산시키고 임시 데이터를 최소한으로 사용하기 때문에 대개 성능이 더 좋습니다. 물론 중간 결과를 구체화해야만 하는 연산도 있습니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 자습서의 다음 항목에서는 지연된 실행을 보여 줍니다.  
  
-   [지연된 실행 예제 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서: 지연 된 실행 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)   
 [개념 및 용어 (함수 변환) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)   
 [집계 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
