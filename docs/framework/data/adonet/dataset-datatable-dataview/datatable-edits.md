---
title: "DataTable 편집"
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d33bd8900c48222142a46ed2c5bd64412d2eaab5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-edits"></a>DataTable 편집
<xref:System.Data.DataRow>에서 열 값을 변경하는 경우, 변경된 값은 현재 상태의 행에 바로 저장됩니다. <xref:System.Data.DataRowState> 으로 설정 됩니다 **Modified**, 변경 내용을 적용는 또는 사용 하 여 취소 하 고는 <xref:System.Data.DataRow.AcceptChanges%2A> 또는 <xref:System.Data.DataRow.RejectChanges%2A> 의 메서드는 **DataRow**합니다. **DataRow** 편집 하는 동안 행의 상태를 일시 중단 하는 데 사용할 수 있는 세 가지 방법을 제공 합니다. 이러한 메서드에는 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 및 <xref:System.Data.DataRow.CancelEdit%2A>이 있습니다.  
  
 열 값을 수정 하는 경우는 **DataRow** 를 직접는 **DataRow** 사용 하 여 열 값을 관리 하는 **현재**, **기본**, 및 **원래** 행 버전입니다. 이러한 행 버전 이외에 **BeginEdit**, **EndEdit**, 및 **CancelEdit** 메서드 네 번째 행 버전을 사용: **Proposed**합니다. 행 버전에 대 한 자세한 내용은 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.  
  
 **Proposed** 편집 작업으로 호출 하 여 시작 하는 동안 행 버전이 존재 **BeginEdit** 를 사용 하 여 끝나는 **EndEdit** 또는 **CancelEdit**  또는 호출 하 여 **AcceptChanges** 또는 **RejectChanges**합니다.  
  
 편집 작업을 하는 동안 있습니다 유효성 검사 논리를 적용할 수 개별 열을 평가 하 여는 **ProposedValue** 에 **ColumnChanged** 의 이벤트는 **DataTable**합니다. **ColumnChanged** 이벤트에는 **DataColumnChangeEventArgs** 변경 되 고 있는 열에 및에 대 한 참조를 유지 하는 **ProposedValue**합니다. 사용자는 제안된 값을 검사한 후 이 값을 수정하거나 편집을 취소할 수 있습니다. 편집이 종료 되는 행의 이동은 **Proposed** 상태입니다.  
  
 호출 하 여 편집을 확인 수 **EndEdit**, 하거나 호출 하 여 취소할 수 있습니다 **CancelEdit**합니다. 하지만 **EndEdit** 편집을 확인 하는 **데이터 집합** 실제로 변경 될 때까지 받아들이지 않는 **AcceptChanges** 호출 됩니다. 이때 또한 호출 하는 경우 **AcceptChanges** 사용 하 여 편집을 종료 하기 전에 **EndEdit** 또는 **CancelEdit**, 편집이 종료 및 **제안됨** 행 값이 둘 다에 대해 허용 되는 **현재** 및 **원래** 행 버전입니다. 동일한 방식으로 호출 **RejectChanges** 편집을 종료 하 고 삭제는 **현재** 및 **Proposed** 행 버전입니다. 호출 **EndEdit** 또는 **CancelEdit** 호출한 후 **AcceptChanges** 또는 **RejectChanges** 편집에 이미 있기 때문에 아무 효과가 종료 되었습니다.  
  
 다음 예제에서는 사용 하는 방법을 **BeginEdit** 와 **EndEdit** 및 **CancelEdit**합니다. 이 예제는 또한 확인는 **ProposedValue** 에 **ColumnChanged** 이벤트 편집을 취소 여부를 결정 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [DataTable 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
