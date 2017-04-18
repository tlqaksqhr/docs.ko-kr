---
title: "DataRows 및 DataRowViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataRows 및 DataRowViews
<xref:System.Data.DataView>는 <xref:System.Data.DataRowView> 개체의 열거할 수 있는 컬렉션을 노출시킵니다.  **DataRowView** 개체는 원본으로 사용하는 테이블의 열 이름 또는 서수 참조에 따라 인덱싱된 개체 배열로 값을 노출시킵니다.  **DataRowView**의 <xref:System.Data.DataRowView.Row%2A> 속성을 사용하여 **DataRowView**에 의해 노출된 <xref:System.Data.DataRow>에 액세스할 수 있습니다.  
  
 **DataRowView**를 사용하여 값을 보는 경우, **DataView**의 <xref:System.Data.DataView.RowStateFilter%2A> 속성은 원본 **DataRow**가 노출되는 행 버전을 결정합니다.  **DataRow**를 사용하여 서로 다른 행 버전에 액세스하는 방법에 대한 자세한 내용은 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)을 참조하세요.  
  
 다음 코드 예제에서는 테이블의 현재 값과 원래 값을 모두 표시합니다.  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## 참고 항목  
 <xref:System.Data.DataRowVersion>   
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)