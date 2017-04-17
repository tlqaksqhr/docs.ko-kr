---
title: "XSD(XML 스키마)에서 DataSet 관계형 구조 파생 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# XSD(XML 스키마)에서 DataSet 관계형 구조 파생
이 단원에서는 XSD\(XML 스키마 정의 언어\) 스키마 문서에서 <xref:System.Data.DataSet>의 관계형 스키마를 빌드하는 방법을 간략하게 설명합니다.  일반적으로 스키마 요소의 각 **complexType** 자식 요소에 대해 **DataSet**에 하나의 테이블이 생성됩니다.  테이블 구조는 복합 형식의 정의에 의해 결정됩니다.  테이블은 스키마에 있는 최상위 요소의 **DataSet**에 만들어집니다.  그러나 **complexType** 요소가 다른 **complexType** 요소 내부에 중첩되었을 경우에는 최상위 **complexType** 요소에 대해서만 테이블이 만들어지며, 이 경우 중첩된 **complexType** 요소는 **DataSet** 내의 <xref:System.Data.DataTable>에 매핑됩니다.  
  
 XSD에 대한 자세한 내용은 [http:\/\/www.w3.org\/](http://www.w3.org/TR/)\(영문\)에 있는 W3C\(World Wide Web 컨소시엄\) XML 스키마 0부: 프라이머 권장 사항, XML 스키마 1부: 구조 권장 사항 및 XML 스키마 2부: 데이터 형식 권장 사항을 참조하세요.  
  
 다음 예제에서는 `MyDataSet` 요소가 **DataSet** 요소일 경우 `customers`가 이 요소의 자식 요소인 XML 스키마를 보여 줍니다.  
  
```  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 앞의 예제에서 `customers` 요소는 복합 형식 요소입니다.  따라서 복합 형식 정의가 구문 분석되고 매핑 프로세스에서는 다음 테이블을 만듭니다.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 테이블의 각 열에 대한 데이터 형식은 지정된 해당 요소 또는 특성의 XML 스키마 형식에서 파생됩니다.  
  
> [!NOTE]
>  `customers` 요소가 **integer**와 같은 단순 XML 스키마 데이터 형식인 경우에는 테이블이 생성되지 않습니다.  테이블은 복합 형식인 최상위 요소에 대해서만 만들어집니다.  
  
 다음 XML 스키마에서 **Schema** 요소에는 `InStateCustomers` 및 `OutOfStateCustomers` 등 두 개의 요소 자식이 포함되어 있습니다.  
  
```  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 `InStateCustomers` 및 `OutOfStateCustomers` 자식 요소는 모두 복합 형식 요소\(`customerType`\)입니다.  따라서 매핑 프로세스에서는 **DataSet**에 다음과 같은 두 개의 동일한 테이블을 생성합니다.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## 단원 내용  
 [DataSet 제약 조건에 XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet**에서 고유 및 외래 키 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 **DataSet**에서 여러 테이블 열 사이의 관계를 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
 [XML 스키마 제약 조건 및 관계](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 XML 스키마 요소를 사용하여 **DataSet**에서 제약 조건을 만들 때 암시적으로 관계가 만들어지는 방법을 설명합니다.  
  
## 관련 단원  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 **DataSet**에서 XML 데이터로 관계 구조와 데이터를 로드하고 보존하는 방법을 설명합니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)