---
title: 초기화 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 352bda826c3b872d06252e168abfb1129f178bf8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762210"
---
# <a name="initialization-expressions"></a>초기화 식
초기화 식은 새 개체를 초기화합니다. 최신 C# 3.0 및 Visual Basic 9.0 초기화 식을 포함하여 대부분의 초기화 식이 지원됩니다. LINQ to Entities 쿼리를 통해 다음 형식을 초기화하고 반환할 수 있습니다.  
  
-   개념적 모델에 정의된 0개 이상의 형식화된 엔터티 개체 컬렉션 또는 복합 형식의 프로젝션  
  
-   [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 지원되는 CLR 형식  
  
-   인라인 컬렉션  
  
-   익명 형식  
  
 다음 쿼리 식 구문 예제에서는 익명 형식 초기화를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 다음 메서드 기반 쿼리 구문의 예제에서는 익명 형식 초기화를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 사용자 정의 클래스 초기화도 지원됩니다. C# 3.0 및 Visual Basic 9.0 초기화 패턴이 지원되며, 속성 getter 및 setter가 대칭이라고 가정합니다. 다음 쿼리 식 구문 예제에서는 쿼리에서의 사용자 지정 클래스 초기화를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 다음 메서드 기반 쿼리 구문 예제에서는 쿼리에서의 사용자 지정 클래스 초기화를 보여 줍니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities 쿼리의 식](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
