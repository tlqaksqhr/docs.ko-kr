---
title: "DataTable에 데이터 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable에 데이터 추가
<xref:System.Data.DataTable>을 만들고 열 및 제약 조건을 사용하여 해당 테이블의 구조를 정의한 후에는 새 데이터 행을 테이블에 추가할 수 있습니다.  새 행을 추가하려면 새 변수의 형식을 <xref:System.Data.DataRow>로 선언합니다.  사용자가 <xref:System.Data.DataTable.NewRow%2A> 메서드를 호출하면 새 **DataRow** 개체가 반환됩니다.  그러면 **DataTable**은 <xref:System.Data.DataColumnCollection>에서 정의된 대로 테이블 구조에 따라 **DataRow** 개체를 만듭니다.  
  
 다음 예제에서는 **NewRow** 메서드를 호출하여 새 행을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 그러면 다음 예제와 같이 인덱스나 열 이름을 사용하여 새로 추가된 행을 조작할 수 있습니다.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 데이터가 새 행에 삽입되면 다음 코드와 같이 **Add** 메서드를 사용하여 이 행을 <xref:System.Data.DataRowCollection>에 추가합니다.  
  
```vb  
workTable.Rows.Add(workRow)  
  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 또한 다음 예제와 같이 **Add** 메서드를 호출하고 <xref:System.Object> 형식의 값 배열에 새 행을 전달하여 추가할 수 있습니다.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 **Object** 형식의 값 배열을 **Add** 메서드로 전달하면 테이블에 새 행이 만들어지고 해당 열 값이 개체 배열의 값으로 설정됩니다.  배열 값은 테이블에 나타나는 순서에 따라 해당 열과 순서대로 대응합니다.  
  
 다음 예제에서는 새로 만든 **Customers** 테이블에 10개의 행을 추가합니다.  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## 참고 항목  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)