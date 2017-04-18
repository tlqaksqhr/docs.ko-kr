---
title: "XSD(XML 스키마)에서 DataSet 관계 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# XSD(XML 스키마)에서 DataSet 관계 생성
<xref:System.Data.DataSet>에서는 부모\-자식 관계를 만들어 둘 이상의 열을 연결시킵니다.  XSD\(XML 스키마 정의 언어\) 스키마에서는 다음 세 가지 방법으로 **DataSet** 관계를 표현합니다.  
  
-   중첩된 복합 형식을 지정합니다.  
  
-   **msdata:Relationship** 주석을 사용합니다.  
  
-   **msdata:ConstraintOnly** 주석을 사용하지 않고 **xs:keyref**를 지정합니다.  
  
## 중첩된 복합 형식  
 스키마에서 중첩된 복합 형식의 정의는 요소의 부모\-자식 관계를 나타냅니다.  다음 XML 스키마 조각에서는 **OrderDetail**이 **Order** 요소의 자식 요소임을 보여 줍니다.  
  
```  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 XML 스키마 매핑 프로세스에서는 스키마의 중첩된 복합 형식에 대응하는 **DataSet**의 테이블을 만듭니다.  또한 생성된 테이블에 대한 부모**\-**자식 열로 사용되는 추가 열을 만듭니다.  이러한 부모**\-**자식 열에서는 관계를 지정하는데 이것은 기본 키\/외래 키 제약 조건을 지정하는 것과는 다릅니다.  
  
## msdata:Relationship 주석  
 **msdata:Relationship** 주석을 사용하여 중첩되지 않은 스키마의 요소 간에 부모\-자식 관계를 명시적으로 지정할 수 있습니다.  다음 예제에서는 **Relationship** 요소의 구조를 보여 줍니다.  
  
```  
  
  <msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 **msdata:Relationship** 주석의 특성에서는 부모\-자식 관계에 포함된 요소뿐만 아니라 이 관계에 포함된 **parentkey** 및 **childkey** 요소와 특성도 식별합니다.  매핑 프로세스에서는 이 정보를 사용하여 **DataSet**에 테이블을 생성하고 이러한 테이블 간에 기본 키\/외래 키 관계를 만듭니다.  
  
 예를 들어, 다음 스키마 조각에서는 중첩되지 않은 같은 수준의 **Order** 및 **OrderDetail** 요소를 지정합니다.  이 스키마에서는 **msdata:Relationship** 주석을 지정하는데, 이 주석은 이러한 두 요소 간의 부모\-자식 관계를 지정합니다.  이 경우 반드시 **msdata:Relationship** 주석을 사용하여 명시적 관계를 지정해야 합니다.  
  
```  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
  
```  
  
 이 매핑 프로세스에서는 **Relationship** 요소를 사용하여 **DataSet**에 **Order** 테이블의 **OrderNumber** 열과 **OrderDetail** 테이블의 **OrderNo** 열 간에 부모\-자식 관계를 만듭니다.  매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키\/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.  
  
### 단원 내용  
 [중첩된 스키마 요소 간의 암시적 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 XML 스키마에 중첩된 요소가 있을 경우 **DataSet**에서 암시적으로 만들어지는 제약 조건 및 관계에 대해 설명합니다.  
  
 [중첩된 요소에 지정된 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 **DataSet**에서 XML 스키마의 중첩된 요소에 대해 관계를 명시적으로 설정하는 방법을 설명합니다.  
  
 [중첩되지 않은 요소 간의 관계 지정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 **DataSet**에서 중첩되지 않은 XML 스키마 요소 간에 관계를 만드는 방법을 설명합니다.  
  
### 관련 단원  
 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 XSD\(XML 스키마 정의 언어\) 스키마에서 만들어지는 **DataSet**의 관계 구조 또는 스키마에 대해 설명합니다.  
  
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet**에서 고유 및 외래 키 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)