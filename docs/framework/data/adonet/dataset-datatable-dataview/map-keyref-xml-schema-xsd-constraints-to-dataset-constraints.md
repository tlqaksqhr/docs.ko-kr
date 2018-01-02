---
title: "데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f888a682510dbf768e5eab2ffdd530e2ac7cf635
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
**keyref** 요소는 문서 내의 요소 간에 링크를 만들 수 있습니다. 이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다. 스키마를 지정 하는 경우는 **keyref** 요소가 요소는 해당 외래 키 제약 조건 테이블의 열에 스키마 매핑 프로세스 중에 변환 됩니다는 <xref:System.Data.DataSet>합니다. 기본적으로는 **keyref** 요소와는 관계 생성의 **ParentTable**, **ChildTable**, **ParentColumn**, 및  **ChildColumn** 해당 관계에 지정 된 속성입니다.  
  
 다음 표에서 윤곽선은 **msdata** 특성에 지정할 수 있습니다는 **keyref** 요소입니다.  
  
|특성 이름|설명|  
|--------------------|-----------------|  
|**사용**|경우 **ConstraintOnly = "true"** 에 지정 된 **keyref** 스키마의 요소를 한 제약 조건을 만들어지지만 관계는 만들어지지입니다. 이 특성이 지정 되지 않은 경우 (또는로 설정 되어 **False**)에 제약 조건과 관계가 모두 만들어집니다는 **데이터 집합**합니다.|  
|**msdata:ConstraintName**|경우는 **ConstraintName** 특성을 지정 하면 해당 값 제약 조건 이름으로 사용 됩니다. 그렇지 않은 경우는 **이름** 특성에는 **keyref** 스키마의 요소에서의 제약 조건 이름을 제공는 **데이터 집합**합니다.|  
|**msdata:UpdateRule**|경우는 **UpdateRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **UpdateRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **UpdateRule** 속성이 **Cascade**합니다.|  
|**msdata:DeleteRule**|경우는 **DeleteRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **DeleteRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **DeleteRule** 속성이 **Cascade**합니다.|  
|**msdata:AcceptRejectRule**|경우는 **AcceptRejectRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **AcceptRejectRule** 제약 조건 속성에는  **데이터 집합**합니다. 그렇지 않은 경우는 **AcceptRejectRule** 속성이 **None**합니다.|  
  
 다음 예제에 지정 하는 스키마는 **키** 및 **keyref** 간의 관계는 **OrderNumber** 의 자식 요소는 **순서**  요소 및 **OrderNo** 의 자식 요소는 **OrderDetail** 요소입니다.  
  
 예제에서는 **OrderNumber** 의 자식 요소는 **OrderDetail** 요소를 참조는 **OrderNo** 의 키 자식 요소는 **순서**요소입니다.  
  
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
  
 다음을 생성 하는 XML 스키마 정의 언어 (XSD) 스키마 매핑 프로세스 **DataSet** 두 테이블이 포함 된:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 또한는 **DataSet** 다음과 같은 제약 조건을 정의 합니다.  
  
-   에 unique 제약 조건을 **순서** 테이블입니다.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   간의 관계는 **순서** 및 **OrderDetail** 테이블입니다. **Nested** 속성이 **False** 두 요소가 스키마에서 중첩 되지 않은 때문에 있습니다.  
  
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
  
-   외래 키 제약 조건을 **OrderDetail** 테이블입니다.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
