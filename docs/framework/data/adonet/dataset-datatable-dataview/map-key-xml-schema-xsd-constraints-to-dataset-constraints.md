---
title: "DataSet 제약 조건에 key XSD(XML 스키마) 제약 조건 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 제약 조건에 key XSD(XML 스키마) 제약 조건 매핑
스키마에서 **key** 요소를 사용하여 요소나 특성에 key 제약 조건을 지정할 수 있습니다.  KEY 제약 조건이 지정된 요소 또는 특성은 모든 스키마 인스턴스에서 고유한 값을 가져야 하며 null 값을 가져서는 안 됩니다.  
  
 KEY 제약 조건이 정의된 열이 null 값을 가질 수 없다는 것을 제외하면, key 제약 조건은 UNIQUE 제약 조건과 유사합니다.  
  
 다음 표에서는 **key** 요소에 지정할 수 있는 **msdata** 특성에 대해 간략히 설명합니다.  
  
|특성 이름|설명|  
|-----------|--------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.  그렇지 않으면 **name** 특성에서 제약 조건 이름의 값을 제공합니다.|  
|**msdata:PrimaryKey**|`PrimaryKey="true"`가 있으면 **IsPrimaryKey** 제약 조건 속성이 **true**로 설정되므로 해당 요소가 기본 키가 됩니다.  기본 키는 null 값을 포함할 수 없기 때문에 **AllowDBNull** 열 속성은 **false**로 설정됩니다.|  
  
 KEY 제약 조건이 지정되어 있는 스키마를 변환할 때, 매핑 프로세스에서는 제약 조건의 각 열에 대해 **AllowDBNull** 열 속성을 **false**로 설정하면서 해당 테이블의 UNIQUE 제약 조건을 만듭니다.  **key** 요소에 `msdata:PrimaryKey="true"`를 지정하지 않은 경우에는 UNIQUE 제약 조건의 **IsPrimaryKey** 속성도 **false**로 설정됩니다.  이것은 `PrimaryKey="true"`인 스키마의 UNIQUE 제약 조건에도 마찬가지로 적용됩니다.  
  
 다음 스키마 예제에서 **key** 요소는 **CustomerID** 요소에 대한 KEY 제약 조건을 지정합니다.  
  
```  
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
  
 **key** 요소에서는 **Customers** 요소의 **CustomerID** 자식 요소 값이 고유한 값이고 null 값을 포함할 수 없도록 지정합니다.  XSD\(XML 스키마 정의 언어\) 스키마를 변환할 때 매핑 프로세스에서는 다음 테이블을 만듭니다.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 또한 XML 스키마 매핑에서는 다음 <xref:System.Data.DataSet>과 같이 **CustomerID** 열에 대해 **UniqueConstraint**를 만듭니다.  여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
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
  
 생성된 **DataSet**에서는 스키마에서 **key** 요소에 `msdata:PrimaryKey="true"`를 지정하기 때문에 **UniqueConstraint**의 **IsPrimaryKey** 속성이 **true**로 설정됩니다.  
  
 **DataSet**에서 **UniqueConstraint**의 **ConstraintName** 속성 값은 스키마의 **key** 요소에 지정된 **msdata:ConstraintName** 특성 값입니다.  
  
## 참고 항목  
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)