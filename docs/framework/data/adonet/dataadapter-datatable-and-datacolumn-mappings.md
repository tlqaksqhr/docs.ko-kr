---
title: "DataAdapter DataTable 및 DataColumn 매핑"
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
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e104ba75026c2ff387eb7c74b11c505e34085f41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>DataAdapter DataTable 및 DataColumn 매핑
A **DataAdapter** 0 개 이상의 컬렉션을 포함 <xref:System.Data.Common.DataTableMapping> 개체에 해당 **TableMappings** 속성입니다. A **DataTableMapping** 데이터 원본에 대해 쿼리에서 반환 된 데이터 간의 마스터 매핑을 제공 및 <xref:System.Data.DataTable>합니다. **DataTableMapping** 이름 자리에 전달 될 수 있습니다는 **DataTable** 이름에 **채우기** 의 메서드는 **DataAdapter**합니다. 다음 예제에서는 한 **DataTableMapping** 라는 **AuthorsMapping** 에 대 한는 **작성자** 테이블입니다.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 A **DataTableMapping** 의 열 이름을 사용할 수 있습니다는 **DataTable** 데이터베이스의 다른 합니다. **DataAdapter** 는 테이블이 업데이트 될 때 열을 일치 하는 매핑을 사용 합니다.  
  
 지정 하지 않는 경우는 **TableName** 또는 **DataTableMapping** 이름을 호출 하는 경우는 **채우기** 또는 **업데이트** 의 메서드는  **DataAdapter**, **DataAdapter** 찾습니다는 **DataTableMapping** "Table" 이라는 합니다. 해당 경우 **DataTableMapping** 존재 하지 않는 **TableName** 의 **DataTable** 은 "Table"입니다. 기본값을 지정할 수 **DataTableMapping** 만들어는 **DataTableMapping** "Table"의 이름으로 합니다.  
  
 다음 코드 예제에서는 **DataTableMapping** (에서 <xref:System.Data.Common> 네임 스페이스)에서 지정 된 기본 매핑을 사용 하면 **DataAdapter** "Table" 이름을 지정 합니다. 이 예제에는 다음 쿼리 결과에서 첫 번째 테이블의에서 열을 매핑합니다 (의 **고객** 테이블의는 **Northwind** 데이터베이스)의 더 친숙 한 이름 집합에는 **Northwind Customers**  테이블에 <xref:System.Data.DataSet>합니다. 매핑되지 않는 열의 경우 데이터 소스의 열 이름이 사용됩니다.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 더 고급 시나리오에서는 결정할 수 있습니다 사용할 동일한 **DataAdapter** 다른 매핑 사용 하 여 다른 테이블의 로드를 지원 하도록 합니다. 이 수행 하려면 추가 하기만 하면 **DataTableMapping** 개체입니다.  
  
 때는 **채우기** 메서드의 인스턴스를 전달 되는 **데이터 집합** 및 **DataTableMapping** 이름, 해당 이름의 매핑이 있으면이 고, 그렇지 않으면 사용 되는 한  **DataTable** 해당 이름이 사용 됩니다.  
  
 다음 예제에서는 한 **DataTableMapping** 의 이름으로 **고객** 및 **DataTable** 이름 **BizTalkSchema**합니다. 예제에서는 다음를 SELECT 문에서 반환한 행을 매핑하는 **BizTalkSchema** **DataTable**합니다.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  열 매핑에 소스 열 이름을 제공하지 않거나 테이블 매핑에 소스 테이블 이름을 제공하지 않으면 기본 이름이 자동으로 생성됩니다. 열 매핑의 증분 기본 이름인 제공 됩니다 열 매핑에 소스 열 제공 되는 경우 **SourceColumn** *N,* 부터는 **SourceColumn1**합니다. 테이블 매핑에 증분 기본 이름인 제공 됩니다 테이블 매핑에 소스 테이블 이름을 제공 되는 경우 **SourceTable** *N*부터 **SourceTable1**합니다.  
  
> [!NOTE]
>  명명 규칙을 방지 하는 것이 좋습니다 **SourceColumn** *N* 열 매핑에 또는 **SourceTable** *N* 테이블에 대 한 변수에 있는 기존의 기본 열 매핑 이름과 충돌할 수 있기 때문에 매핑하는 **ColumnMappingCollection** 또는 테이블 매핑 이름에는 **DataTableMappingCollection** . 이미 있는 이름을 제공하면 예외가 throw됩니다.  
  
## <a name="handling-multiple-result-sets"></a>여러 개의 결과 집합 처리  
 경우에 **SelectCommand** 여러 테이블을 반환 **채우기** 테이블에 대 한 증분 값을 갖는 테이블 이름을 자동으로 생성는 **데이터 집합**부터 테이블 이름 사이에서 형식 지정 **TableName** *N*부터 **TableName1**합니다. 테이블 매핑을 사용 하 여 원하는 테이블에 대해 지정 된 이름에 자동으로 생성 된 테이블 이름을 매핑하는 **DataSet**합니다. 예는 **SelectCommand** 두 테이블을 반환 하는 **고객** 및 **Orders**, 다음 호출을 실행 **채우기**합니다.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 두 테이블에서 생성 됩니다는 **DataSet**: **고객** 및 **Customers1**합니다. 테이블 매핑을 사용 하 여 두 번째 테이블은 이름이 있는지 확인 하기 위한 **Orders** 대신 **Customers1**합니다. 이 수행 하려면 원본 테이블의 매핑 **Customers1** 에 **데이터 집합** 테이블 **Orders**다음 예제에 나온 것 처럼 합니다.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>참고 항목  
 [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
