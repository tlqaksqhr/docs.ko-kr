---
title: "두 시퀀스 간의 차집합 반환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 두 시퀀스 간의 차집합 반환
<xref:System.Linq.Queryable.Except%2A> 연산자를 사용하여 두 시퀀스 간의 차집합을 반환합니다.  
  
## 예제  
 이 예제에서는 <xref:System.Linq.Queryable.Except%2A>을 사용하여 `Customers`는 살지만 `Employees`가 살지 않는 모든 국가의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Except%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.  다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.  
  
## 참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [표준 쿼리 연산자 변환](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)