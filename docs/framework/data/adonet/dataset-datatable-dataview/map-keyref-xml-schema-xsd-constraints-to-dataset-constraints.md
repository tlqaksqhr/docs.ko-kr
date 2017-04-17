---
title: "DataSet 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
**keyref** 요소를 사용하면 문서 내의 요소 간에 링크를 만들 수 있습니다.  이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다.  스키마에서 **keyref** 요소를 지정하면, 스키마 매핑 프로세스를 수행하는 동안 이 요소는 <xref:System.Data.DataSet>의 테이블에 있는 열에 대한 해당 외래 키 제약 조건으로 변환됩니다.  또한 기본적으로 **keyref** 요소는 해당 관계에 지정된 **ParentTable**, **ChildTable**, **ParentColumn** 및 **ChildColumn** 속성으로 관계를 생성합니다.  
  
 다음 표에서는 **keyref** 요소에서 지정할 수 있는 **msdata** 특성에 대해 간략히 설명합니다.  
  
|특성 이름|설명|  
|-----------|--------|  
|**msdata:ConstraintOnly**|스키마의 **keyref** 요소에 **ConstraintOnly\="true"**가 지정되면 제약 조건은 만들어지지만 관계는 만들어지지 않습니다.  이 특성이 지정되지 않았거나 **False**로 설정된 경우에는 **DataSet**에서 제약 조건과 관계가 모두 만들어집니다.|  
|**msdata:ConstraintName**|**ConstraintName** 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.  그렇지 않으면, 스키마에 있는 **keyref** 요소의 **name** 특성에서 **DataSet**에서의 제약 조건 이름을 제공합니다.|  
|**msdata:UpdateRule**|**UpdateRule** 특성이 스키마의 **keyref** 요소에 지정되면 해당 값은 **DataSet**의 **UpdateRule** 제약 조건 속성에 할당됩니다.  그렇지 않으면, **UpdateRule** 속성이 **Cascade**로 설정됩니다.|  
|**msdata:DeleteRule**|**DeleteRule** 특성이 스키마의 **keyref** 요소에 지정되면 해당 값은 **DataSet**의 **DeleteRule** 제약 조건 속성에 할당됩니다.  그렇지 않으면, **DeleteRule** 속성이 **Cascade**로 설정됩니다.|  
|**msdata:AcceptRejectRule**|**AcceptRejectRule** 특성이 스키마의 **keyref** 요소에 지정되면 해당 값은 **DataSet**의 **AcceptRejectRule** 제약 조건 속성에 할당됩니다.  그렇지 않으면, **AcceptRejectRule** 속성이 **None**으로 설정됩니다.|  
  
 다음 예제에는 **Order** 요소의 **OrderNumber** 자식 요소와 **OrderDetail** 요소의 **OrderNo** 자식 요소 간에 **key** 및 **keyref** 관계를 지정하는 스키마가 포함되어 있습니다.  
  
 이 예제에서 **OrderDetail** 요소의 **OrderNumber** 자식 요소는 **Order** 요소의 **OrderNo** 키 자식 요소를 참조합니다.  
  
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
  
 XSD\(XML 스키마 정의 언어\) 스키마 매핑 프로세스에서는 두 개의 테이블이 있는 다음 **DataSet**을 생성합니다.  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 또한 **DataSet**에서는 다음 제약 조건을 정의합니다.  
  
-   **Order** 테이블에 UNIQUE 제약 조건을 만듭니다.  
  
    ```  
  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   **Order** 및 **OrderDetail** 테이블 간의 관계를 만듭니다.  두 요소가 스키마에서 중첩되지 않았기 때문에 **Nested** 속성은 **False**로 설정됩니다.  
  
    ```  
  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   **OrderDetail** 테이블에 외래 키 제약 조건을 만듭니다.  
  
    ```  
  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## 참고 항목  
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)