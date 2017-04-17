---
title: "AcceptChanges 및 RejectChanges | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# AcceptChanges 및 RejectChanges
<xref:System.Data.DataTable>의 데이터에서 변경된 내용이 정확한지 확인한 후 <xref:System.Data.DataRow>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드를 사용하여 변경 내용을 승인할 수 있습니다. 그러면 **Current** 행 값이 **Original** 값으로 설정되고 **RowState** 속성이 **Unchanged**로 설정됩니다.  변경 내용을 승인하거나 거부하면 모든 **RowError** 정보가 지워지고 **HasErrors** 속성이 **false**로 설정됩니다.  또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다.  자세한 내용은 [DataAdapters를 사용하여 데이터 소스 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)을 참조하세요.  
  
 **DataTable**에 외래 키 제약 조건이 있는 경우 **AcceptChanges** 및 **RejectChanges**를 사용하여 승인되거나 거부된 변경 내용이 **ForeignKeyConstraint.AcceptRejectRule**에 따라 **DataRow**의 자식 행으로 전파됩니다.  자세한 내용은 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)을 참조하세요.  
  
 다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다.  오류가 해결된 경우 **RowError** 값이 빈 문자열로 설정되므로 **HasErrors** 속성은 **false**로 설정됩니다.  오류가 발생한 모든 행이 해결되거나 거부되면 **AcceptChanges**가 호출되어 전체 **DataTable**의 모든 변경 사항이 승인됩니다.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## 참고 항목  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)