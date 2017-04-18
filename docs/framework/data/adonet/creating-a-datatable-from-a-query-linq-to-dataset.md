---
title: "쿼리에서 DataTable 만들기(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 쿼리에서 DataTable 만들기(LINQ to DataSet)
데이터 바인딩에는 일반적으로 <xref:System.Data.DataTable> 개체가 사용됩니다.  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 쿼리 결과를 받아서 나중에 데이터 바인딩에 사용할 수 있도록 데이터를 <xref:System.Data.DataTable>에 복사합니다.  데이터 작업이 수행되면 새 <xref:System.Data.DataTable>이 소스 <xref:System.Data.DataTable>에 다시 병합됩니다.  
  
 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 다음 프로세스를 사용하여 쿼리에서 <xref:System.Data.DataTable>을 만듭니다.  
  
1.  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 소스 테이블\(<xref:System.Linq.IQueryable%601> 인터페이스를 구현한 <xref:System.Data.DataTable> 개체\)에서 <xref:System.Data.DataTable>을 복제합니다.  <xref:System.Collections.IEnumerable> 소스는 일반적으로 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 식 또는 메서드 쿼리를 통해 만들어집니다.  
  
2.  복제된 <xref:System.Data.DataTable>의 스키마는 소스 테이블의 첫 번째 열거된 <xref:System.Data.DataRow> 개체 열을 통해 작성되며 복제된 테이블의 이름은 소스 테이블 이름에 "query"라는 단어를 추가하여 지정됩니다.  
  
3.  소스 테이블에서 각 행의 내용은 새 <xref:System.Data.DataRow> 개체에 복사된 다음 복제 테이블에 삽입됩니다.  <xref:System.Data.DataRow.RowState%2A> 및 <xref:System.Data.DataRow.RowError%2A> 속성은 복사 작업 동안 유지됩니다.  소스의 <xref:System.Data.DataRow> 개체가 다른 테이블의 개체이면 <xref:System.ArgumentException>이 throw됩니다.  
  
4.  쿼리 가능한 입력 테이블의 모든 <xref:System.Data.DataRow> 개체가 복사된 후 복제된 <xref:System.Data.DataTable>이 반환됩니다.  소스 시퀀스에 <xref:System.Data.DataRow> 개체가 없는 경우 이 메서드는 빈 <xref:System.Data.DataTable>을 반환합니다.  
  
 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드를 호출하면 실행할 소스 테이블에 쿼리가 바인딩됩니다.  
  
 소스 테이블의 행에 null 참조 또는 nullable 값 형식이 있으면 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드가 해당 값을 <xref:System.DBNull.Value>로 바꿉니다.  이 방법을 통해 반환된 <xref:System.Data.DataTable>에서 null 값이 올바르게 처리됩니다.  
  
 참고: <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 여러 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 개체에서 행을 반환할 수 있는 쿼리를 입력으로 허용합니다.  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 소스 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 개체의 데이터만 반환되는 <xref:System.Data.DataTable>에 복사하며 속성은 복사하지 않습니다.  <xref:System.Data.DataTable.Locale%2A> 및 <xref:System.Data.DataTable.TableName%2A>과 같은 반환되는 <xref:System.Data.DataTable>에 대한 속성은 명시적으로 설정해야 합니다.  
  
 다음 예제에서는 SalesOrderHeader 테이블에 2001년 8월 8일 이후 주문을 쿼리한 다음 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드를 사용하여 해당 쿼리에서 <xref:System.Data.DataTable>을 만듭니다.  그런 다음 <xref:System.Data.DataTable>이 <xref:System.Windows.Forms.DataGridView>의 프록시 역할을 수행하는 <xref:System.Windows.Forms.BindingSource>에 바인딩됩니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## 사용자 지정 CopyToDataTable\<T\> 메서드 만들기  
 기존 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 제네릭 매개 변수 `T`가 <xref:System.Data.DataRow> 형식인 <xref:System.Collections.Generic.IEnumerable%601> 소스에서만 작동합니다.  이 제한은 유용하지만 이로 인해 일련의 스칼라 형식, 익명 형식을 반환하는 쿼리 또는 테이블 조인을 수행하는 쿼리에서 테이블을 만들지 못하게 됩니다.  일련의 스칼라 형식 또는 익명 형식에서 테이블을 로드하는 두 가지 사용자 지정 `CopyToDataTable` 메서드를 구현하는 방법에 대한 예제를 보려면 [방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable\<T\> 구현](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)을 참조하세요.  
  
 이 단원의 예제에서는 다음과 같은 사용자 지정 형식을 사용합니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### 예제  
 이 예제에서는 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 조인을 수행하여 8월의 온라인 주문을 가져오고 해당 쿼리에서 테이블을 만듭니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### 예제  
 다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 쿼리 결과로부터 테이블을 만듭니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### 예제  
 다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 결과를 프로젝션합니다.  반환된 일련의 익명 형식은 기존 테이블에 로드됩니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### 예제  
 다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 결과를 프로젝션합니다.  반환된 일련의 익명 형식은 기존 테이블에 로드됩니다.  `Book` 및 `Movies` 형식은 `Item` 형식에서 파생되므로 테이블 스키마는 자동으로 확장됩니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### 예제  
 다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 새 테이블에 로드되는 일련의 <xref:System.Double>을 반환합니다.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## 참고 항목  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)   
 [제네릭 필드 및 SetField 메서드](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)   
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)