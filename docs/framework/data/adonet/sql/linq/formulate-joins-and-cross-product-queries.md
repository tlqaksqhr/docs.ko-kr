---
title: '방법: 조인 및 교차곱 쿼리 작성'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 468ee54b0936afcbb548249bc714ea4b04abd3de
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="formulate-joins-and-cross-product-queries"></a>방법: 조인 및 교차곱 쿼리 작성
다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 외래 키 탐색을 사용 하 여 다음 예제는 `From` Visual Basic의 절 (`from` 절에 C#) 런던에 고객에 대 한 모든 주문을 선택 하 합니다.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>예제  
 외래 키 탐색을 사용 하 여 다음 예제는 `Where` Visual Basic의 절 (`where` 절에 C#) 재고 아웃에 대해 필터링 할 `Products` 인 `Supplier` 미국에 합니다.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>예제  
 외래 키 탐색을 사용 하 여 다음 예제는 `From` Visual Basic의 절 (`from` 절에 C#) 시애틀의 직원에 대 한 필터링 하 고 그들의 지역을 나열 합니다.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>예제  
 외래 키 탐색을 사용 하 여 다음 예제는 `Select` Visual Basic의 절 (`select` 절에 C#) 직원이 한 명 다른 보고 하는 위치 및 동일한 직원이 있는의 직원 쌍을 필터링 할 `City`합니다.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>예제  
 다음 Visual Basic에서는 모든 고객과 주문에 대 한 조회 하 고, 고객에 게 주문을 일치 되는 해당 목록의 모든 고객에 대 한 연락처 이름이 제공 되도록 보장 합니다.  
  
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
