---
title: "조인 및 외적 쿼리 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 조인 및 외적 쿼리 작성
다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `From` 절\(C\#에서는 `from` 절\)에서 외래 키 탐색을 사용하여 London에 있는 고객에 대한 모든 주문을 선택합니다.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Where` 절\(C\#에서는 `where` 절\)에서 외래 키 탐색을 사용하여 `Supplier`가 미국에 있는 품절된 `Products`를 필터링합니다.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `From` 절\(C\#에서는 `from` 절\)에서 외래 키 탐색을 사용하여 시애틀에 있는 직원과 그들의 지역을 나열합니다.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#에서는 `select` 절\)에서 외래 키 탐색을 사용하여 한 직원이 다른 직원에게 보고하는 직원 쌍과 같은 `City` 출신의 직원 쌍을 필터링합니다.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## 예제  
 다음 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 예제에서는 모든 고객과 주문을 검색하고 주문이 고객과 일치하도록 하며 해당 목록의 모든 고객에 대한 연락처 이름이 제공되도록 합니다.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## 예제  
 다음 예제에서는 두 테이블과 두 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## 예제  
 다음 예제에서는 세 테이블과 각 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## 예제  
 다음 예제에서는 `DefaultIfEmpty()`를 사용하여 `LEFT OUTER JOIN`을 얻는 방법을 보여 줍니다.  `Employee`에 `Order`가 없는 경우 `DefaultIfEmpty()` 메서드는 null을 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## 예제  
 다음 예제에서는 조인으로 인해 생성된 `let` 식을 보여 줍니다..  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## 예제  
 다음 예제에서는 복합 키와 함께 사용된 `join`을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## 예제  
 다음 예제에서는 한 면이 nullable이고 다른 면은 nullable이 아닌 `join`을 생성하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## 참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)