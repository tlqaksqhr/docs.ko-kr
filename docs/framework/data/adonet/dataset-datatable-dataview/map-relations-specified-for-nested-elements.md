---
title: "중첩된 요소에 지정된 관계 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9866b556f2ba09cef7616fea4a2a6d8135e6b8e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="map-relations-specified-for-nested-elements"></a>중첩된 요소에 지정된 관계 매핑
스키마를 포함할 수 있습니다는 **msdata: relationship** 주석을 명시적으로 스키마의 두 요소 간의 매핑을 지정 합니다. 에 지정 된 두 요소가 **msdata: relationship** 스키마에서 중첩 될 수 있지만 될 필요가 없습니다. 매핑 프로세스를 사용 하 여 **msdata: relationship** 두 열 간의 기본 키/외래 키 관계를 생성 하는 스키마에 있습니다.  
  
 다음 예제는 XML 스키마를 보여 줍니다.는 **OrderDetail** 의 자식 요소 **순서**합니다. **msdata: relationship** 이 부모-자식 관계를 식별 하 고 지정 하는 **OrderNumber** 열이 결과 **순서** 테이블이 관련 되어는 **OrderNo** 열이 결과 **OrderDetail** 테이블입니다.  
  
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
  
-   **순서** 및 **OrderDetail** 테이블입니다.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   간의 관계는 **순서** 및 **OrderDetail** 테이블입니다. **Nested** 이 관계에 대 한 속성이로 설정 되어 **True** 때문에 **순서** 및 **OrderDetail** 스키마에서 요소가 중첩 .  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 스키마 (XSD)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [데이터 집합 제약 조건에 XML 스키마 (XSD) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
