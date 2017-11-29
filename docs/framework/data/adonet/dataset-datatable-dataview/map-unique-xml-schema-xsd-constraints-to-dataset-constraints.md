---
title: "데이터 집합 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66183768b5b48608dc69a4021b27816595c43b4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑
XML 스키마 정의 언어 (XSD) 스키마에는 **고유** 요소는 요소나 특성에 고유성 제약 조건을 지정 합니다. XML 스키마를 관계형 스키마로 변환하는 과정에서, XML 스키마의 요소나 특성에 지정된 UNIQUE 제약 조건은 생성된 해당 <xref:System.Data.DataTable>에 있는 <xref:System.Data.DataSet>의 UNIQUE 제약 조건에 매핑됩니다.  
  
 다음 표에서 윤곽선은 **msdata** 에서 지정할 수 있는 특성의 **고유** 요소입니다.  
  
|특성 이름|설명|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다. 그렇지 않은 경우는 **이름** 특성에서 제약 조건 이름의 값을 제공 합니다.|  
|**msdata: primarykey**|경우 `PrimaryKey="true"` 에 **고유** , unique 제약 조건을 사용 요소가 만들어집니다는 **IsPrimaryKey** 속성이로 설정 **true**합니다.|  
  
 다음 예제에서는 사용 하는 XML 스키마는 **고유** 고유성 제약 조건을 지정 하는 요소입니다.  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 **고유** 스키마 요소에에서 지정 하는 모든 **고객** 인스턴스 문서에서 요소를 값은 **CustomerID** 자식 요소가 고유 해야 합니다. 건물 안에 **DataSet**, 매핑 프로세스에서는이 스키마를 읽고 다음 테이블을 생성 합니다.  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 매핑 프로세스에서 unique 제약 조건을 만듭니다는 **CustomerID** 열에서 다음에 표시 된 대로 **DataSet**합니다. 여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 에 **데이터 집합** 생성 하는 **IsPrimaryKey** 속성이 **False** unique 제약 조건에 대 한 합니다. **고유** 나타내는 속성에는 **CustomerID** 열 값은 고유 해야 합니다. (에 지정 된 대로 null 참조일 수 있습니다 하지만 **AllowDBNull** 열 속성)입니다.  
  
 스키마를 수정 하 고 선택 사항인 경우 **msdata: primarykey** 특성 값을 **True**, 테이블에 unique 제약 조건이 만들어집니다. **AllowDBNull** 열 속성이로 설정 되어 **False**, 및 **IsPrimaryKey** 속성으로 설정 하는 제약 조건의 **True**되므로, **CustomerID** 열 기본 키 열입니다.  
  
 XML 스키마의 요소나 특성의 조합에 UNIQUE 제약 조건을 지정할 수 있습니다. 다음 예제에서는의 조합을 지정 하는 방법을 보여 줍니다 **CustomerID** 및 **CompanyName** 값 모두에 대해 고유 해야 합니다. **고객** 모든 인스턴스에서 하 여 다른 추가 **xs:field** 스키마의 요소입니다.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 이 결과에서 생성 된 제약 조건 **DataSet**합니다.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합 제약 조건에 XML 스키마 (XSD) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [XML 스키마 (XSD)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
