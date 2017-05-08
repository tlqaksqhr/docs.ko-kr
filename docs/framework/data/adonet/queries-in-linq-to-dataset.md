---
title: "LINQ to DataSet의 쿼리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to DataSet의 쿼리
쿼리는 데이터 소스에서 데이터를 검색하는 식입니다.  관계형 데이터베이스에는 SQL이 사용되고 XML에는 XQuery가 사용되는 것과 같이 쿼리는 일반적으로 특수화된 쿼리 언어로 표현됩니다.  따라서 개발자는 쿼리하는 데이터 소스나 데이터 형식에 따라 새로운 쿼리 언어를 배워야 했습니다.  [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]는 다양한 데이터 소스 및 형식에 사용할 수 있는 간단하고 일관된 모델을 제공합니다.  [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리에서는 항상 프로그래밍 개체를 사용합니다.  
  
 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리 작업은 데이터 소스 가져오기, 쿼리 만들기 및 쿼리 실행으로 구성됩니다.  
  
 <xref:System.Collections.Generic.IEnumerable%601> 제네릭 인터페이스를 구현한 데이터 소스는 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]을 통해 쿼리할 수 있습니다.  <xref:System.Data.DataTable>에 대해 <xref:System.Data.DataTableExtensions.AsEnumerable%2A>을 호출하면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리의 데이터 소스 역할을 하는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현한 개체가 반환됩니다.  
  
 쿼리에는 데이터 소스에서 검색하려는 정보를 정확히 지정해야 합니다.  또한 정보를 반환하기 전에 정보에 대한 정렬, 그룹화 및 구체화하는 방법을 쿼리에 지정할 수 있습니다.  [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]에서 쿼리는 변수에 저장됩니다.  값 시퀀스를 반환하도록 설계된 쿼리인 경우에는 쿼리 변수 자체가 열거 가능한 형식이어야 합니다.  이 쿼리 변수는 어떠한 작업을 수행하거나 데이터를 반환하지 않고 쿼리 정보를 저장하기만 합니다.  쿼리를 만든 후에는 해당 쿼리를 실행하여 데이터를 검색해야 합니다.  
  
 값 시퀀스를 반환하는 쿼리의 경우 쿼리 변수 자체에는 쿼리 결과가 저장되지 않고 쿼리 명령만 저장됩니다.  쿼리 실행은 `foreach` 또는 `For Each` 루프에서 쿼리 변수가 반복될 때까지 지연됩니다.  쿼리가 구성된 다음 쿼리가 실행되므로 *지연된 실행*이라고 합니다.  즉, 원하는 때에 언제라도 쿼리를 실행할 수 있습니다.  예를 들어, 이 기능은 다른 응용 프로그램에서 업데이트되는 데이터베이스가 있을 때 유용합니다.  사용자의 응용 프로그램에서 최신 정보를 검색하는 쿼리를 만든 다음 쿼리를 반복적으로 실행하여 업데이트된 정보를 항상 반환할 수 있습니다.  
  
 값 시퀀스를 반환하는 지연된 쿼리와는 달리 singleton 값을 반환하는 쿼리는 즉시 실행됩니다.  singleton 쿼리의 예로는 <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> 및 <xref:System.Linq.Enumerable.First%2A>가 있습니다.  singleton 결과를 계산하려면 쿼리 결과가 필요하므로 이러한 쿼리는 즉시 실행됩니다.  예를 들어, 쿼리 결과의 평균을 구하려면 평균 함수에 사용할 입력 데이터를 얻기 위해 쿼리를 실행해야 합니다.  또한 쿼리에서 <xref:System.Linq.Enumerable.ToList%2A> 또는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드를 사용하여 singleton 값을 생성하지 않는 쿼리를 즉시 실행할 수도 있습니다.  쿼리 결과를 캐시하려는 경우 즉시 실행을 적용하는 이러한 기술을 유용하게 사용할 수 있습니다.  지연된 쿼리 및 즉시 쿼리 실행에 대한 자세한 내용은 [Getting Started with LINQ](http://msdn.microsoft.com/ko-kr/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)을 참조하세요.  
  
## 쿼리  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리는 쿼리 식 구문과 메서드 기반 쿼리 구문이라는 두 가지 구문 형식으로 만들 수 있습니다.  
  
### 쿼리 식 구문  
 쿼리 식은 선언적 쿼리 구문입니다.  이 구문을 사용하면 C\# 또는 Visual Basic에서 SQL에서와 비슷한 형식으로 쿼리를 작성할 수 있습니다.  쿼리 식 구문을 사용하면 최소한의 코드로 데이터 소스에 대해 복잡한 필터링, 정렬 및 그룹화 작업을 수행할 수 있습니다.  자세한 내용은 [LINQ 쿼리 식](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md) 및 [기본 쿼리 작업\(Visual Basic\)](../Topic/Basic%20Query%20Operations%20\(Visual%20Basic\).md)를 참조하세요.  
  
 쿼리 식 구문은 C\# 3.0과 [!INCLUDE[vb_orcas_long](../../../../includes/vb-orcas-long-md.md)]의 새로운 기능입니다.  그러나 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] CLR\(공용 언어 런타임\)에서는 쿼리 식 구문을 자체적으로 인식하지 못합니다.  따라서 컴파일 타임에 쿼리 식은 CLR에서 인식할 수 있는 메서드 호출로 변환됩니다.  이러한 메서드를 *표준 쿼리 연산자*라고 합니다.  개발자는 쿼리 구문을 사용하는 대신 메서드 구문을 사용하여 표준 쿼리 연산자를 직접 호출할 수도 있습니다.  자세한 내용은 [Query Syntax and Method Syntax in LINQ](../Topic/Query%20Syntax%20and%20Method%20Syntax%20in%20LINQ%20\(C%23\).md)을 참조하세요.  표준 쿼리 연산자를 사용하는 방법에 대한 자세한 내용은 [NOT IN BUILD: LINQ General Programming Guide](http://msdn.microsoft.com/ko-kr/609c7a6b-cbdd-429d-99f3-78d13d3bc049)를 참조하세요.  
  
 다음 예제에서는 <xref:System.Linq.Enumerable.Select%2A>를 사용하여 `Product` 테이블의 모든 행을 반환하고 제품 이름을 표시합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### 메서드 기반 쿼리 구문  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 작성하는 데 메서드 기반 쿼리를 사용할 수도 있습니다.  메서드 기반 쿼리 구문은 람다 식을 매개 변수로 전달하는 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 연산자 메서드에 대한 직접 메서드 호출의 시퀀스입니다.  자세한 내용은 [람다 식](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
 이 예제에서는 <xref:System.Linq.Enumerable.Select%2A>를 사용하여 `Product` 테이블의 모든 행을 반환하고 제품 이름을 표시합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## 쿼리 작성  
 위에서 설명한 것처럼 값 시퀀스를 반환하도록 쿼리가 디자인되었을 경우 쿼리 변수 자체에는 쿼리 명령만 저장됩니다.  쿼리에 즉시 실행을 발생시키는 메서드가 없으면 `foreach` 또는 `For Each` 루프에서 쿼리 변수를 반복할 때까지 쿼리의 실제 실행이 지연됩니다.  지연된 실행은 여러 쿼리를 결합하거나 하나의 쿼리를 확장 가능하게 합니다.  확장된 쿼리는 새 작업을 포함할 수 있도록 수정되며, 실행 결과에 변경 사항이 반영됩니다.  다음 예제의 첫 번째 쿼리에서는 모든 제품을 반환합니다.  두 번째 쿼리에서는 `Where`를 사용하여 첫 번째 쿼리를 확장하고 크기가 "L"인 모든 제품을 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 쿼리를 실행한 후에는 추가 쿼리를 작성할 수 없으므로 이후의 모든 쿼리에서는 메모리 내 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 연산자를 사용합니다.  `foreach` 또는 `For Each` 문에서 쿼리 변수를 반복하거나 즉시 실행을 발생시키는 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 변환 연산자 중 하나를 호출할 때 쿼리가 실행됩니다.  이러한 연산자에는 <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> 및 <xref:System.Linq.Enumerable.ToDictionary%2A>가 있습니다.  
  
 다음 예제의 첫 번째 쿼리에서는 가격을 기준으로 정렬된 모든 제품을 반환합니다.  즉시 쿼리 실행을 적용하기 위해 <xref:System.Linq.Enumerable.ToArray%2A> 메서드가 사용됩니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## 참고 항목  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)   
 [DataSet 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Getting Started with LINQ in C\#](../Topic/Getting%20Started%20with%20LINQ%20in%20C%23.md)   
 [Getting Started with LINQ in Visual Basic](../Topic/Getting%20Started%20with%20LINQ%20in%20Visual%20Basic.md)