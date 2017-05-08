---
title: "DataRelations 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataRelations 추가
여러 <xref:System.Data.DataTable> 개체가 포함된 <xref:System.Data.DataSet>에서는 <xref:System.Data.DataRelation> 개체를 사용하여 하나의 테이블을 다른 테이블에 연관시키거나, 테이블 사이를 탐색하거나, 연관된 테이블의 자식 또는 부모 행을 반환할 수 있습니다.  
  
 **DataRelation**을 만드는 데 필요한 인수로는 만들어지는 **DataRelation**의 이름과 관계에서 부모 및 자식 열로 작동하는 열을 참조하는 하나 이상의 <xref:System.Data.DataColumn>으로 이루어진 배열이 있습니다.  **DataRelation**을 만든 후에는 이를 사용하여 테이블 사이를 탐색하거나 값을 검색할 수 있습니다.  
  
 **DataRelation**을 <xref:System.Data.DataSet>에 추가하면 기본적으로 부모 테이블에는 <xref:System.Data.UniqueConstraint>가, 자식 테이블에는 <xref:System.Data.ForeignKeyConstraint>가 추가됩니다.  이러한 기본 제약 조건에 대한 자세한 내용은 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)를 참조하세요.  
  
 다음 코드 예제에서는 <xref:System.Data.DataSet>의 두 <xref:System.Data.DataTable> 개체를 사용하여 **DataRelation**을 만듭니다.  각 <xref:System.Data.DataTable>에는 두 <xref:System.Data.DataTable> 개체 사이의 링크로 작동하는 **CustID**라는 열이 있습니다.  이 예제에서는 **DataRelation** 하나가 <xref:System.Data.DataSet>의 **Relations** 컬렉션에 추가됩니다.  이 예제에서 첫 번째 인수는 만들어지는 **DataRelation**의 이름을 지정합니다.  두 번째 인수는 부모 **DataColumn**을 설정하고, 세 번째 인수는 자식 **DataColumn**을 설정합니다.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 **DataRelation**에는 **Nested** 속성도 있습니다. 이 속성을 **true**로 설정할 설정하면 자식 테이블의 행은 <xref:System.Data.DataSet.WriteXml%2A>을 사용하여 XML 요소로 작성할 경우 부모 테이블의 관련 행 내에 중첩됩니다.  자세한 내용은 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## 참고 항목  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)