---
title: "XML 스키마 제약 조건 및 관계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e450954e4b0e51057e98dd329fe26c38f0ebbb05
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="xml-schema-constraints-and-relationships"></a>XML 스키마 제약 조건 및 관계
XML 스키마 정의 언어 (XSD) 스키마에서 제약 조건을 지정할 수 있습니다 (고유, key 및 keyref 제약 조건) 및 관계 (사용 하는 **msdata: relationship** 주석). 이 항목에서는 XML 스키마에 지정된 제약 조건과 관계를 해석하여 <xref:System.Data.DataSet>을 생성하는 방법을 설명합니다.  
  
 에 일반적으로 XML 스키마에서 지정 된 **msdata: relationship** 주석에서 관계만 생성 하려는 경우는 **데이터 집합**합니다. 자세한 내용은 참조 [에서 XSD (XML 스키마) 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)합니다. 제약 조건을 지정 (고유, key 및 keyref 등)에서 제약 조건을 생성 하려는 경우는 **DataSet**합니다. 이 항목의 뒷부분에서 설명하겠지만 KEY 및 KEYREF 제약 조건도 관계를 생성하는 데 사용됩니다.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>KEY 및 KEYREF 제약 조건에서 관계 생성  
 지정 하는 대신는 **msdata: relationship** 주석, XML 스키마 매핑 프로세스 중에 제약조건뿐만아니라관계를생성하는데사용되는key및keyref제약조건을지정할수있습니다 **데이터 집합**합니다. 그러나 지정 하는 경우 `msdata:ConstraintOnly="true"` 에 **keyref** 요소는 **데이터 집합** 제약 조건만 포함 하며 관계를 포함 하지 것입니다.  
  
 다음 예제에서는 포함 된 XML 스키마 **순서** 및 **OrderDetail** 중첩 되지 않은 요소입니다. 스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
```xml  
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
  
 **DataSet** XML 스키마 매핑 프로세스를 포함 하는 동안 생성 된는 **순서** 및 **OrderDetail** 테이블입니다. 또한는 **DataSet** 관계 및 제약 조건을 포함 합니다. 다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다. 스키마를 지정 하지 않는 참고는 **msdata: relationship** 주석; 관계를 생성 하는 key 및 keyref 제약 조건 대신 사용 됩니다.  
  
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
  
 이전 스키마 예제에서는 **순서** 및 **OrderDetail** 요소가 중첩 되지 않습니다. 다음 스키마 예제에서는 이들 요소가 중첩됩니다. 그러나 없습니다 **msdata: relationship** 에 주석이 지정 됩니다. 따라서 암시적 관계가 가정 됩니다. 자세한 내용은 참조 [지도 암시적 관계 사이 중첩 된 스키마 요소](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)합니다. 스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.  
  
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
  
 **DataSet** 두 테이블이 포함 된 XML 스키마 매핑 프로세스에서 발생 합니다.  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 **데이터 집합** 도 두 개의 관계가 포함 됩니다 (에 따라 하나는 **msdata: relationship** 주석 및 다른 key 및 keyref 제약 조건에 따라) 및 다양 한 제약 조건입니다. 다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.  
  
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
  
 중첩된 테이블을 참조 하는 keyref 제약 조건을 포함 하는 경우는 **msdata:IsNested = "true"** 주석을 **데이터 집합** keyref 제약 조건을 기반으로 하는 단일 중첩된 관계 만들어집니다 및 관련된 unique/key 제약 조건입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
