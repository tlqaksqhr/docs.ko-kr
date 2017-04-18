---
title: "컴파일된 쿼리(LINQ to Entities) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 8025ba1d-29c7-4407-841b-d5a3bed40b7a
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# 컴파일된 쿼리(LINQ to Entities)
구조적으로 비슷한 쿼리를 Entity Framework에서 여러 차례 실행하는 응용 프로그램이 있는 경우, 쿼리를 한 번 컴파일한 후 매개 변수를 다르게 하여 여러 차례 실행하는 방법을 통해 성능을 높일 수 있는 경우가 많습니다.  예를 들어, 응용 프로그램에서 특정 도시의 모든 고객을 검색해야 하며 사용자가 런타임에 양식에서 도시를 지정하는 경우를 생각해 봅니다.  LINQ to Entities에서는 컴파일된 쿼리를 이 용도로 사용할 수 있도록 지원합니다.  
  
 .NET Framework 4.5부터 시작하여 LINQ 쿼리가 자동으로 캐시됩니다.  그러나, 여전히 컴파일된 LINQ 쿼리를 사용하여 나중에 실행할 때 이러한 비용을 줄일 수 있으며 컴파일된 쿼리는 자동으로 캐시되는 LINQ 쿼리에서보다 효율적으로 작동합니다.  메모리 내 컬렉션에 `Enumerable.Contains` 연산자를 적용하는 LINQ to Entities 쿼리는 자동으로 캐시되지 않습니다.  또한 메모리 내 컬렉션은 컴파일된 LINQ 쿼리에서 매개 변수화할 수 없습니다.  
  
 <xref:System.Data.Objects.CompiledQuery> 클래스는 쿼리를 재사용할 수 있도록 컴파일하고 캐시합니다.  개념상 이 클래스에는 다수의 오버로드가 있는 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드가 포함됩니다.  이 `Compile` 메서드를 호출하여 컴파일된 쿼리를 나타내는 새 대리자를 만듭니다.  <xref:System.Data.Objects.ObjectContext> 및 매개 변수 값과 함께 제공된 `Compile` 메서드는 <xref:System.Linq.IQueryable%601> 인스턴스와 같이 결과를 생성하는 대리자를 반환합니다.  쿼리는 첫 번째 실행 중에만 한 번 컴파일됩니다.  컴파일 시에 쿼리에 대해 설정된 병합 옵션은 나중에 변경할 수 없습니다.  쿼리가 컴파일되면 기본 형식의 매개 변수만 제공할 수 있지만 생성된 SQL을 변경할 쿼리의 부분을 대체할 수 없습니다.  자세한 내용은 [Entity Framework 병합 옵션 및 컴파일된 쿼리](http://go.microsoft.com/fwlink/?LinkId=199591)\(영문\)를 참조하세요.  
  
 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드가 컴파일하는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리 식은 <xref:System.Func%605>와 같은 제네릭 `Func` 대리자 중 하나로 나타냅니다.  쿼리 식은 최대로 `ObjectContext` 매개 변수 1개, 반환 매개 변수 1개 및 쿼리 매개 변수 16개를 캡슐화할 수 있습니다.  쿼리 매개 변수가 17개 이상 필요한 경우 속성으로 쿼리 매개 변수를 나타내는 구조를 만들 수 있습니다.  속성을 설정한 후 쿼리 식에서 구조의 속성을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Decimal> 입력 매개 변수를 사용하고 총 금액이 200달러 이상인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery2)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery2)]  
  
## 예제  
 다음 예제에서는 <xref:System.Data.Objects.ObjectQuery%601> 인스턴스를 반환하는 쿼리를 컴파일한 후 호출합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery1_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery1_mq)]  
  
## 예제  
 다음 예제에서는 제품 가격의 평균을 <xref:System.Decimal> 값 형태로 반환하는 쿼리를 컴파일한 다음 호출합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery3_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery3_mq)]  
  
## 예제  
 다음 예제에서는 <xref:System.String> 입력 매개 변수를 사용하고 전자 메일 주소가 지정 문자열로 시작되는 `Contact`를 반환하는 쿼리를 컴파일한 다음 호출합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery4_mq)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery4_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery4_mq)]  
  
## 예제  
 다음 예제에서는 <xref:System.DateTime> 및 <xref:System.Decimal> 입력 매개 변수를 사용하고 주문 날짜가 2003년 3월 8일 이후이고 합계 $300 미만인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery5)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery5)]  
  
## 예제  
 다음 예제에서는 <xref:System.DateTime> 입력 매개 변수를 사용하고 주문 날짜가 2004년 3월 8일 이후인 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.  이 쿼리는 주문 정보를 일련의 익명 형식으로 반환합니다.  익명 형식은 컴파일러에서 유추됩니다. 따라서 <xref:System.Data.Objects.CompiledQuery>의 `Compile` 메서드에서 형식 매개 변수를 지정할 수 없으며, 형식은 쿼리 자체에서 정의됩니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery6)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery6)]  
  
## 예제  
 다음 예제에서는 사용자 정의 구조 입력 매개 변수를 사용하고 일련의 주문을 반환하는 쿼리를 컴파일한 다음 호출합니다.  이 구조는 시작 날짜, 종료 날짜 및 수수료 합계 쿼리 매개 변수를 정의하고, 2003년 3월 3일에서 3월 8일 사이에 배송되었으며 수수료 합계가 $700.00보다 큰 주문을 반환합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#compiledquery7)]
 [!code-vb[DP L2E Conceptual Examples#CompiledQuery7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#compiledquery7)]  
  
 쿼리 매개 변수를 정의하는 구조는 다음과 같습니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myparamsstruct)]
 [!code-vb[DP L2E Conceptual Examples#MyParamsStruct](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myparamsstruct)]  
  
## 참고 항목  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)   
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)   
 [Entity Framework 병합 옵션 및 컴파일된 쿼리 \(영문\)](http://go.microsoft.com/fwlink/?LinkId=199591)