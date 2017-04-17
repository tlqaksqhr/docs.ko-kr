---
title: "DataRelations 탐색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataRelations 탐색
<xref:System.Data.DataRelation>의 기본 기능 중 하나는 <xref:System.Data.DataSet> 내에서 <xref:System.Data.DataTable>를 하나씩 탐색할 수 있도록 하는 것입니다.  따라서 연관된 **DataTable**의 **DataRow**가 하나 주어지면 하나의 **DataTable**에서 연관된 모든 <xref:System.Data.DataRow> 개체를 검색할 수 있습니다.  예를 들어, 고객 테이블과 주문 테이블 사이에 **DataRelation**을 설정한 다음 **GetChildRows**를 사용하여 특정 고객 행에 대한 모든 주문 행을 검색할 수 있습니다.  
  
 다음 코드 예제에서는 **DataSet**의 **Customers** 테이블과 **Orders** 테이블 사이에 **DataRelation**을 만들고 각 고객의 모든 주문을 반환합니다.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 다음 예제에서는 이전 예제를 기반으로 네 개의 테이블을 모두 연관시키고 각각의 관계를 탐색합니다.  이전 예제에서와 마찬가지로, **CustomerID**는 **Customers** 테이블을 **Orders** 테이블에 연관시킵니다.  **Customers** 테이블의 각 고객에 대해 **Orders** 테이블의 모든 자식 행이 결정되어 특정 고객의 주문 개수와 해당 **OrderID** 값이 반환됩니다.  
  
 확장된 예제에서는 **OrderDetails** 및 **Products** 테이블의 값도 반환됩니다.  **Orders** 테이블은 각각의 고객 주문에서 주문된 제품과 수량을 확인하기 위해 **OrderID**를 사용하여 **OrderDetails** 테이블에 연관됩니다.  **OrderDetails** 테이블에는 주문된 제품의 **ProductID**만 들어 있으므로 **OrderDetails**는 **ProductName**을 반환하기 위해 **ProductID**를 사용하여 **Products**에 연관됩니다.  이 관계에서 **Products** 테이블은 부모 테이블이고 **Order Details** 테이블은 자식 테이블입니다.  그 결과, **OrderDetails** 테이블을 반복하여 검색하면 **GetParentRow**가 호출되어 연관된 **ProductName** 값이 검색됩니다.  
  
 **Customers** 및 **Orders** 테이블에 대해 **DataRelation**을 만들면 **createConstraints** 플래그\(기본값은 **true**\)의 값이 지정되지 않습니다.  이 경우에는 **Orders** 테이블의 모든 행이 **Customers** 부모 테이블에 존재하는 **CustomerID** 값을 가지고 있다고 가정합니다.  **Customers** 테이블에 없는 **CustomerID**가 **Orders** 테이블에 있으면 <xref:System.Data.ForeignKeyConstraint>에서 예외가 throw됩니다.  
  
 부모 열에 포함되어 있지 않은 값이 자식 열에 있는 경우 **DataRelation**을 추가할 때 **createConstraints** 플래그를 **false**로 설정합니다.  이 예제에서 **createConstraints** 플래그는 **Orders** 테이블과 **OrderDetails** 테이블 간의 **DataRelation**에 대해 **false**로 설정됩니다.  그러면 응용 프로그램에서는 런타임 예외를 발생시키지 않고 **OrderDetails** 테이블의 모든 레코드와 **Orders** 테이블 레코드의 하위 집합만 반환할 수 있습니다.  확장된 예제는 다음과 같은 형식의 출력을 생성합니다.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 다음 코드 예제는 확장된 샘플로서 반환되는 **Orders** 테이블 레코드의 하위 집합만 포함하며, **OrderDetails** 및 **Products** 테이블의 값을 반환합니다.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## 참고 항목  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)