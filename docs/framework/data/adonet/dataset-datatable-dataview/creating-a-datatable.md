---
title: "DataTable 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable 만들기
<xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.  
  
 적절한 **DataTable** 생성자를 사용하면 **DataTable** 개체를 만들 수 있습니다.  이 생성자는 **Add** 메서드를 사용하여 **DataTable** 개체의 **Tables** 컬렉션에 추가하는 방식으로 **DataSet**에 추가할 수 있습니다.  
  
 또한 **DataTable** 개체는 **DataAdapter** 개체의 **Fill** 또는 **FillSchema** 메서드를 사용하여 **DataSet** 내에서 만들거나 **DataSet**의 **ReadXml**, **ReadXmlSchema** 또는 **InferXmlSchema** 메서드를 사용하여 미리 정의되거나 유추된 XML 스키마에서 만들 수도 있습니다.  **DataTable**을 특정 **DataSet**의 **Tables** 컬렉션 멤버로 추가한 후에는 기타 모든 **DataSet**의 테이블 컬렉션에 추가할 수 없습니다.  
  
 **DataTable**을 처음 만드는 경우에는 스키마\(구조\)가 존재하지 않습니다.  테이블 스키마를 정의하려면 <xref:System.Data.DataColumn> 개체를 만들어 테이블의 **Columns** 컬렉션에 추가해야 합니다.  사용자는 또한 테이블의 기본 키 열을 정의할 수 있으며 **Constraint** 개체를 만들어 테이블의 **Constraints** 컬렉션에 추가할 수 있습니다.  **DataTable** 스키마를 정의한 후에는 테이블의 **Rows** 컬렉션에 **DataRow** 개체를 추가하여 테이블에 데이터 행을 추가할 수 있습니다.  
  
 **DataTable**을 만드는 경우에는 <xref:System.Data.DataTable.TableName%2A> 속성 값을 입력할 필요가 없습니다. 이 속성은 나중에 지정할 수 있으며 비워 놓을 수도 있습니다.  그러나 **TableName** 값이 없는 테이블을 **DataSet**에 추가하는 경우, 해당 테이블의 이름은 Table0부터 시작하는 증분 기본 이름인 Table*N*으로 지정됩니다.  
  
> [!NOTE]
>  **TableName** 값을 입력하는 경우에는 "Table*N*" 명명 규칙을 사용하지 않는 것이 좋습니다. 이 경우 **DataSet**에 있는 기존의 기본 테이블 이름과 충돌이 발생할 수 있습니다.  이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 다음 예제에서는 **DataTable** 개체의 인스턴스를 만들고 이름을 "Customers"로 지정합니다.  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 다음 예제에서는 **DataSet**의 **Tables** 컬렉션에 **DataTable**의 인스턴스를 추가하여 만듭니다.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## 참고 항목  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataTableCollection>   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)