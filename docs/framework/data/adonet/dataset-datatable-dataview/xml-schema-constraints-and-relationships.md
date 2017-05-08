---
title: "XML 스키마 제약 조건 및 관계 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# XML 스키마 제약 조건 및 관계
XSD\(XML 스키마 정의 언어\) 스키마에서는 UNIQUE, KEY, KEYREF 등의 제약 조건 및 관계\(**msdata:Relationship** 주석 사용\)를 지정할 수 있습니다.  이 항목에서는 XML 스키마에 지정된 제약 조건과 관계를 해석하여 <xref:System.Data.DataSet>을 생성하는 방법을 설명합니다.  
  
 일반적으로 XML 스키마에서는, **DataSet**에서 관계만을 생성하려는 경우 **msdata:Relationship** 주석을 지정합니다.  자세한 내용은 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)을 참조하세요.  **DataSet**에서 제약 조건을 생성하려는 경우에는 UNIQUE, KEY 및 KEYREF 등의 제약 조건을 지정합니다.  이 항목의 뒷부분에서 설명하겠지만 KEY 및 KEYREF 제약 조건도 관계를 생성하는 데 사용됩니다.  
  
## KEY 및 KEYREF 제약 조건에서 관계 생성  
 **msdata:Relationship** 주석을 지정하는 대신 XML 스키마 매핑 프로세스를 수행하는 동안 사용되는 KEY 및 KEYREF 제약 조건을 지정하여 **DataSet**에 제약 조건뿐만 아니라 관계도 생성할 수 있습니다.  그러나 **KEYREF** 요소에서 `msdata:ConstraintOnly="true"`를 지정하면 **DataSet**에는 제약 조건만 포함되며 관계는 포함되지 않습니다.  
  
 다음 예제에서는 중첩되지 않은 **Order** 및 **OrderDetail** 요소가 포함된 XML 스키마를 보여 줍니다.  스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
```  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 XML 스키마 매핑 프로세스를 수행하는 동안 생성된 **DataSet**에는 **Order** 및 **OrderDetail** 테이블이 포함됩니다.  또한 **DataSet**에는 관계와 제약 조건도 포함됩니다.  다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.  이 스키마에서는 **msdata:Relationship** 주석을 지정하지 않고, 대신 KEY 및 KEYREF 제약 조건을 사용하여 관계를 생성합니다.  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 이전 스키마 예제에서는 **Order** 및 **OrderDetail** 요소가 중첩되지 않습니다.  다음 스키마 예제에서는 이들 요소가 중첩됩니다.  하지만 **msdata:Relationship** 주석이 지정되지 않기 때문에 암시적 관계가 가정됩니다.  자세한 내용은 [중첩된 스키마 요소 간의 암시적 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)을 참조하세요.  스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
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
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 XML 스키마 매핑 프로세스의 결과로서 만들어진 **DataSet**에는 다음 두 테이블이 포함됩니다.  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 또한 **DataSet**에는 두 개의 관계\(하나는 **msdata:relationship** 주석을 기반으로 하며, 다른 하나는 KEY 및 KEYREF 제약 조건을 기반으로 함\)와 다양한 제약 조건이 포함됩니다.  다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 중첩된 테이블을 참조하는 KEYREF 제약 조건에 **msdata:IsNested\="true"** 주석이 포함되어 있으면 **DataSet**에서는 KEYREF 제약 조건 및 관련 UNIQUE\/KEY 제약 조건을 기반으로 하는 단일 중첩 관계를 만듭니다.  
  
## 참고 항목  
 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)