---
title: "크로스 테이블 쿼리(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 크로스 테이블 쿼리(LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서는 단일 테이블 쿼리뿐 아니라 크로스 테이블 쿼리도 수행할 수 있습니다. 이 작업은 *조인*을 사용하여 수행됩니다.  조인은 한 데이터 소스의 개체를 공통 특성\(예: 제품 또는 연락처 ID\)을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.  개체 지향적 프로그래밍의 경우 각 개체에 다른 개체를 참조하는 멤버가 있으므로 개체 간의 관계를 탐색하기가 비교적 쉽습니다. 그러나 외부 데이터베이스 테이블에서는 관계를 탐색하기가 쉽지 않습니다.  데이터베이스 테이블에는 기본 제공 관계가 없습니다. 이러한 경우 조인 연산을 사용하여 각 소스의 요소를 연결할 수 있습니다.  예를 들어 제품 정보와 판매 정보가 들어 있는 두 테이블이 있는 경우 조인 연산을 사용하여 동일한 판매 주문에 대한 판매 정보와 제품을 연결할 수 있습니다.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 프레임워크에는 <xref:System.Linq.Enumerable.Join%2A>과 <xref:System.Linq.Enumerable.GroupJoin%2A>이라는 두 개의 조인 연산자가 있습니다. 이러한 연산자는 키가 같은 경우에만 두 데이터 소스를 연결하는 조인인 *동등 조인*을 수행합니다.  반면 [!INCLUDE[tsql](../../../../includes/tsql-md.md)]은 `equals` 이외의 조인 연산자\(예: `less than` 연산자\)를 지원합니다.  
  
 관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>은 내부 조인을 구현합니다.  내부 조인은 상대 데이터 집합에 일치하는 항목이 있는 개체만 반환되는 조인입니다.  
  
 동등한 관계형 데이터베이스 용어가 없는 <xref:System.Linq.Enumerable.GroupJoin%2A> 연산자는 내부 조인 및 왼쪽 우선 외부 조인의 상위 집합을 구현합니다. 왼쪽 우선 외부 조인은 두 번째 컬렉션에 관계가 있는 요소가 없더라도 첫 번째\(왼쪽\) 컬렉션의 각 요소를 반환하는 조인입니다.  
  
 조인에 대한 자세한 내용은 [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md)\(을\)를 참조하세요.  
  
## 예제  
 다음 예제에서는 AdventureWorks 샘플 데이터베이스의 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 기존 방식의 조인을 수행하여 8월의 온라인 주문을 가져옵니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## 참고 항목  
 [DataSet 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [단일 테이블 쿼리](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)   
 [형식화된 데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)