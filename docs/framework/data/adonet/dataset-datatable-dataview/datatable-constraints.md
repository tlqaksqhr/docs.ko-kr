---
title: "DataTable 제약 조건 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTable 제약 조건
제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다.  제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다.  제약 조건은 <xref:System.Data.DataSet>의  `System.Data.DataSet.EnforceConstraints`가 **true**인 경우에 적용됩니다.  `EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.  
  
 ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다.  기본적으로 <xref:System.Data.DataRelation>을 **DataSet**에 추가하여 둘 이상의 테이블 간에 관계를 만들면 이러한 두 제약 조건이 자동으로 만들어집니다.  그러나 관계를 만들 때 **createConstraints** \= **false**를 지정하여 이 동작이 실행되지 못하게 할 수 있습니다.  
  
## ForeignKeyConstraint  
 **ForeignKeyConstraint**는 관련 테이블에서의 업데이트 및 삭제를 전파하는 방법에 대한 규칙을 적용합니다.  예를 들어, 특정 테이블의 행 값이 업데이트되거나 삭제되는 경우 또는 이 값이 하나 이상의 관련 테이블에서 사용되는 경우, **ForeignKeyConstraint**는 관련 테이블에서 실행되는 동작을 결정합니다.  
  
 **ForeignKeyConstraint**의 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> 및 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 속성은 사용자가 관련 테이블의 행을 삭제하거나 업데이트할 때 수행해야 하는 작업을 정의합니다.  다음 표에서는 **ForeignKeyConstraint**의 **DeleteRule** 및 **UpdateRule** 속성에서 사용할 수 있는 다양한 설정에 대해 설명합니다.  
  
|규칙 설정|설명|  
|-----------|--------|  
|**Cascade**|관련 행을 삭제하거나 업데이트합니다.|  
|**SetNull**|관련 행의 값을 **DBNull**로 설정합니다.|  
|**SetDefault**|관련 행의 값을 기본값으로 설정합니다.|  
|**없음**|관련 행에 대해 아무 동작도 수행하지 않습니다.  이 값이 기본값입니다.|  
  
 **ForeignKeyConstraint**는 관련 열의 변경 사항을 제약할 수 있을 뿐만 아니라 전파할 수도 있습니다.  열의 **ForeignKeyConstraint**에 대한 속성 집합에 따라서, 또는 **DataSet**의 **EnforceConstraints** 속성이 **true**로 설정된 경우, 부모 행에서 특정 동작을 수행하면 예외가 발생합니다.  예를 들어, **ForeignKeyConstraint**의 **DeleteRule** 속성이 **None**으로 설정된 경우, 자식 행이 하나라도 포함되어 있는 부모 행은 삭제할 수 없습니다.  
  
 **ForeignKeyConstraint** 생성자를 사용하여 단일 열 사이 또는 열 배열 사이에서 외래 키 제약 조건을 만들 수 있습니다.  생성된 **ForeignKeyConstraint** 개체를 테이블의 **Constraints** 속성에 있는 **Add** 메서드로 전달합니다. 이 속성은 **ConstraintCollection**입니다.  **ConstraintCollection**의 **Add** 메서드의 여러 오버로드에 생성자 인수를 전달하여 **ForeignKeyConstraint**를 만들 수도 있습니다.  
  
 **ForeignKeyConstraint**를 만드는 경우 **DeleteRule** 및 **UpdateRule** 값을 생성자에 인수로 전달하거나 다음 예제와 같이 속성으로 설정할 수 있습니다. 여기서 **DeleteRule** 값은 **None**으로 설정되어 있습니다.  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### AcceptRejectRule  
 행에 대한 변경 내용은 **AcceptChanges** 메서드를 사용하여 적용하거나 **DataSet**, **DataTable** 또는 **DataRow**의 **RejectChanges** 메서드를 사용하여 취소할 수 있습니다.  **DataSet**에 **ForeignKeyConstraints**가 포함되어 있는 경우 **AcceptChanges** 또는 **RejectChanges** 메서드는 **AcceptRejectRule**을 적용합니다.  부모 행에서 **AcceptChanges** 또는 **RejectChanges**가 호출되는 경우, **ForeignKeyConstraint**의 **AcceptRejectRule** 속성은 자식 행에서 수행되는 동작을 결정합니다.  
  
 다음 표에서는 **AcceptRejectRule**에 대해 사용 가능한 설정의 목록을 보여 줍니다.  
  
|규칙 설정|설명|  
|-----------|--------|  
|**Cascade**|자식 행의 변경을 승인하거나 거부합니다.|  
|**없음**|자식 행에 대해 아무 동작도 수행하지 않습니다.  이 값이 기본값입니다.|  
  
### 예제  
 다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.DataTable> 개체의 <xref:System.Data.ConstraintCollection>에 추가합니다.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## UniqueConstraint  
 **UniqueConstraint** 개체는 **DataTable**의 단일 열 또는 열 배열에 할당될 수 있습니다. 이 개체를 사용하면 지정한 하나 이상의 열에서 모든 데이터가 행별로 고유한지 확인할 수 있습니다.  또한 **UniqueConstraint** 생성자를 사용하면 열 또는 열 배열의 UNIQUE 제약 조건을 만들 수 있습니다.  생성된 **UniqueConstraint** 개체를 테이블의 **Constraints** 속성에 있는 **Add** 메서드로 전달합니다. 이 속성은 **ConstraintCollection**입니다.  **ConstraintCollection**의 **Add** 메서드의 여러 오버로드에 생성자 인수를 전달하여 **UniqueConstraint**를 만들 수도 있습니다.  하나 이상의 열에 대해 **UniqueConstraint**를 만들 때 해당 열이 기본 키인지 여부를 선택적으로 지정할 수 있습니다.  
  
 열의 **Unique** 속성을 **true**로 설정하여 열에 대해 UNIQUE 제약 조건을 만들 수도 있습니다.  또는 단일 열의 **Unique** 속성을 **false**로 설정하면 UNIQUE 제약 조건\(있는 경우\)이 제거됩니다.  하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다.  **DataTable**의 **PrimaryKey** 속성에서 열을 제거하면 **UniqueConstraint**가 제거됩니다.  
  
 다음 예제에서는 **DataTable**의 두 열에 대해 **UniqueConstraint**를 만듭니다.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## 참고 항목  
 <xref:System.Data.DataRelation>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.ForeignKeyConstraint>   
 <xref:System.Data.UniqueConstraint>   
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)