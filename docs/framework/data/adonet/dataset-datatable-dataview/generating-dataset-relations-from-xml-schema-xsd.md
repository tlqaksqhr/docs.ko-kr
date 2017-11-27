---
title: "XSD(XML 스키마)에서 데이터 집합 관계 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bda9ff0052c6dc2462f007e3febb3cbf9ca7d5ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>XSD(XML 스키마)에서 데이터 집합 관계 생성
<xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다. 세 가지 방법으로 나타내는 데는 **DataSet** XML 스키마 정의 언어 (XSD) 스키마 내에서 관계:  
  
-   중첩된 복합 형식을 지정합니다.  
  
-   사용 하 여 **msdata: relationship** 주석입니다.  
  
-   지정 된 **xs: keyref** 없이 **사용** 주석입니다.  
  
## <a name="nested-complex-types"></a>중첩된 복합 형식  
 스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다. 다음 XML 스키마의 일부분을 보여 줍니다 **OrderDetail** 의 자식 요소는 **순서** 요소입니다.  
  
```xml  
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
  
 XML 스키마 매핑 프로세스에 테이블을 만듭니다는 **DataSet** 스키마에서 중첩된 된 복합 형식에 해당 하는 합니다. 또한 부모도 사용 되는 추가 열을 만듭니다**-**생성된 된 테이블에 대 한 자식 열입니다. 이러한 부모는**-**자식 열에서는 되지 않는 기본 키/외래 키 제약 조건을 지정할 때와 동일한 관계를 지정 합니다.  
  
## <a name="msdatarelationship-annotation"></a>msdata:Relationship 주석  
 **msdata: relationship** 주석 명시적으로 중첩 되지 않은 스키마의 요소 간의 부모-자식 관계를 지정할 수 있습니다. 다음 예제에서는의 구조는 **관계** 요소입니다.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 특성은 **msdata: relationship** 으로 부모-자식 관계에 관련 된 요소를 식별 하는 주석에서 **parentkey** 및 **childkey** 요소 및 특성 관계를 맺고 있습니다. 매핑 프로세스에서는이 정보를 사용 하 여 테이블에서 생성 하는 **데이터 집합** 고 이러한 테이블 간에 기본 키/외래 키 관계를 만들 수 있습니다.  
  
 예를 들어 다음 스키마 조각 지정 **순서** 및 **OrderDetail** 동일한 수준에 있는 요소 (안에 있는 경우). 스키마 지정는 **msdata: relationship** 주석으로,이 두 요소 간의 부모-자식 관계를 지정 합니다. 사용 하 여 명시적 관계를 지정 해야이 경우에 **msdata: relationship** 주석입니다.  
  
```xml  
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
  
 사용 하 여 매핑 프로세스는 **관계** 요소 간의 부모-자식 관계를 만들 수는 **OrderNumber** 열에는 **순서** 테이블과 **OrderNo** 열에는 **OrderDetail** 테이블에 **DataSet**합니다. 매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.  
  
### <a name="in-this-section"></a>단원 내용  
 [중첩 된 스키마 요소 간의 암시적 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 제약 조건 및에 암시적으로 만들어진 관계에 설명 된 **DataSet** 중첩 된 요소가 XML 스키마에서 발생 하는 경우.  
  
 [중첩 된 요소에 지정 된 관계 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 관계를 명시적으로 설정 하는 방법을 설명는 **DataSet** XML 스키마의 중첩 된 요소에 대 한 합니다.  
  
 [중첩 되지 않은 요소 사이 관계 지정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 관계를 만드는 방법에 설명 된 **데이터 집합** 중첩 되지 않은 XML 스키마 요소 간에 합니다.  
  
### <a name="related-sections"></a>관련 단원  
 [XML 스키마 (XSD)에서 데이터 집합 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 관계 구조 또는 스키마에 설명 된 **데이터 집합** XML 스키마 정의 언어 (XSD) 스키마에서 만들어집니다.  
  
 [데이터 집합 제약 조건에 XML 스키마 (XSD) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 고유 및 외래 키 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 설명 된 **DataSet**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
