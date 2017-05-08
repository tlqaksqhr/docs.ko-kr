---
title: "DataView 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataView 만들기
<xref:System.Data.DataView>를 만드는 방법은 두 가지입니다.  하나는 **DataView** 생성자를 사용하는 방법이고 다른 하나는 <xref:System.Data.DataTable>의 <xref:System.Data.DataTable.DefaultView%2A> 속성에 대한 참조를 만드는 방법입니다.  **DataView** 생성자는 비어 있을 수 있고, **DataTable**을 단일 인수로 사용하거나 **DataTable**을 필터 조건, 정렬 조건 및 행 상태 필터와 함께 사용할 수도 있습니다.  **DataView**에 사용할 수 있는 추가 인수에 대한 자세한 내용은 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)을 참조하세요.  
  
 **DataView**의 인덱스는 **DataView**를 만들 때는 물론 **Sort**, **RowFilter** 또는 **RowStateFilter** 속성을 수정할 때도 빌드되기 때문에 **DataView**를 만들 때 초기 정렬 순서나 필터링 조건을 생성자 인수로 지정하면 최적의 성능을 얻을 수 있습니다.  정렬 조건이나 필터 조건을 지정하지 않고 **DataView**를 만든 다음 **Sort**, **RowFilter** 또는 **RowStateFilter** 속성을 나중에 설정하면 **DataView**를 만들 때와 정렬 또는 필터 속성을 수정할 때를 포함하여 인덱스가 최소한 두 번 이상 빌드됩니다.  
  
 인수를 사용하지 않는 생성자를 통해 **DataView**를 만드는 경우에는 **Table** 속성을 설정해야만 **DataView**를 사용할 수 있습니다.  
  
 다음 코드 예제에서는 **DataView** 생성자를 사용하여 **DataView**를 만드는 방법을 보여 줍니다.  **RowFilter**, **Sort** 열 및 **DataViewRowState**는 **DataTable**과 함께 제공됩니다.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 다음 코드 예제에서는 테이블의 **DefaultView** 속성을 사용하여 **DataTable**의 기본 **DataView**에 대한 참조를 가져오는 방법을 보여 줍니다.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## 참고 항목  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)