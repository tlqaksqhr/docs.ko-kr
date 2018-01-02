---
title: "DataTable에 열 추가"
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
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 423b9ed389a5a3750c8e9b0339e0887d6b650741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-columns-to-a-datatable"></a>DataTable에 열 추가
A <xref:System.Data.DataTable> 의 컬렉션을 포함 <xref:System.Data.DataColumn> 에서 참조 한 개체는 **열** 테이블의 속성입니다. 이 열 컬렉션과 모든 제약 조건을 함께 사용하여 테이블의 스키마나 구조를 정의합니다.  
  
 만들 **DataColumn** 사용 하 여 테이블 내에서 개체는 **DataColumn** 생성자를 호출 하 여는 **추가** 의 메서드는 **열**되는 테이블의 속성을 <xref:System.Data.DataColumnCollection>합니다. **추가** 메서드에 선택적 **ColumnName**, **DataType**, 및 **식** 인수 하 고 새 만듭니다  **DataColumn** 컬렉션의 구성원으로 합니다. 에서도 기존의 적용 **DataColumn** 개체를 컬렉션에 추가 하며 추가에 대 한 참조를 반환 **DataColumn** 요청 하는 경우. 때문에 **DataTable** 의 데이터 형식을 지정할 때 사용 되는.NET Framework 형식, 개체를 데이터 소스로 한정 되지 않는 한 **DataColumn**합니다.  
  
 다음 예제에서는 4 번째 열에는 **DataTable**합니다.  
  
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
  
 예제에서는 다음에 유의 대 한 속성의 **CustID** 열을 허용 하지 않도록 설정 **DBNull** 값 및 값을 고유 값을 제한 하 합니다. 그러나 정의 하는 경우는 **CustID** 열 테이블의 기본 키 열으로는 **AllowDBNull** 속성으로 자동 설정 **false** 및는 **Unique** 속성으로 자동 설정 **true**합니다. 자세한 내용은 참조 [기본 키 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.  
  
> [!CAUTION]
>  열에는 열에는 증분 기본 이름인 지정할은 열 이름이 열에 대해 제공 되지 않은 경우*N,* "Column1" 부터는 것에 추가 된 경우는 **DataColumnCollection**합니다. 명명 규칙을 방지 하는 것이 좋습니다 "열*N*"에 있는 기존의 기본 열 이름과 충돌이 발생할 수 있습니다 제공 이름을 하기 때문에 열 이름을 제공 하는 경우는 **DataColumnCollection**합니다. 이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 <xref:System.Xml.Linq.XElement>를 <xref:System.Data.DataColumn.DataType%2A>에서 <xref:System.Data.DataColumn>의 <xref:System.Data.DataTable>로 사용하는 경우 데이터를 읽을 때 XML serialization이 작동하지 않습니다. 예를 들어 <xref:System.Xml.XmlDocument> 메서드를 사용하여 `DataTable.WriteXml`를 작성하는 경우 XML에 대한 serialization 수행 시 <xref:System.Xml.Linq.XElement>에 추가 부모 노드가 있습니다. 이 문제를 해결하려면 <xref:System.Data.SqlTypes.SqlXml> 대신 <xref:System.Xml.Linq.XElement> 형식을 사용합니다. `ReadXml` 및 `WriteXml`이 <xref:System.Data.SqlTypes.SqlXml>와 올바르게 작동합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
