---
title: 데이터 정렬 및 필터링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 02a67a490eb8339663aac08c97c665ffee09f0df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="sorting-and-filtering-data"></a>데이터 정렬 및 필터링
<xref:System.Data.DataView>를 사용하면 다음과 같은 여러 가지 방법으로 <xref:System.Data.DataTable>의 데이터를 정렬 및 필터링할 수 있습니다.  
  
-   <xref:System.Data.DataView.Sort%2A> 속성을 사용하여 하나 또는 여러 열의 정렬 순서를 지정하고, ASC(오름차순) 및 DESC(내림차순) 매개 변수를 포함시킬 수 있습니다.  
  
-   <xref:System.Data.DataView.ApplyDefaultSort%2A> 속성을 사용하여 테이블의 기본 키 열을 기준으로 오름차순의 정렬 순서를 자동으로 만들 수 있습니다. <xref:System.Data.DataView.ApplyDefaultSort%2A> 경우에 적용 됩니다는 **정렬** 속성은 null 참조 또는 빈 문자열인 경우 테이블에 기본 키가 정의 하 고 있습니다.  
  
-   <xref:System.Data.DataView.RowFilter%2A> 속성을 사용하여 해당 열 값을 기준으로 행의 하위 집합을 지정할 수 있습니다. 사용할 수 있는 식에 대 한 자세한 내용은 **RowFilter** 속성에 대 한 참조 정보를 참조는 <xref:System.Data.DataColumn.Expression%2A> 속성은 <xref:System.Data.DataColumn> 클래스입니다.  
  
     에 데이터를 전송할 데이터의 하위 집합에 대 한 동적 뷰를 제공 하는 특정 쿼리 결과를 사용 하 여 반환 하려는 경우는 <xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A> 의 메서드는 **DataView** 최상의 성능을 얻으려면 보다는 설정의 **RowFilter** 속성입니다. 설정의 **RowFilter** 속성 데이터, 응용 프로그램에 오버 헤드가 및 성능이 저하에 대 한 인덱스를 다시 작성 합니다. **RowFilter** 속성은 가장 적합 한 데이터 바인딩된 응용 프로그램에 바인딩된 컨트롤에서 필터링 된 결과 표시 하는 위치입니다. **찾을** 및 **FindRows** 메서드를 다시 작성 해야 인덱스를 요구 하지 않고 현재 인덱스를 활용 합니다. 에 대 한 자세한 내용은 **찾을** 및 **FindRows** 메서드 참조 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)합니다.  
  
-   <xref:System.Data.DataView.RowStateFilter%2A> 속성을 사용하면 표시할 행 버전을 지정할 수 있습니다. **DataView** 암시적으로에 따라 노출 시킬 행 버전 관리는 **RowState** 기본 행의 합니다. 예를 들어 경우는 **RowStateFilter** 로 설정 된 **DataViewRowState.Deleted**, **DataView** 노출 된 **원래** 의 행 버전 모든 **Deleted** 있기 때문에 행 없음 **현재** 행 버전입니다. 사용 하 여 표시 된 행의 행 버전을 확인할 수 있습니다는 **RowVersion** 의 속성은 **DataRowView**합니다.  
  
     다음 표에서에 대 한 옵션을 보여 줍니다. **DataViewRowState**합니다.  
  
    |DataViewRowState 옵션|설명|  
    |------------------------------|-----------------|  
    |**CurrentRows**|**현재** 의 모든 행 버전 **Unchanged**, **Added**, 및 **Modified** 행. 이 값이 기본값입니다.|  
    |**추가**|**현재** 의 모든 행 버전 **Added** 행.|  
    |**삭제**|**원래** 의 모든 행 버전 **Deleted** 행.|  
    |**ModifiedCurrent**|**현재** 의 모든 행 버전 **Modified** 행.|  
    |**ModifiedOriginal**|**원래** 의 모든 행 버전 **Modified** 행.|  
    |**없음**|행이 없습니다.|  
    |**OriginalRows**|**원래** 의 모든 행 버전 **Unchanged**, **Modified**, 및 **Deleted** 행.|  
    |**Unchanged**|**현재** 의 모든 행 버전 **Unchanged** 행.|  
  
 행 상태 및 행 버전에 대 한 자세한 내용은 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
