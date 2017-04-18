---
title: "메서드 기반 쿼리 구문 예제: 관계 탐색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 메서드 기반 쿼리 구문 예제: 관계 탐색
[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]의 탐색 속성은 연결의 End에서 엔터티를 찾는 데 사용되는 바로 가기 속성입니다.  탐색 속성을 사용하면 엔터티 간에 탐색하거나 연결 집합을 통해 관련 엔터티 간에 탐색할 수 있습니다.  이 항목에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서 탐색 속성을 통해 관계를 탐색하는 방법을 보여 주는 메서드 기반 쿼리 구문 예제를 제공합니다.  
  
 이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음과 같은 `using`\/`Imports` 문을 사용합니다.  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## 예제  
 메서드 기반 쿼리 구문을 사용하는 다음 예제에서는 <xref:System.Linq.Queryable.SelectMany%2A> 메서드를 사용하여 성이 "Zhou"인 연락처의 모든 주문을 가져옵니다.  `Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## 예제  
 메서드 기반 쿼리 구문을 사용하는 다음 예제에서는 <xref:System.Linq.Queryable.Select%2A> 메서드를 사용하여 성이 "Zhou"인 각 연락처의 총 금액 합계와 연락처 ID를 모두 가져옵니다.  `Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.  `Sum` 메서드는 `Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 모든 주문에 대한 총 금액을 더합니다.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## 예제  
 메서드 기반 쿼리 구문의 다음 예제에서는 성이 "Zhou"인 연락처의 모든 주문을 가져옵니다.  `Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.  연락처의 이름과 주문은 익명 형식으로 반환됩니다.  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## 예제  
 다음 예제에서는 `SalesOrderHeader.Address` 및 `SalesOrderHeader.Contact` 탐색 속성을 사용하여 서로 연결된 `Address` 및 `Contact` 개체의 컬렉션을 가져옵니다.  Seattle 시로 가는 각 주문에 대한 연락처의 성, 주소, 판매 주문 번호 및 총 주문 금액이 익명 형식으로 반환됩니다.  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## 예제  
 다음 예제에서는 `Where` 메서드를 사용하여 2003년 12월 1일 이후의 주문을 찾은 다음 `order.SalesOrderDetail` 탐색 속성을 사용하여 각 주문의 세부 사항을 가져옵니다.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## 참고 항목  
 [Navigation Properties](http://msdn.microsoft.com/ko-kr/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)   
 [LINQ to Entities의 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)