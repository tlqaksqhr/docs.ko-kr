---
title: "중첩된 요소에 지정된 관계 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 중첩된 요소에 지정된 관계 매핑
두 요소 간의 매핑을 명시적으로 지정하기 위해 스키마에 **msdata:Relationship** 주석이 포함될 수 있습니다.  **msdata:Relationship**에 지정된 두 요소는 스키마에서 중첩될 수 있으나 반드시 중첩되어야 하는 것은 아닙니다.  매핑 프로세스에서는 스키마의 **msdata:Relationship**을 사용하여 두 열 간에 기본 키\/외래 키 관계를 생성합니다.  
  
 다음 예제에서는 **OrderDetail** 요소가 **Order**의 자식 요소인 XML 스키마를 보여 줍니다.  **msdata:Relationship**에서는 이러한 부모\-자식 관계를 식별하여, 결과 **Order** 테이블의 **OrderNumber** 열이 결과 **OrderDetail** 테이블의 **OrderNo** 열과 연관된다고 지정합니다.  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
-   **Order** 및 **OrderDetail** 테이블을 만듭니다.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   **Order** 및 **OrderDetail** 테이블 간의 관계를 만듭니다.  스키마에서 **Order** 및 **OrderDetail** 요소가 중첩되었기 때문에 이 관계의 **Nested** 속성은 **True**로 설정됩니다.  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.  
  
## 참고 항목  
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)