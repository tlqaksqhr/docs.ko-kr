---
title: "투영 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 투영 작성
다음 예제에서는 C\#의 `select` 문과 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 문을 다른 기능과 함께 사용하여 쿼리 투영을 만드는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)을 사용하여 `Customers`에 대한 연락처 이름의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *익명 형식*을 사용하여 `Customers`에 대한 연락처 이름 및 전화 번호의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *익명 형식*을 사용하여 직원에 대한 이름 및 전화 번호의 시퀀스를 반환합니다.  결과 시퀀스에서 `FirstName`과 `LastName` 필드는 단일 필드\(`Name`\)로 결합되고 `HomePhone` 필드는 `Phone`으로 이름이 변경됩니다.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *익명 형식*을 사용하여 모든 `ProductID`와 `HalfPrice`라는 계산된 값의 시퀀스를 반환합니다.  이 값은 2로 나누어진 `UnitPrice`로 설정됩니다.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *조건문*을 사용하여 제품 이름과 제품 사용 가능성의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *알려진 형식*\(Name\)을 사용하여 직원 이름의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select`와 `Where`\(C\#의 `select`와 `where`\)를 사용하여 London에 있는 고객에 대한 연락처 이름의 *필터링된 시퀀스*를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]의 `Select` 절\(C\#의 `select` 절\)과 *익명 형식*을 사용하여 고객에 대한 데이터의 *생성된 하위 집합*을 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## 예제  
 다음 예제에서는 중첩된 쿼리를 사용하여 다음 결과를 반환합니다.  
  
-   모든 주문의 시퀀스와 해당 `OrderID`입니다.  
  
-   할인이 있는 주문 항목에 대한 시퀀스입니다.  
  
-   운송 비용이 포함되지 않은 총 금액입니다.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## 참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)