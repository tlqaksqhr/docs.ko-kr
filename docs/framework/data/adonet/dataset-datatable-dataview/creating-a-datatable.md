---
title: DataTable 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: a374c7c6e7dfc04cd8828208d6762f8d8665072e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767169"
---
# <a name="creating-a-datatable"></a>DataTable 만들기
<xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.  
  
 만들 수는 **DataTable** 적절 한 사용 하 여 개체 **DataTable** 생성자입니다. 에 추가할 수 있습니다는 **DataSet** 를 사용 하 여는 **추가** 메서드를 추가 하는 **DataTable** 개체의 **테이블** 컬렉션입니다.  
  
 만들 수도 있습니다 **DataTable** 내에서 개체는 **DataSet** 를 사용 하 여는 **채우기** 또는 **FillSchema** 의 메서드는  **DataAdapter** 개체 또는 미리 정의 된 또는 유추 된 XML 스키마 사용 하 여는 **ReadXml**, **ReadXmlSchema**, 또는 **InferXmlSchema** 메서드는 **DataSet**합니다. 에 추가 하면 사용자에 게 유의 **DataTable** 의 구성원으로는 **테이블** 하나의 컬렉션 **데이터 집합**, 다른 의테이블컬렉션에추가할수없습니다**DataSet**합니다.  
  
 처음 만드는 경우는 **DataTable**, 스키마 (구조)가 없습니다. 테이블의 스키마를 정의 하려면 만들고 해야 추가 <xref:System.Data.DataColumn> 개체는 **열** 테이블의 컬렉션입니다. 있습니다 수는 테이블에 대 한 기본 키 열을 정의 하 고 만들고 추가할 수도 **제약 조건** 개체는 **제약 조건을** 테이블의 컬렉션입니다. 에 대 한 스키마를 정의 하면는 **DataTable**, 추가 하 여 테이블에 데이터 행을 추가할 수 있습니다 **DataRow** 개체는 **행** 테이블의 컬렉션입니다.  
  
 에 대 한 값을 제공 하지 않아도 됩니다는 <xref:System.Data.DataTable.TableName%2A> 속성 만들 때 한 **DataTable**; 다른 시간에 속성을 지정 하거나 비워 둘 수 있습니다. 그러나 없는 테이블을 추가 하는 하면는 **TableName** 값을 한 **데이터 집합**, 테이블에는 증분 기본 이름인 Table 제공 됩니다*N*Table0 "Table"로 시작 합니다.  
  
> [!NOTE]
>  방지 하는 것이 좋습니다는 "테이블*N*" 명명 규칙을 제공 하는 경우는 **TableName** 값을 제공 하는 이름에 있는 기존의 기본 테이블 이름과 충돌이 발생할 수 있습니다는 **데이터 집합** . 이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 다음 예제에서는의 인스턴스는 **DataTable** 개체 하 고 이름을 "Customers" 할당  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 다음 예제에서는 인스턴스를 만듭니다는 **DataTable** 추가 하 여는 **테이블** 의 컬렉션을 **데이터 집합**합니다.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
