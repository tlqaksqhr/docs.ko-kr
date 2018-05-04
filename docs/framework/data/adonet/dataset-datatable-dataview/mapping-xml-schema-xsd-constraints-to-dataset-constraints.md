---
title: 데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: 0a23e7a7ab6456125559ffd8fa19ffa5eba9335d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑
XSD(XML 스키마 정의 언어)를 사용하여 요소와 특성에서 제약 조건을 지정할 수 있습니다. XML 스키마에서 관계형 스키마에 매핑하는 경우는 <xref:System.Data.DataSet>, XML 스키마 제약 조건을 테이블 및 열 내에서 적절 한 관계형 제약 조건에 매핑되는 **데이터 집합**합니다.  
  
 이 단원에서는 다음 XML 스키마 제약 조건의 매핑에 대해 설명합니다.  
  
-   고유성 제약 조건을 사용 하 여 지정 된 **고유** 요소입니다.  
  
-   사용 하 여 지정 된 키 제약 조건에서 **키** 요소입니다.  
  
-   Keyref 제약 조건을 사용 하 여 지정 된 **keyref** 요소입니다.  
  
 요소나 특성에서 제약 조건을 사용하여 문서의 모든 인스턴스에서 요소의 값에 특정 제한 사항을 지정할 수 있습니다. 에 키 제약 조건을 예를 들어는 **CustomerID** 의 자식 요소는 **고객** 스키마 요소에에서 나타냅니다의 값은 **CustomerID** 자식 요소 여야 합니다 모든 문서 인스턴스에서 고유 있으며 null 값이 허용 되지 않습니다.  
  
 또한 문서 내에서 관계를 설정하도록 문서의 요소와 특성 사이에 제약 조건을 지정할 수 있습니다. KEY 및 KEYREF 제약 조건은 스키마에서 사용되어 문서 내에서의 제약 조건을 지정함으로써 결과적으로 문서 요소와 특성 간의 관계를 설정합니다.  
  
 매핑 프로세스 내에서 만든 테이블에 적절 한 제약 조건으로 이러한 스키마 제약 조건을 변환에서 **DataSet**합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 집합 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 unique 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 설명 된 **DataSet**합니다.  
  
 [데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 (고유 제약 조건 null 값은 허용 되지) 키 제약 조건을 만드는 데 사용 되는 XML 스키마 요소에 설명 된 **DataSet**합니다.  
  
 [데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Keyref (외래 키) 제약 조건을 만드는 데 XML 스키마 요소에 설명 된 **DataSet**합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 관계 구조 또는 스키마에 설명 된 **데이터 집합** XSD 스키마에서 만들어집니다.  
  
 [XSD(XML 스키마)에서 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 여러 테이블 열 사이의 관계를 만드는 사용 되는 XML 스키마 요소에 설명 된 **DataSet**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
