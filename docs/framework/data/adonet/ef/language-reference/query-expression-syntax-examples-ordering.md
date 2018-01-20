---
title: "쿼리 식 구문 예제: 정렬"
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
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 09cc843bd56d4b9c8c13dba7883e10c6a7834cb6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="query-expression-syntax-examples-ordering"></a>쿼리 식 구문 예제: 정렬
이 항목의 예제에 사용 하는 방법을 보여 줍니다는 `OrderBy` 및 `OrderByDescending` 를 쿼리 하는 메서드는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 쿼리 식 구문을 사용 합니다. 이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a>OrderBy  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성을 기준으로 정렬된 연락처 목록을 반환합니다.  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성의 길이를 기준으로 연락처 목록을 정렬합니다.  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a>OrderByDescending  
  
### <a name="example"></a>예제  
 다음 예제에서는 `orderby… descending` 메서드와 같은 `Order By … Descending`(Visual Basic에서는 <xref:System.Linq.Enumerable.OrderByDescending%2A>)을 사용하여 가격 목록을 내림차순으로 정렬합니다.  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenBy%2A>를 사용하여 성을 기준으로 정렬한 다음 이름을 기준으로 다시 정렬한 연락처 목록을 반환합니다.  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a>ThenByDescending  
  
### <a name="example"></a>예제  
 다음 예제에서는 `OrderBy… Descending` 메서드와 같은 <xref:System.Linq.Enumerable.ThenByDescending%2A>을 사용하여 이름과 가격을 각각 1차 및 2차 정렬 기준으로 삼아 내림차순으로 제품 목록을 정렬합니다.  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
