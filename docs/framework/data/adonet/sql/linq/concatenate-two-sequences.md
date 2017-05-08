---
title: "두 시퀀스 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 두 시퀀스 연결
<xref:System.Linq.Queryable.Concat%2A> 연산자를 사용하여 두 시퀀스를 연결합니다.  
  
 <xref:System.Linq.Queryable.Concat%2A> 연산자는 수신자와 인수의 순서가 동일하게 정렬된 다중 집합에 대해 정의되어 있습니다.  
  
 SQL의 정렬은 결과 생성 전에 수행되는 최종 단계입니다.  이러한 이유로 인해 <xref:System.Linq.Queryable.Concat%2A> 연산자는 `UNION ALL`을 사용하여 구현되며 해당 인수의 순서를 유지하지 않습니다.  결과에 정렬을 올바르게 하려면 결과를 명시적으로 정렬해야 합니다.  
  
## 예제  
 이 예제에서는 <xref:System.Linq.Queryable.Concat%2A>을 사용하여 모든 `Customer`와 `Employee`에 대한 전화 번호 및 팩스 번호의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## 예제  
 이 예제에서는 <xref:System.Linq.Queryable.Concat%2A>을 사용하여 모든 `Customer`와 `Employee`에 대한 이름 및 전화 번호 매핑의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## 참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [표준 쿼리 연산자 변환](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)