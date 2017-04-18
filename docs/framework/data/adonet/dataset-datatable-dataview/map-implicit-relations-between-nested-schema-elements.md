---
title: "중첩된 스키마 요소 간의 암시적 관계 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 중첩된 스키마 요소 간의 암시적 관계 매핑
XSD\(XML 스키마 정의 언어\) 스키마에는 다른 형식 내부에 중첩된 복합 형식이 포함될 수 있습니다.  이 경우 매핑 프로세스에서는 기본 매핑을 적용하며 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
-   각 복합 형식\(부모 및 자식\)에 대해 하나의 테이블을 만듭니다.  
  
-   부모에 UNIQUE 제약 조건이 없는 경우 각 테이블 정의에는 *TableName*\_Id라는 추가 기본 키 열이 하나 포함됩니다. 여기서 *TableName*은 부모 테이블의 이름입니다.  
  
-   **IsPrimaryKey** 속성을 **True**로 설정함으로써 추가 열을 기본 키로 식별하는 기본 키 제약 조건을 부모 테이블에 만듭니다.  제약 조건은 Constraint*\#*으로 명명되며, 여기서 *\#*은 1, 2, 3 등을 나타냅니다.  예를 들어, 첫 번째 제약 조건의 기본 이름은 Constraint1입니다.  
  
-   추가 열을 부모 테이블의 기본 키를 참조하는 외래 키로 식별하는 외래 키 제약 조건을 자식 테이블에 만듭니다.  제약 조건은 *ParentTable\_ChildTable*로 명명되며, 여기서 *ParentTable*은 부모 테이블의 이름이고 *ChildTable*은 자식 테이블의 이름입니다.  
  
-   부모와 자식 테이블 간의 데이터 관계를 만듭니다.  
  
 다음 예제에서는 **OrderDetail**이 **Order**의 자식 요소인 스키마를 보여 줍니다.  
  
```  
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
  
 XML 스키마 매핑 프로세스에서는 **DataSet**에 다음 항목을 만듭니다.  
  
-   **Order** 및 **OrderDetail** 테이블을 만듭니다.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   **Order** 테이블에 UNIQUE 제약 조건을 만듭니다.  **IsPrimaryKey** 속성은 **True**로 설정됩니다.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   **OrderDetail** 테이블에 외래 키 제약 조건을 만듭니다.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   **Order** 및 **OrderDetail** 테이블 간의 관계를 만듭니다.  스키마에서 **Order** 및 **OrderDetail** 요소가 중첩되었기 때문에 이 관계의 **Nested** 속성은 **True**로 설정됩니다.  
  
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
  
## 참고 항목  
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)