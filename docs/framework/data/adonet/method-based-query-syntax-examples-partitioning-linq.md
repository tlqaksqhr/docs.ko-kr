---
title: '메서드 기반 쿼리 구문 예제: 분할(LINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: d517b09ac921001ab16216e4950df66dfabda13d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766168"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a>메서드 기반 쿼리 구문 예제: 분할(LINQ
이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.TakeWhile%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
 `FillDataSet` 에 이러한 예제에서 사용 하는 방법이 지정 되어 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.  
  
 이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 자세한 내용은 참조 [하는 방법: Visual Studio에서 데이터 집합 프로젝트에 LINQ 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.  
  
## <a name="skip"></a>Skip  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 메서드를 사용하여 `Contact` 테이블에서 맨 위쪽에 있는 5개의 연락처 정보를 가져옵니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 메서드를 사용하여 Seattle에 있는 처음 2개의 주소를 제외한 모든 주소를 가져옵니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a>SkipWhile  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 및 <xref:System.Linq.Enumerable.SkipWhile%2A> 메서드를 사용하여 `Product` 테이블에서 가격이 300.00보다 높은 제품을 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a>Take  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 `Contact` 테이블에서 맨 위쪽에 있는 5개의 연락처 정보를 가져옵니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 Seattle에 있는 처음 3개의 주소를 가져옵니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a>TakeWhile  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 및 <xref:System.Linq.Enumerable.TakeWhile%2A> 메서드를 사용하여 `Product` 테이블에서 가격이 300.00보다 낮은 제품을 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 데이터 집합에 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
