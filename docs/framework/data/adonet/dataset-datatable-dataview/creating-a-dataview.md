---
title: "DataView 만들기"
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
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28a2f6f299d2f904dc3f842c0c778f30081240b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-dataview"></a>DataView 만들기
<xref:System.Data.DataView>를 만드는 방법은 두 가지입니다. 사용할 수 있습니다는 **DataView** 생성자를 만들 수 있습니다에 대 한 참조는 <xref:System.Data.DataTable.DefaultView%2A> 의 속성은 <xref:System.Data.DataTable>합니다. **DataView** 생성자는 비어 있을 수 있습니다 또는 하나를 사용할 수는 **DataTable** 단일 인수로 또는 **DataTable** 필터 조건, 정렬 조건 및 행과 함께 상태 필터입니다. 에 사용할 수 있는 추가 인수에 대 한 자세한 내용은 **DataView**, 참조 [정렬 및 필터링 데이터](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)합니다.  
  
 때문에 대 한 인덱스는 **DataView** 때 작성 됩니다는 **DataView** 만들어지면와 같은 경우에 **정렬**, **RowFilter**, 또는  **RowStateFilter** 속성이 수정, 초기 정렬 순서를 제공 하거나 만들 때 조건을 생성자 인수로 필터링 하 여 최상의 성능을 얻으려면는 **DataView**합니다. 만들기는 **DataView** 정렬 또는 필터 조건을 지정 하 고 다음을 설정 하지 않고는 **정렬**, **RowFilter**, 또는 **RowStateFilter** 속성에는 나중에 인덱스를 두 번 이상 구축할 수로 인해: 되 면 때는 **DataView** 만들어지면 및 다시 정렬 또는 필터 속성은 수정한 시간입니다.  
  
 만들 경우에 **DataView** 인수를 사용 하지 않는 생성자를 사용 하 여, 됩니다 사용할 수는 **DataView** 설정 하기 전에 **테이블** 속성 .  
  
 다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 **DataView** 를 사용 하는 **DataView** 생성자입니다. A **RowFilter**, **정렬** 열 및 **DataViewRowState** 와 함께 제공 되는 **DataTable**합니다.  
  
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
  
 다음 코드 예제를 기본에 대 한 참조를 가져오는 방법을 보여 줍니다 **DataView** 의 **DataTable** 를 사용 하는 **DefaultView** 테이블의 속성입니다.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
