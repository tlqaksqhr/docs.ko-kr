---
title: "방법: 조인 및 교차곱 쿼리 작성"
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 703823368f451839304ce02ff8b5f7259a44b935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a>방법: 조인 및 교차곱 쿼리 작성
다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `From`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `from` 절)에서 외래 키 탐색을 사용하여 London에 있는 고객에 대한 모든 주문을 선택합니다.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Where`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `where` 절)에서 외래 키 탐색을 사용하여 `Products`가 미국에 있는 품절된 `Supplier`를 필터링합니다.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `From`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `from` 절)에서 외래 키 탐색을 사용하여 시애틀에 있는 직원과 그들의 지역을 나열합니다.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Select`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `select` 절)에서 외래 키 탐색을 사용하여 한 직원이 다른 직원에게 보고하는 직원 쌍과 같은 `City` 출신의 직원 쌍을 필터링합니다.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 예제에서는 모든 고객과 주문을 검색하고 주문이 고객과 일치하도록 하며 해당 목록의 모든 고객에 대한 연락처 이름이 제공되도록 합니다.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 테이블과 두 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 테이블과 각 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `LEFT OUTER JOIN`를 사용하여 `DefaultIfEmpty()`을 얻는 방법을 보여 줍니다. `DefaultIfEmpty()`에 `Order`가 없는 경우 `Employee` 메서드는 null을 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 조인으로 인해 생성된 `let` 식을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 복합 키와 함께 사용된 `join`을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 면이 nullable이고 다른 면은 nullable이 아닌 `join`을 생성하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
