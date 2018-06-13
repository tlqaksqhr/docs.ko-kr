---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 04defffc724875e691fd7b87331c28e6b6c0cd28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758310"
---
# <a name="the-load-method"></a>로드 메서드
<xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다. 이 가장 간단한 형태의 단일 매개 변수를 허용 하는 오버 로드 된 메서드는 **DataReader**합니다. 이 양식에서 단순히 로드는 **DataTable** 행이 있는 합니다. 선택적으로 지정할 수는 **LoadOption** 매개 변수 데이터를 추가 하는 방법을 제어 하는 **DataTable**합니다.  
  
 **LoadOption** 매개 변수는 경우에 특히 유용 여기서는 **DataTable** 이미 데이터 행이 포함 된, 데이터 원본에서 어떻게 들어오는 데이터를 설명 하므로 데이터와 결합 됩니다 이미 표에 합니다. 예를 들어 **PreserveCurrentValues** (기본값)을 지정 하는 경우로 표시 된 행에 **Added** 에 **DataTable**, **원래** 값 이나 각 열은 데이터 소스에서 일치 하는 행의 내용을로 설정 됩니다. **현재** 값 행이 추가 될 때 할당 하는 값을 유지 합니다 및 **RowState** 행의로 설정 됩니다 **Changed**합니다.  
  
 다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.  
  
|LoadOption 값|설명|  
|----------------------|-----------------|  
|**OverwriteRow**|들어오는 행이 동일한 있으면 **PrimaryKey** 값에 이미 들어 있는 행으로는 **DataTable**, **원래** 및 **현재** 각 값 열 들어오는 행의 값으로 대체 되 고 **RowState** 속성이로 설정 되어 **Unchanged**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본의 행의 **DataTable** 으로 추가 됩니다 한 **RowState** 값 **Unchanged**합니다.<br /><br /> 이 옵션에는 실제로 내용을 새로 고칩니다는 **DataTable** 데이터 소스의 내용과 일치 하도록 합니다.|  
|**PreserveCurrentValues (기본값)**|들어오는 행이 동일한 있으면 **PrimaryKey** 값에 이미 들어 있는 행으로는 **DataTable**, **원래** 들어오는 행과는 의내용에값이설정**현재** 값 변경 되지 않습니다.<br /><br /> 경우는 **RowState** 은 **Added** 또는 **Modified**로 설정 된 **Modified**합니다.<br /><br /> 경우는 **RowState** 되었습니다 **Deleted**, 상태로 유지 됩니다 **Deleted**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본의 행은 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Unchanged**합니다.|  
|**UpdateCurrentValues**|들어오는 행의 동일한 경우 **PrimaryKey** 값에 이미 들어 있는 행으로는 **DataTable**, **현재** 값에 복사 되는 **원래**값 및 **현재** 값이 들어오는 행의 내용으로 설정 됩니다.<br /><br /> 경우는 **RowState** 에 **DataTable** 되었습니다 **Added**, **RowState** 남아 **Added**합니다. 로 표시 된 행에 대 한 **Modified** 또는 **Deleted**, **RowState** 은 **Modified**합니다.<br /><br /> 에 이미 존재 하지 않는 데이터 원본의 행은 **DataTable** 추가 되 면 및 **RowState** 로 설정 되어 **Added**합니다.|  
  
 다음 샘플에서는 **부하** 에 직원 생일 목록을 표시 하는 메서드는 **Northwind** 데이터베이스입니다.  
  
```vb  
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
  
## <a name="see-also"></a>참고 항목  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
