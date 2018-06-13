---
title: 데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757868"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑
스키마에서는 요소에 대 한 key 제약 조건을 지정 하거나 사용 하 여 특성 수는 **키** 요소입니다. KEY 제약 조건이 지정된 요소 또는 특성은 모든 스키마 인스턴스에서 고유한 값을 가져야 하며 null 값을 가져서는 안 됩니다.  
  
 KEY 제약 조건이 정의된 열이 null 값을 가질 수 없다는 것을 제외하면, key 제약 조건은 UNIQUE 제약 조건과 유사합니다.  
  
 다음 표에서 윤곽선은 **msdata** 에서 지정할 수 있는 특성의 **키** 요소입니다.  
  
|특성 이름|설명|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다. 그렇지 않은 경우는 **이름** 특성에서 제약 조건 이름의 값을 제공 합니다.|  
|**msdata:PrimaryKey**|경우 `PrimaryKey="true"` 가 있으면는 **IsPrimaryKey** 제약 조건 속성이로 설정 되어 **true**, 있기 때문에 기본 키입니다. **AllowDBNull** 열 속성이로 설정 되어 **false**이므로 기본 키는 null 값을 가질 수 없습니다.|  
  
 Key 제약 조건을 지정 하는 스키마를 변환 매핑 프로세스에서는 포함 된 테이블에 unique 제약 조건을 만듭니다는 **AllowDBNull** 열 속성이로 설정 **false** 각 열에 제약 조건입니다. **IsPrimaryKey** unique 제약 조건의 속성이 **false** 지정 하기 전 까지는 `msdata:PrimaryKey="true"` 에 **키** 요소입니다. 이것은 `PrimaryKey="true"`인 스키마의 UNIQUE 제약 조건에도 마찬가지로 적용됩니다.  
  
 다음 스키마 예제에서는 **키** 요소에 키 제약 조건을 지정 된 **CustomerID** 요소입니다.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 **키** 요소를 지정 하는 값은 **CustomerID** 의 자식 요소는 **고객** 요소는 고유 값 이어야 하 고 null 값을 가질 수 없습니다. XSD(XML 스키마 정의 언어) 스키마를 변환할 때 매핑 프로세스에서는 다음 테이블을 만듭니다.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 XML 스키마 매핑도 만듭니다.는 **UniqueConstraint** 에 **CustomerID** 열에서 다음에 표시 된 대로 <xref:System.Data.DataSet>합니다. 여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 에 **데이터 집합** 생성 하는 **IsPrimaryKey** 의 속성에서 **UniqueConstraint** 로 설정 되어 **true** 때문에 스키마 지정 `msdata:PrimaryKey="true"` 에 **키** 요소입니다.  
  
 값은 **ConstraintName** 속성은 **UniqueConstraint** 에 **데이터 집합** 의 값이는 **msdata:ConstraintName** 에 지정 된 특성의 **키** 스키마의 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
