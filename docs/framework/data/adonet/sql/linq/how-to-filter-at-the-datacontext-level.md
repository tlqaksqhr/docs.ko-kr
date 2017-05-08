---
title: "방법: DataContext 수준에서 필터링 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: DataContext 수준에서 필터링
`DataContext` 수준에서 `EntitySets`를 필터링할 수 있습니다.  이러한 필터는 <xref:System.Data.Linq.DataContext> 인스턴스로 수행되는 모든 쿼리에 적용됩니다.  
  
## 예제  
 다음 예제에서는 `ShippedDate` 기준으로 고객의 미리 로드된 주문을 필터링하기 위해 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=fullName>가 사용됩니다.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## 참고 항목  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)