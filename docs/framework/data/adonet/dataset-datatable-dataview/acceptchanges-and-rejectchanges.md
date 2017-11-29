---
title: "AcceptChanges 및 RejectChanges"
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
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ac64fee869ce58413e799f4217f009ef6ae91a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges 및 RejectChanges
데이터에 대 한 변경 내용의 정확성을 확인 한 후는 <xref:System.Data.DataTable>를 사용 하 여 변경 내용을 적용 수 있습니다는 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드는 <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataSet>, 하는 설정의 **현재** 행 값이 고 **원래** 값을 설정 합니다는 **RowState** 속성을 **Unchanged**합니다. 수락 하거나 변경 내용이 거부 된 모든 지웁니다 **RowError** 정보 및 설정의 **HasErrors** 속성을 **false**합니다. 또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다. 자세한 내용은 참조 [Dataadapter로 데이터 원본 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)합니다.  
  
 외래 키 제약 조건에 있는 경우에 **DataTable**, 변경 내용을 적용 하거나 사용 하 여 취소 **AcceptChanges** 및 **RejectChanges** 는 의자식행으로전파 **DataRow** 에 따라는 **ForeignKeyConstraint.AcceptRejectRule**합니다. 자세한 내용은 참조 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다. 해결 된 오류를 참고는 **RowError** 값이 빈 문자열로 다시 설정 일으키는 **HasErrors** 속성으로 설정 되어야 **false**합니다. 모든 행 오류와 함께 해결 되거나 거부 되 면 **AcceptChanges** 전체에 대 한 모든 변경 내용을 적용 하기 위해 호출 **DataTable**합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
