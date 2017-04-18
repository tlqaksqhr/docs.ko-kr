---
title: "메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet)
이 항목의 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> 및 <xref:System.Linq.Enumerable.Union%2A> 연산자를 사용하여 데이터 행 집합에 대해 값 기반 비교 연산을 수행하는 방법을 보여 줍니다.[DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) <xref:System.Data.DataRowComparer>에 대한 자세한 내용은 [DataRow 비교](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)를 참조하세요.  
  
 이러한 예제에 사용된 `FillDataSet` 메서드에 대한 자세한 내용은 [DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)를 참조하세요.  
  
 이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음과 같은 `using`\/`Imports` 문을 사용합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)을 참조하세요.  
  
## Distinct  
  
### 예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A> 메서드를 사용하여 시퀀스의 중복 요소를 제거합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## Except  
  
### 예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Except%2A> 메서드를 사용하여 첫 번째 테이블에만 있고 두 번째 테이블에는 없는 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## Intersect  
  
### 예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Intersect%2A> 메서드를 사용하여 두 테이블 모두에 있는 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## 공용 구조체  
  
### 예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Union%2A> 메서드를 사용하여 두 테이블 중 한 테이블에만 있는 고유 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## 참고 항목  
 [DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)