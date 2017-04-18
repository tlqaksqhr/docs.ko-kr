---
title: "기본 키 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 기본 키 정의
일반적으로 데이터베이스 테이블에는 테이블의 각 행을 고유하게 식별하는 열 또는 열 그룹이 있습니다.  이 식별 열 또는 열 그룹을 기본 키라고 합니다.  
  
 단일 <xref:System.Data.DataColumn>이 <xref:System.Data.DataTable>의 <xref:System.Data.DataTable.PrimaryKey%2A>로 식별되는 경우, 테이블에서 열의 <xref:System.Data.DataColumn.AllowDBNull%2A> 속성은 **false**로 자동 설정되고, <xref:System.Data.DataColumn.Unique%2A> 속성은 **true**로 자동 설정됩니다.  열이 여러 개인 기본 키의 경우에는 **AllowDBNull** 속성만 **false**로 자동 설정됩니다.  
  
 다음 예제에서와 같이, <xref:System.Data.DataTable>의 **PrimaryKey** 속성 값은 하나 이상의 **DataColumn** 개체 배열로 구성됩니다.  첫 번째 예제에서는 단일 열이 기본 키로 정의됩니다.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 다음 예제에서는 두 열이 기본 키로 정의됩니다.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## 참고 항목  
 <xref:System.Data.DataTable>   
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)