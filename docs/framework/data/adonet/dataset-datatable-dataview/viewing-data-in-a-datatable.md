---
title: "DataTable에서 데이터 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable에서 데이터 보기
**DataTable**의 **Rows** 및 **Columns** 컬렉션을 사용하여 <xref:System.Data.DataTable>의 내용에 액세스할 수 있습니다.  <xref:System.Data.DataTable.Select%2A> 메서드를 사용하여 검색 조건, 정렬 순서 및 행 상태 등의 기준에 따라 **DataTable**에 있는 데이터의 하위 집합을 반환할 수도 있습니다.  또한 기본 키 값으로 특정 행을 검색할 때 **DataRowCollection**의 <xref:System.Data.DataRowCollection.Find%2A> 메서드를 사용할 수 있습니다.  
  
 **DataTable** 개체의 **Select** 메서드는 지정된 조건과 일치하는 <xref:System.Data.DataRow> 개체를 반환합니다.  **Select**에는 필터 식, 정렬 식 및 **DataViewRowState**의 선택적 옵션 인수가 사용됩니다.  필터 식은 **DataColumn** 값에 따라 반환되는 행을 식별하며, 이 식은 `LastName = 'Smith'`와 같이 표현됩니다.  정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다.  식 작성 규칙에 대한 자세한 내용은 **DataColumn** 클래스의 <xref:System.Data.DataColumn.Expression%2A> 속성을 참조하세요.  
  
> [!TIP]
>  **DataTable**의 **Select** 메서드를 여러 번 호출하려는 경우, 먼저 **DataTable**에 대해 <xref:System.Data.DataView>를 만들면 성능을 향상시킬 수 있습니다.  **DataView**를 만들면 테이블 행의 인덱스가 작성됩니다.  그러면 **Select** 메서드는 해당 인덱스를 사용하여 쿼리 결과 생성 시간을 상당히 줄여 줍니다.  **DataTable**에 대해 **DataView**를 만드는 방법은 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)을 참조하세요.  
  
 **Select** 메서드는 <xref:System.Data.DataViewRowState>에 따라 보거나 조작하려는 행 버전을 선택합니다.  다음 표에서는 사용할 수 있는 **DataViewRowState** 열거형 값에 대해 설명합니다.  
  
|DataViewRowState 값|설명|  
|------------------------|--------|  
|**CurrentRows**|변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행|  
|**삭제됨**|삭제된 행|  
|**ModifiedCurrent**|원래 데이터가 수정된 현재 버전  \(**ModifiedOriginal** 참조\)|  
|**ModifiedOriginal**|수정된 모든 행의 원래 버전.  현재 버전은 **ModifiedCurrent**를 사용하여 알 수 있습니다.|  
|**Added**|새 행|  
|**없음**|없음|  
|**OriginalRows**|변경되지 않거나 삭제된 행을 포함하는 원래 행|  
|**Unchanged**|변경되지 않은 행|  
  
 다음 예제에서는 **DataSet** 개체가 필터링되므로, **DataViewRowState**가 **CurrentRows**로 설정된 행에서만 작업을 수행합니다.  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 **Select** 메서드를 사용하면 **RowState** 값이나 필드 값이 다른 행을 반환할 수 있습니다.  다음 예제에서는 이미 삭제된 모든 행을 참조하는 **DataRow** 배열을 반환하고, **CustID** 열이 5보다 큰 모든 행을 참조하는 또 다른 **DataRow** 배열을 반환합니다. 이 배열은 **CustLName**에 따라 정렬됩니다.  **Deleted** 행에서 정보를 보는 방법에 대한 자세한 내용은 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)을 참조하세요.  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## 참고 항목  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataViewRowState>   
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)