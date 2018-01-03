---
title: "DataView로 정렬(LINQ to DataSet)"
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
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ae9ee83802b71eeab63fe5305b49d79a5cfaaf39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>DataView로 정렬(LINQ to DataSet)
특정 조건을 기준으로 데이터를 정렬한 다음 UI 컨트롤을 통해 클라이언트에 데이터를 제공하는 기능은 데이터 바인딩의 중요한 기능입니다. <xref:System.Data.DataView>에서는 데이터를 정렬하여 특정 정렬 기준에 따라 정렬된 데이터 행을 반환하는 여러 방법을 제공합니다. 문자열 기반 하는 것 외에도 정렬 기능 <xref:System.Data.DataView> 도 사용할 수 있습니다 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 정렬 기준에 대 한 식입니다. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]문자열 기반 정렬 보다 훨씬 더 복잡 하 고 강력한 정렬 작업에 대 한 식을 사용 합니다. 이 항목에서는 <xref:System.Data.DataView>를 사용하여 정렬하는 두 가지 방법을 모두 설명합니다.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>정렬 정보가 있는 쿼리에서 DataView 만들기  
 <xref:System.Data.DataView> 개체는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리에서 만들 수 있습니다. 해당 쿼리에 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A> 또는 <xref:System.Linq.Enumerable.ThenByDescending%2A> 절이 있는 경우 이러한 절의 식은 <xref:System.Data.DataView>의 데이터를 정렬하기 위한 기본 요소로 사용됩니다. 예를 들어 쿼리에 `Order By…` 및 `Then By…` 절이 있는 경우 결과 <xref:System.Data.DataView>는 지정된 두 열을 기준으로 데이터를 정렬합니다.  
  
 식 기반 정렬은 간단한 문자열 기반 정렬에 비해 강력하고 복잡한 정렬 기능을 제공합니다. 문자열 기반 정렬 및 식 기반 정렬은 함께 사용할 수 없습니다. 쿼리에서 <xref:System.Data.DataView.Sort%2A>를 만든 후에 문자열 기반 <xref:System.Data.DataView>를 설정하면 쿼리에서 유추된 식 기반 필터가 지워지며, 이 필터는 재설정할 수 없습니다.  
  
 <xref:System.Data.DataView>의 인덱스는 <xref:System.Data.DataView>가 만들어지거나 정렬 또는 필터링 정보가 수정될 때 작성됩니다. 최적의 성능을 얻으려면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]가 만들어진 <xref:System.Data.DataView> 쿼리에 정렬 기준을 제공한 다음 이후에 정렬 정보를 수정하지 않아야 합니다. 자세한 내용은 참조 [DataView 성능](../../../../docs/framework/data/adonet/dataview-performance.md)합니다.  
  
> [!NOTE]
>  대부분의 경우 정렬에 사용되는 식은 파생 효과가 없어야 하고 명확해야 합니다. 또한 정렬 작업이 여러 번 실행될 수 있으므로 이러한 식에는 실행 집합 번호에 따라 달라지는 논리가 없어야 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 SalesOrderHeader 테이블을 쿼리하여 반환된 행을 주문 날짜를 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>예제  
 다음 예제에서는 SalesOrderHeader 테이블을 쿼리하여 반환된 행을 합계 금액을 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>예제  
 다음 예제에서는 SalesOrderDetail 테이블을 쿼리하여 반환된 행을 주문 수량과 판매 주문 ID를 기준으로 정렬한 다음 해당 쿼리에서 <xref:System.Data.DataView>를 만들고 <xref:System.Data.DataView>를 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>문자열 기반 정렬 속성 사용  
 <xref:System.Data.DataView>의 문자열 기반 정렬 기능은 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서 계속 사용할 수 있습니다. <xref:System.Data.DataView> 쿼리에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]를 만든 후에는 <xref:System.Data.DataView.Sort%2A> 속성을 사용하여 <xref:System.Data.DataView>에 대한 정렬을 설정할 수 있습니다.  
  
 문자열 기반 정렬 및 식 기반 정렬 기능은 함께 사용할 수 없습니다. <xref:System.Data.DataView.Sort%2A> 속성을 설정하면 <xref:System.Data.DataView>가 만들어진 쿼리에서 상속된 식 기반 정렬이 지워집니다.  
  
 문자열 기반 하는 방법에 대 한 자세한 내용은 <xref:System.Data.DataView.Sort%2A> 참조 필터링 [정렬 및 필터링 데이터](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 내림차순으로 행을 정렬하고, 이름을 기준으로 오름차순으로 행을 정렬합니다.  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>예제  
 다음 예제에서는 Contact 테이블에 대해 &quot;S&quot;로 시작하는 성을 쿼리합니다.  해당 쿼리에서 <xref:System.Data.DataView>가 만들어지고 <xref:System.Windows.Forms.BindingSource> 개체에 바인딩됩니다.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>정렬 지우기  
 <xref:System.Data.DataView>의 정렬 정보는 설정된 후에 <xref:System.Data.DataView.Sort%2A> 속성을 사용하여 지울 수 있습니다. 두 가지 방법으로 <xref:System.Data.DataView>의 정렬 정보를 지울 수 있습니다.  
  
-   <xref:System.Data.DataView.Sort%2A> 속성을 `null`으로 설정합니다.  
  
-   <xref:System.Data.DataView.Sort%2A> 속성을 빈 문자열로 설정합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 쿼리에서 <xref:System.Data.DataView>를 만든 다음 <xref:System.Data.DataView.Sort%2A> 속성을 빈 문자열로 설정하여 정렬을 지웁니다.  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>예제  
 다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 내림차순으로 정렬하도록 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다. 그런 다음 <xref:System.Data.DataView.Sort%2A> 속성을 `null`로 설정하여 정렬 정보를 지웁니다.  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 및 LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 [DataView로 필터링](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 [데이터 정렬](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)
