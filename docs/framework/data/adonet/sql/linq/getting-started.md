---
title: "시작(LINQ to SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 시작(LINQ to SQL)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하면 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 기술을 사용하여 메모리 내 컬렉션에 액세스하는 것처럼 SQL 데이터베이스에 액세스할 수 있습니다.  
  
 예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `London`에서 `Customers`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.  
  
 루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## 다음 단계  
 삽입 및 업데이트를 포함하는 몇 가지 다른 예제를 보려면 [LINQ to SQL을\- 사용하여 할 수 있는 작업](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)을 참조하세요.  
  
 그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요.  [연습을 통한 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)을 참조하세요.  
  
 마지막으로, 사용자의 고유한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 시작하는 방법을 배우려면 [LINQ to SQL을 사용하는 일반적인 단계](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)를 참조하세요.  
  
## 참고 항목  
 [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)   
 [Introduction to LINQ](../../../../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)