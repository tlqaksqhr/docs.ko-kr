---
title: "DataRow 삭제 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# DataRow 삭제
<xref:System.Data.DataTable> 개체에서 <xref:System.Data.DataRow> 개체를 삭제하는 데 사용할 수 있는 메서드에는 <xref:System.Data.DataRowCollection> 개체의 **Remove** 메서드와 **DataRow** 개체의 <xref:System.Data.DataRow.Delete%2A> 메서드가 있습니다.  <xref:System.Data.DataRowCollection.Remove%2A> 메서드는 **DataRowCollection**에서 **DataRow**를 삭제하는 반면, <xref:System.Data.DataRow.Delete%2A> 메서드는 삭제할 행을 표시만 합니다.  응용 프로그램에서 **AcceptChanges** 메서드를 호출할 때 행이 실제로 삭제됩니다.  <xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다.  삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.  
  
 <xref:System.Data.DataRowCollection> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>가 호출되지 않아야 합니다.  <xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>는 컬렉션의 상태를 수정하지 않습니다.  
  
 <xref:System.Data.DataSet> 또는 **DataTable**을 **DataAdapter** 및 관계형 데이터 소스와 함께 사용할 경우 **DataRow**의 **Delete** 메서드를 사용하여 행을 제거합니다.  **Delete** 메서드는 **DataSet** 또는 **DataTable**에서 행을 **Deleted**로 표시만 하고 제거하지는 않습니다.  대신 **DataAdapter**가 **Deleted**로 표시된 행을 발견하면 **DeleteCommand** 메서드를 실행하여 데이터 소스에서 행을 삭제합니다.  그런 다음 **AcceptChanges** 메서드를 사용하여 행을 영구적으로 제거합니다.  **Remove**를 사용하여 행을 삭제할 경우 해당 행은 테이블에서 완전히 제거되지만 **DataAdapter**는 데이터 소스에서 행을 삭제하지 않습니다.  
  
 다음 예제와 같이 **DataRowCollection**의 **Remove** 메서드는 **DataRow**를 인수로 사용하여 컬렉션에서 제거합니다.  
  
```vb  
workTable.Rows.Remove(workRow)  
  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 반면에, 다음 예제에서는 **DataRow**에서 **Delete** 메서드를 호출하여 **RowState**를 **Deleted**로 변경하는 방법을 보여 줍니다.  
  
```vb  
workRow.Delete  
  
```  
  
```csharp  
workRow.Delete();  
```  
  
 행이 삭제 표시된 상태에서 **DataTable** 개체의 **AcceptChanges** 메서드를 호출하면 해당 행은 **DataTable**에서 삭제됩니다.  반대로, **RejectChanges**를 호출하면 **RowState**가 **Deleted**로 표시되기 전의 상태로 돌아갑니다.  
  
> [!NOTE]
>  **DataRow**의 **RowState**가 **Added**인 경우, 이 행이 테이블에 추가되고 **Deleted**로 표시되어 테이블에서 삭제되는 것을 의미합니다.  
  
## 참고 항목  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)