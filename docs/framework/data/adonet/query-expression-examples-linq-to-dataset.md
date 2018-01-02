---
title: "쿼리 식 예제(LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d959d28f50cef7820702ae535dcc3307e59cf080
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="query-expression-examples-linq-to-dataset"></a>쿼리 식 예제(LINQ to DataSet)
이 단원에서는 표준 쿼리 연산자를 사용하는 쿼리 식 구문으로 작성된 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 프로그래밍 예제를 제공합니다. <xref:System.Data.DataSet> 이러한 예에서 사용 된를 사용 하 여 채워집니다는 `FillDataSet` 에 지정 된 메서드를 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다. 자세한 내용은 참조 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [프로젝션](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
 [제한 사항](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Where%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
 [분할](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 분할하는 방법을 보여 줍니다.  
  
 [정렬](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenByDescending%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.  
  
 [요소 연산자](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 <xref:System.Data.DataRow>에서 <xref:System.Data.DataSet> 요소를 가져오는 방법을 보여 줍니다.  
  
 [집계 연산자](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.  
  
 [조인 연산자](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 <xref:System.Linq.Enumerable.Join%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [메서드 기반 쿼리 예제](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 [DataSet별 연산자 예제](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
