---
title: "DataTable에 열 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable에 열 추가
<xref:System.Data.DataTable>에는 테이블의 **Columns** 속성에서 참조하는 <xref:System.Data.DataColumn> 개체의 컬렉션이 포함되어 있습니다.  이 열 컬렉션과 모든 제약 조건을 함께 사용하여 테이블의 스키마나 구조를 정의합니다.  
  
 **DataColumn** 생성자를 사용하거나 테이블의 **Columns** 속성, 즉 <xref:System.Data.DataColumnCollection>의 **Add** 메서드를 호출하여 테이블 안에 **DataColumn** 개체를 만듭니다.  **Add** 메서드에서는 선택적인 **ColumnName**, **DataType** 및 **Expression** 인수를 승인하며, 컬렉션의 멤버로서 새 **DataColumn**을 만듭니다.  이 메서드에서는 또한 기존의 **DataColumn** 개체를 승인하여 컬렉션에 추가하며, 필요한 경우 추가된 **DataColumn**의 참조를 반환합니다.  **DataTable** 개체는 특정 데이터 소스로 한정되지 않습니다. 따라서 **DataColumn**의 데이터 형식을 지정할 때는 .NET Framework 형식이 사용됩니다.  
  
 다음 예제에서는 **DataTable**에 네 개의 열을 추가합니다.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 이 예제에서는 **CustID** 열의 속성이 **DBNull** 값을 허용하지 않고 이 값을 고유 값으로 제약하도록 설정되어 있습니다.  그러나 **CustID** 열을 테이블의 기본 키 열로 정의하는 경우, **AllowDBNull** 속성은 **false**로 자동 설정되고 **Unique** 속성은 **true**로 자동 설정됩니다.  자세한 내용은 [기본 키 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)을 참조하세요.  
  
> [!CAUTION]
>  열에 이름이 입력되지 않은 경우 해당 열을 **DataColumnCollection**에 추가하면 열 이름이 "Column1"로 시작하는 Column*N*인 증분 기본 이름으로 지정됩니다.  열 이름을 입력하는 경우에는 "Column*N*" 명명 규칙을 사용하지 않는 것이 좋습니다. 이 경우 **DataColumnCollection**에 있는 기존의 기본 열 이름과 충돌이 발생할 수 있습니다.  이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 <xref:System.Xml.XLinq.XElement>를 <xref:System.Data.DataTable>에서 <xref:System.Data.DataColumn>의 <xref:System.Data.DataColumn.DataType%2A>로 사용하는 경우 데이터를 읽을 때 XML serialization이 작동하지 않습니다.  예를 들어 `DataTable.WriteXml` 메서드를 사용하여 <xref:System.Xml.XmlDocument>를 작성하는 경우 XML에 대한 serialization 수행 시 <xref:System.Xml.XLinq.XElement>에 추가 부모 노드가 있습니다.  이 문제를 해결하려면 <xref:System.Xml.XLinq.XElement> 대신 <xref:System.Data.SqlTypes.SqlXml> 형식을 사용합니다.  `ReadXml` 및 `WriteXml`이 <xref:System.Data.SqlTypes.SqlXml>와 올바르게 작동합니다.  
  
## 참고 항목  
 <xref:System.Data.DataColumn>   
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataTable>   
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)