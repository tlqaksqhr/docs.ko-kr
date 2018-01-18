---
title: "중첩된 스키마 요소 사이에 암시적 관계 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 740d45c47f46c311ed703fa11ec86a9739930944
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>중첩된 스키마 요소 사이에 암시적 관계 매핑
XSD(XML 스키마 정의 언어) 스키마에는 다른 형식 내부에 중첩된 복합 형식이 포함될 수 있습니다. 이 경우 매핑 프로세스에서는 기본 매핑을 적용하며 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
-   각 복합 형식(부모 및 자식)에 대해 하나의 테이블을 만듭니다.  
  
-   기본 키 열이 하나 더 각 테이블 정의 명명 된 부모에 unique 제약 조건이 없는 있으면 *TableName*_Id 여기서 *TableName* 부모 테이블의 이름입니다.  
  
-   기본 키로 추가 열을 식별 하는 부모 테이블에 기본 키 제약 조건 (설정 하 여는 **IsPrimaryKey** 속성을 **True**). 제약 조건으로 명명 되며 *#*  여기서  *#*  1, 2, 3, 및 등이 있습니다. 예를 들어, 첫 번째 제약 조건의 기본 이름은 Constraint1입니다.  
  
-   추가 열을 부모 테이블의 기본 키를 참조하는 외래 키로 식별하는 외래 키 제약 조건을 자식 테이블에 만듭니다. 으로 명명 되며 *ParentTable_ChildTable* 여기서 *ParentTable* 부모 테이블의 이름 및 *ChildTable* 자식 테이블의 이름입니다.  
  
-   부모와 자식 테이블 간의 데이터 관계를 만듭니다.  
  
 다음 예제는 스키마를 보여 줍니다. 여기서 **OrderDetail** 의 자식 요소인 **순서**합니다.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
   <xs:complexType>  
     <xs:choice maxOccurs="unbounded">  
       <xs:element name="Order">  
         <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 XML 스키마 매핑 프로세스의 다음 항목을 만듭니다는 **DataSet**:  
  
-   **순서** 및 **OrderDetail** 테이블입니다.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   에 unique 제약 조건을 **순서** 테이블입니다. **IsPrimaryKey** 속성이 **True**합니다.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   외래 키 제약 조건을 **OrderDetail** 테이블입니다.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   간의 관계는 **순서** 및 **OrderDetail** 테이블입니다. **Nested** 이 관계에 대 한 속성이로 설정 되어 **True** 때문에 **순서** 및 **OrderDetail** 스키마에서 요소가 중첩 .  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
