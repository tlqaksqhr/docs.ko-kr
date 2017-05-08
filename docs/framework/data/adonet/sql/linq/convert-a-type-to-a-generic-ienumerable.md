---
title: "형식을 제네릭 IEnumerable로 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 형식을 제네릭 IEnumerable로 변환
<xref:System.Linq.Enumerable.AsEnumerable%2A>을 사용하여 제네릭 `IEnumerable`로 형식화된 인수를 반환합니다.  
  
## 예제  
 이 예제에서는 기본 제네릭 `Query`를 사용하여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리를 SQL로 변환하여 해당 쿼리를 서버에서 실행합니다.  그러나 `where` 절에서는 SQL로 변환할 수 없는 사용자 정의 클라이언트측 메서드\(`isValidProduct`\)를 참조합니다.  
  
 이 솔루션에서는 `where`의 클라이언트측 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 구현을 지정하여 제네릭 <xref:System.Linq.IQueryable%601>을 대체합니다.  이 작업은 <xref:System.Linq.Enumerable.AsEnumerable%2A> 연산자를 호출하여 수행합니다.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## 참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)