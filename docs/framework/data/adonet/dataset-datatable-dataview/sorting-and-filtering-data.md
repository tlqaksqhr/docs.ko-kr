---
title: "데이터 정렬 및 필터링 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 데이터 정렬 및 필터링
<xref:System.Data.DataView>를 사용하면 다음과 같은 여러 가지 방법으로 <xref:System.Data.DataTable>의 데이터를 정렬 및 필터링할 수 있습니다.  
  
-   <xref:System.Data.DataView.Sort%2A> 속성을 사용하여 하나 또는 여러 열의 정렬 순서를 지정하고, ASC\(오름차순\) 및 DESC\(내림차순\) 매개 변수를 포함시킬 수 있습니다.  
  
-   <xref:System.Data.DataView.ApplyDefaultSort%2A> 속성을 사용하여 테이블의 기본 키 열을 기준으로 오름차순의 정렬 순서를 자동으로 만들 수 있습니다.  <xref:System.Data.DataView.ApplyDefaultSort%2A>는 **Sort** 속성이 null 참조 또는 빈 문자열인 경우와 테이블에 기본 키가 정의되어 있는 경우에만 적용됩니다.  
  
-   <xref:System.Data.DataView.RowFilter%2A> 속성을 사용하여 해당 열 값을 기준으로 행의 하위 집합을 지정할 수 있습니다.  **RowFilter** 속성에서 사용할 수 있는 식에 대한 자세한 내용은 <xref:System.Data.DataColumn> 클래스의 <xref:System.Data.DataColumn.Expression%2A> 속성에 대한 정보를 참조하세요.  
  
     데이터의 하위 집합에 대한 동적 뷰를 제공하는 것과는 반대로 데이터에 대한 특정 쿼리 결과를 반환하려는 경우 **RowFilter** 속성을 설정하는 대신 **DataView**의 <xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A> 메서드를 사용할 수 있습니다.  **RowFilter** 속성을 설정하면 데이터의 인덱스가 다시 빌드되고, 응용 프로그램에 오버헤드가 발생하여 성능이 저하됩니다.  **RowFilter** 속성은 바인딩된 컨트롤에 필터링된 결과를 표시하는 데이터 바인딩된 응용 프로그램에 가장 적합합니다.  **Find** 및 **FindRows** 메서드는 인덱스를 다시 빌드하지 않고 현재 인덱스를 사용합니다.  **Find** 및 **FindRows** 메서드에 대한 자세한 내용은 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)을 참조하세요.  
  
-   <xref:System.Data.DataView.RowStateFilter%2A> 속성을 사용하면 표시할 행 버전을 지정할 수 있습니다.  **DataView**에서는 원본으로 사용하는 행의 **RowState**에 따라 노출시킬 행 버전을 암시적으로 관리합니다.  예를 들어, **RowStateFilter**가 **DataViewRowState.Deleted**로 설정되어 있으면 **Current** 행 버전이 없기 때문에 **DataView**에서 모든 **Deleted** 행의 **Original** 행 버전을 노출합니다.  **DataRowView**의 **RowVersion** 속성을 사용하여 노출시킬 행의 버전을 결정할 수 있습니다.  
  
     다음 표에서는 **DataViewRowState**에 대한 옵션을 보여 줍니다.  
  
    |DataViewRowState 옵션|설명|  
    |-------------------------|--------|  
    |**CurrentRows**|모든 **Unchanged**, **Added** 및 **Modified** 행의 **Current** 행 버전입니다.  이 값이 기본값입니다.|  
    |**Added**|모든 **Added** 행의 **Current** 행 버전입니다.|  
    |**삭제됨**|모든 **Deleted** 행의 **Original** 행 버전입니다.|  
    |**ModifiedCurrent**|모든 **Modified** 행의 **Current** 행 버전입니다.|  
    |**ModifiedOriginal**|모든 **Modified** 행의 **Original** 행 버전입니다.|  
    |**없음**|행이 없습니다.|  
    |**OriginalRows**|모든 **Unchanged**, **Modified** 및 **Deleted** 행의 **Original** 행 버전입니다.|  
    |**Unchanged**|모든 **Unchanged** 행의 **Current** 행 버전입니다.|  
  
 행 상태 및 행 버전에 대한 자세한 내용은 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)을 참조하세요.  
  
 다음 코드 예제에서는 재고 수량이 재주문 수준보다 적거나 같은 모든 제품을 표시하는 뷰를 만듭니다. 이 때 먼저 공급자 ID로 정렬한 다음 제품 이름으로 정렬하여 표시합니다.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## 참고 항목  
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)