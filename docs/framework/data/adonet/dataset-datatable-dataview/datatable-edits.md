---
title: "DataTable 편집 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable 편집
<xref:System.Data.DataRow>에서 열 값을 변경하는 경우, 변경된 값은 현재 상태의 행에 바로 저장됩니다.  그런 다음 <xref:System.Data.DataRowState>가 **Modified**로 설정되며, **DataRow**의 <xref:System.Data.DataRow.AcceptChanges%2A> 또는 <xref:System.Data.DataRow.RejectChanges%2A> 메서드를 사용하여 변경된 내용을 승인하거나 거부합니다.  또한 **DataRow**에서는 편집하는 동안 행의 상태를 일시 중단하는 데 사용할 수 있는 세 개의 메서드를 제공합니다.  이러한 메서드에는 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 및 <xref:System.Data.DataRow.CancelEdit%2A>이 있습니다.  
  
 사용자가 **DataRow**에서 열 값을 직접 수정하는 경우, **DataRow**는 **Current**, **Default** 및 **Original** 행 버전을 사용하여 열 값을 관리합니다.  이러한 행 버전 이외에도 **BeginEdit**, **EndEdit** 및 **CancelEdit** 메서드에서는 네 번째 행 버전인 **Proposed**를 사용합니다.  행 버전에 대한 자세한 내용은 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)을 참조하세요.  
  
 **Proposed** 행 버전은 편집 동작을 수행하는 중에 나타납니다. 편집 동작은 **BeginEdit**을 호출하여 시작되고 **EndEdit** 또는 **CancelEdit**을 사용하거나 **AcceptChanges** 또는 **RejectChanges**를 호출하면 종료됩니다.  
  
 편집 동작을 수행하는 중에 사용자는 **DataTable**의 **ColumnChanged** 이벤트에서 **ProposedValue**를 검사하여 개별 열에 유효성 검사 논리를 적용할 수 있습니다.  **ColumnChanged** 이벤트에는 변경 중인 열 및 **ProposedValue**를 참조하는 **DataColumnChangeEventArgs**가 포함되어 있습니다.  사용자는 제안된 값을 검사한 후 이 값을 수정하거나 편집을 취소할 수 있습니다.  편집을 종료하면 행의 상태가 **Proposed**에서 변경됩니다.  
  
 사용자는 **EndEdit**을 호출하여 편집을 확인하거나 **CancelEdit**을 호출하여 편집을 취소할 수 있습니다.  **EndEdit**은 편집을 확인하지만 **DataSet**은 **AcceptChanges**가 호출된 후에야 변경 내용을 실제로 승인합니다.  또한 **EndEdit**이나 **CancelEdit**을 사용하여 편집을 종료하기 전에 **AcceptChanges**를 호출하면 편집이 종료되고 **Current** 및 **Original** 행 버전 모두에 대해 **Proposed** 행 값이 승인됩니다.  마찬가지로 **RejectChanges**를 호출하면 편집이 종료되고 **Current** 및 **Proposed** 행 버전이 삭제됩니다.  **AcceptChanges** 또는 **RejectChanges**를 호출한 후에 **EndEdit** 또는 **CancelEdit**을 호출하는 경우에는 편집이 이미 종료된 상태이므로 아무런 영향을 주지 않습니다.  
  
 다음 예제에서는 **EndEdit** 및 **CancelEdit**과 함께 **BeginEdit**을 사용하는 방법을 보여 줍니다.  이 예제에서는 또한 **ColumnChanged** 이벤트에서 **ProposedValue**를 검사하고 편집 취소 여부를 결정합니다.  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataRowVersion>   
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [DataTable 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)