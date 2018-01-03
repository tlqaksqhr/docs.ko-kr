---
title: "메서드 기반 쿼리 구문 예제: 정렬(LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6496d628538caa6cd0af328e6594f8453b40afb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a>메서드 기반 쿼리 구문 예제: 정렬(LINQ to DataSet)
이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드에서 메서드 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.  
  
 `FillDataSet` 에 이러한 예제에서 사용 하는 방법이 지정 되어 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.  
  
 이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 자세한 내용은 참조 [하는 방법: Visual Studio에서 데이터 집합 프로젝트에 LINQ 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.  
  
## <a name="orderby"></a>OrderBy  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드를 사용자 지정 비교자와 함께 사용하여 대소문자 구분 없이 성을 정렬합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a>Reverse  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Reverse%2A> 메서드를 사용하여 `OrderDate`가 2002년 2월 20일 이전인 주문 목록을 만듭니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 및 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드를 사용자 지정 비교자와 함께 사용하여 먼저 가격을 기준으로 정렬한 다음 대소문자 구분 없이 제품 이름을 내림차순으로 정렬합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 데이터 집합에 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
