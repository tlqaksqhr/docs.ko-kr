---
title: "DataSet 제약 조건에 XSD(XML 스키마) 제약 조건 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 제약 조건에 XSD(XML 스키마) 제약 조건 매핑
XSD\(XML 스키마 정의 언어\)를 사용하여 요소와 특성에서 제약 조건을 지정할 수 있습니다.  XML 스키마를 <xref:System.Data.DataSet>의 관계형 스키마에 매핑하면, XML 스키마 제약 조건이 **DataSet** 내에 있는 테이블과 열에 대한 적절한 관계형 제약 조건으로 매핑됩니다.  
  
 이 단원에서는 다음 XML 스키마 제약 조건의 매핑에 대해 설명합니다.  
  
-   **unique** 요소를 사용하여 지정된 고유성 제약 조건  
  
-   **key** 요소를 사용하여 지정된 KEY 제약 조건  
  
-   **keyref** 요소를 사용하여 지정된 KEYREF 제약 조건  
  
 요소나 특성에서 제약 조건을 사용하여 문서의 모든 인스턴스에서 요소의 값에 특정 제한 사항을 지정할 수 있습니다.  예를 들어, 스키마에서 **Customer** 요소의 **CustomerID** 자식 요소에 대한 KEY 제약 조건은 **CustomerID** 자식 요소의 값이 모든 문서 인스턴스에서 고유해야 하며 null 값이 허용되지 않음을 나타냅니다.  
  
 또한 문서 내에서 관계를 설정하도록 문서의 요소와 특성 사이에 제약 조건을 지정할 수 있습니다.  KEY 및 KEYREF 제약 조건은 스키마에서 사용되어 문서 내에서의 제약 조건을 지정함으로써 결과적으로 문서 요소와 특성 간의 관계를 설정합니다.  
  
 매핑 프로세스에서는 이러한 스키마 제약 조건을 **DataSet** 내에 만들어진 테이블에 대한 적절한 제약 조건으로 변환합니다.  
  
## 단원 내용  
 [DataSet 제약 조건에 unique XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet**에서 UNIQUE 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
 [DataSet 제약 조건에 key XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet**에서 KEY 제약 조건\(null 값이 허용되지 않는 UNIQUE 제약 조건\)을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
 [DataSet 제약 조건에 keyref XSD\(XML 스키마\) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 **DataSet**에서 KEYREF\(외래 키\) 제약 조건을 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
## 관련 단원  
 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 XSD 스키마에서 만들어지는 **DataSet**의 관계 구조 또는 스키마에 대해 설명합니다.  
  
 [XSD\(XML 스키마\)에서 DataSet 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 **DataSet**에서 여러 테이블 열 사이의 관계를 만드는 데 사용되는 XML 스키마 요소에 대해 설명합니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)