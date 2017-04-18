---
title: "DataViews 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataViews 수정
<xref:System.Data.DataView>를 사용하여 원본 테이블의 데이터 행을 추가, 삭제 또는 수정할 수 있습니다.  **DataView**를 사용하여 원본 테이블의 데이터를 수정하는 기능은 **DataView**의 세 가지 부울 속성 중 하나를 설정하여 제어할 수 있습니다.  이러한 속성에는 <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> 및 <xref:System.Data.DataView.AllowDelete%2A>가 있습니다.  이들 속성은 기본적으로 **true**로 설정되어 있습니다.  
  
 **AllowNew**가 **true**인 경우 **DataView**의 <xref:System.Data.DataView.AddNew%2A> 메서드를 사용하여 새 <xref:System.Data.DataRowView>를 만들 수 있습니다.  **DataRowView**의 <xref:System.Data.DataRowView.EndEdit%2A> 메서드를 호출할 때까지는 원본 <xref:System.Data.DataTable>에 새 행이 실제로 추가되지 않습니다.  **DataRowView**의 <xref:System.Data.DataRowView.CancelEdit%2A> 메서드를 호출하면 새 행이 삭제됩니다.  또한 한 번에 하나의 **DataRowView**만 편집할 수 있습니다.  보류된 행이 있는데도 **DataRowView**의 **AddNew** 또는 **BeginEdit** 메서드를 호출하면 보류된 행에 대해 **EndEdit**이 암시적으로 호출됩니다.  **EndEdit**을 호출하면 변경 내용이 원본 **DataTable**에 적용되며, 나중에 **DataTable**, **DataSet** 또는 **DataRow** 개체의 **AcceptChanges** 또는 **RejectChanges** 메서드를 사용하여 커밋하거나 거부할 수 있습니다.  **AllowNew**가 **false**인 경우 **DataRowView**의 **AddNew** 메서드를 호출하면 예외가 throw됩니다.  
  
 **AllowEdit**이 **true**인 경우 **DataRowView**를 통해 **DataRow**의 내용을 수정할 수 있습니다.  **DataRowView.EndEdit**을 사용하여 원본 행의 변경 내용을 확정하거나 **DataRowView.CancelEdit**을 사용하여 변경 내용을 거부할 수 있습니다.  행은 한 번에 하나씩만 편집할 수 있습니다.  보류된 행이 있는데도 **DataRowView**의 **AddNew** 또는 **BeginEdit** 메서드를 호출하면 보류된 행에 대해 **EndEdit**이 암시적으로 호출됩니다.  **EndEdit**을 호출하면 제안된 변경 내용은 원본 **DataRow**의 **Current** 행 버전에 놓이게 되며, 나중에 **DataTable**, **DataSet** 또는 **DataRow** 개체의 **AcceptChanges** 또는 **RejectChanges** 메서드를 사용하여 커밋하거나 거부할 수 있습니다.  **AllowEdit**이 **false**인 경우 **DataView**의 값을 수정하려고 하면 예외가 throw됩니다.  
  
 기존 **DataRowView**를 편집하려고 하면 제안된 변경 내용에서 원본 **DataTable**의 이벤트가 발생합니다.  원본 **DataRow**에 대해 **EndEdit** 또는 **CancelEdit**을 호출하면 **DataRowView**에 대해 **EndEdit** 또는 **CancelEdit**이 호출되었는지 여부와 상관없이 보류된 변경 내용이 적용되거나 취소됩니다.  
  
 **AllowDelete**가 **true**인 경우 **DataView** 또는 **DataRowView** 개체의 **Delete** 메서드를 사용하여 **DataView**에서 행을 삭제할 수 있으며, 해당 행은 원본 **DataTable**에서 삭제됩니다.  **AcceptChanges** 또는 **RejectChanges**를 각각 사용하여 삭제 내용을 나중에 커밋하거나 거부할 수 있습니다.  **AllowDelete**가 **false**인 경우 **DataView** 또는 **DataRowView**의 **Delete** 메서드를 호출하면 예외가 throw됩니다.  
  
 다음 코드 예제에서는 **DataView**를 사용하여 행을 삭제하는 기능을 비활성화하고, **DataView**를 사용하여 원본 테이블에 새 행을 추가합니다.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## 참고 항목  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)