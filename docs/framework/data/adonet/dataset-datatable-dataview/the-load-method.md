---
title: "Load 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Load 메서드
<xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다.  이 메서드는 매우 간단한 형식으로 **DataReader** 단일 매개 변수를 승인하는 오버로드된 메서드입니다.  이러한 형식으로는 **DataTable**을 행과 함께 로드하는 기능만 합니다.  필요에 따라 **LoadOption** 매개 변수를 지정하여 **DataTable**에 데이터를 추가하는 방식을 제어할 수도 있습니다.  
  
 **LoadOption** 매개 변수는 데이터 소스에서 들어오는 데이터를 테이블에 이미 들어 있는 데이터와 결합하는 방법을 설명하므로, **DataTable**에 데이터 행이 이미 들어 있는 경우에 특히 유용합니다.  예를 들어, **PreserveCurrentValues**\(기본값\)는 **DataTable**의 행이 **Added**로 표시되는 경우 **Original** 값이나 각 열이 데이터 소스의 일치하는 행 내용으로 설정되도록 지정합니다.  **Current** 값은 행이 추가되었을 때 할당된 값을 유지하며 행의 **RowState**는 **Changed**로 설정됩니다.  
  
 다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.  
  
|LoadOption 값|설명|  
|------------------|--------|  
|**OverwriteRow**|들어오는 행과 **DataTable**에 이미 들어 있는 행의 **PrimaryKey** 값이 같으면 각 열의 **Original** 및 **Current** 값이 들어오는 행의 값으로 대체되고 **RowState** 속성은 **Unchanged**로 설정됩니다.<br /><br /> **DataTable**에 없는 데이터 소스의 행이 추가되며, 해당 행의 **RowState** 값은 **Unchanged**로 설정됩니다.<br /><br /> 이 옵션을 적용하면 데이터 소스의 내용과 일치하도록 **DataTable**의 내용을 새로 고칩니다.|  
|**PreserveCurrentValues\(기본값\)**|들어오는 행과 **DataTable**에 이미 들어 있는 행의 **PrimaryKey** 값이 같으면 **Original** 값은 들어오는 행의 내용으로 설정되고 **Current** 값은 변경되지 않습니다.<br /><br /> **RowState**가 **Added** 또는 **Modified**인 경우 **Modified**로 설정됩니다.<br /><br /> **RowState**가 **Deleted**였으면 **Deleted**로 유지됩니다.<br /><br /> **DataTable**에 없는 데이터 소스의 행이 추가되며, 해당 행의 **RowState**는 **Unchanged**로 설정됩니다.|  
|**UpdateCurrentValues**|들어오는 행과 **DataTable**에 이미 들어 있는 행의 **PrimaryKey** 값이 같으면 **Current** 값이 **Original** 값에 복사된 다음 들어오는 행의 내용으로 설정됩니다.<br /><br /> **DataTable**의 **RowState**가 **Added**였으면 **RowState**는 **Added**로 유지됩니다.  행이 **Modified** 또는 **Deleted**로 표시된 경우 **RowState**는 **Modified**입니다.<br /><br /> **DataTable**에 없는 데이터 소스의 행이 추가되며, 해당 행의 **RowState**는 **Added**로 설정됩니다.|  
  
 다음 샘플에서는 **Load** 메서드를 사용하여 **Northwind** 데이터베이스에 직원 생일 목록을 표시합니다.  
  
 \[Visual Basic\]  
  
```  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## 참고 항목  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)