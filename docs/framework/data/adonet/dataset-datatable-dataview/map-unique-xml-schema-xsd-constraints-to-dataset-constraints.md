---
title: "DataSet 제약 조건에 unique XSD(XML 스키마) 제약 조건 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 제약 조건에 unique XSD(XML 스키마) 제약 조건 매핑
XSD\(XML 스키마 정의 언어\) 스키마에서 **unique** 요소는 요소나 특성에 대한 고유성 제약 조건을 지정합니다.  XML 스키마를 관계형 스키마로 변환하는 과정에서, XML 스키마의 요소나 특성에 지정된 UNIQUE 제약 조건은 생성된 해당 <xref:System.Data.DataSet>에 있는 <xref:System.Data.DataTable>의 UNIQUE 제약 조건에 매핑됩니다.  
  
 다음 표에서는 **unique** 요소에 지정할 수 있는 **msdata** 특성에 대해 간략히 설명합니다.  
  
|특성 이름|설명|  
|-----------|--------|  
|**msdata:ConstraintName**|이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.  그렇지 않으면 **name** 특성에서 제약 조건 이름의 값을 제공합니다.|  
|**msdata:PrimaryKey**|**unique** 요소에 `PrimaryKey="true"`가 있으면 **IsPrimaryKey** 속성이 **true**로 설정된 UNIQUE 제약 조건이 만들어집니다.|  
  
 다음 예제에서는 **unique** 요소를 사용하여 고유성 제약 조건을 지정하는 XML 스키마를 보여 줍니다.  
  
```  
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
   <xs:unique      
msdata:ConstraintName="UCustID"      
name="UniqueCustIDConstr" >        
<xs:selector xpath=".//Customers" />        
<xs:field xpath="CustomerID" />      
</xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 스키마의 **unique** 요소는 문서 인스턴스의 모든 **Customers** 요소에 대해 해당 **CustomerID** 자식 요소의 값이 고유하도록 지정합니다.  **DataSet**을 빌드하면 매핑 프로세스에서는 해당 스키마를 읽고 다음 테이블을 생성합니다.  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 또한 매핑 프로세스에서는 다음 **DataSet**에서처럼 **CustomerID** 열에 대해 UNIQUE 제약 조건을 만듭니다.  여기에서는 편의를 위해 관련 속성만 보여 줍니다.  
  
```  
  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID  
      Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 생성된 **DataSet**에서 UNIQUE 제약 조건을 위해 **IsPrimaryKey** 속성을 **False**로 설정됩니다.  열의 **unique** 속성은 **CustomerID** 열 값이 고유해야 함을  나타냅니다. 그러나 열의 **AllowDBNull** 속성에 지정된 것처럼 이 값은 null 참조가 될 수 있습니다.  
  
 스키마를 수정하고 선택적인 **msdata:PrimaryKey** 특성 값을 **True**로 설정하면 테이블에 UNIQUE 제약 조건이 만들어집니다.  **AllowDBNull** 열 속성은 **False**로 설정되고 제약 조건의 **IsPrimaryKey** 속성은 **True**로 설정되므로 **CustomerID** 열이 기본 키 열이 됩니다.  
  
 XML 스키마의 요소나 특성의 조합에 UNIQUE 제약 조건을 지정할 수 있습니다.  다음 예제에서는 스키마에 다른 **xs:field** 요소를 추가하여 **CustomerID**와 **CompanyName** 값의 조합이 임의의 인스턴스의 모든 **Customers**에 대해 고유하도록 지정하는 방법을 설명합니다.  
  
```  
  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 이것은 결과 **DataSet**에 만들어진 제약 조건입니다.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## 참고 항목  
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)