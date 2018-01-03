---
title: "식 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: def78e45fa59fafbc6b8e5ffec7273f755e49d29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="comparison-expressions"></a>식 비교
비교 식은 상수 값, 속성 값, 메서드 결과가 다른 값과 같은지, 같지 않은지, 다른 값보다 큰지, 작은지를 확인합니다. 특정 비교가 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]에 유효하지 않으면 예외가 throw됩니다. 암시적이든 명시적이든 모든 비교를 수행하려면 데이터 소스의 모든 구성 요소가 비교 가능한 항목이어야 합니다. 비교 식은 쿼리 결과를 제한하기 위해 `Where` 절에서 자주 사용됩니다.  
  
 다음 쿼리 식 구문 예제에서는 판매 주문 번호가 "SO43663"인 경우 결과를 반환하는 쿼리를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 다음 메서드 기반 쿼리 구문 예제에서는 판매 주문 번호가 "SO43663"인 경우 결과를 반환하는 쿼리를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 다음 쿼리 식 구문 예제에서는 운송 날짜가 2001년 7월 8일인 경우 판매 주문 정보를 반환하는 쿼리를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 다음 메서드 기반 쿼리 구문 예제에서는 운송 날짜가 2001년 7월 8일인 경우 판매 주문 정보를 반환하는 쿼리를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 상수를 생성하는 식은 서버에서 변환되며 로컬 계산은 수행되지 않습니다. 다음 예제에서는 상수를 생성하는 `Where` 절의 식을 사용합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]에서는 상수 형태의 사용자 클래스를 사용할 수 없습니다. 하지만 사용자 클래스에서 속성 참조는 상수로 간주되며 명령 트리 상수 식으로 변환되고 데이터 소스에서 실행됩니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 상수 식을 반환하는 메서드는 지원되지 않습니다. 다음 예제에는 상수를 반환하는 `Where` 절의 메서드가 포함됩니다. 이 예제에서는 런타임에 예외가 throw됩니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities 쿼리의 식](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
