---
title: 관계 유추
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 9833966fa5a16bef70a6ae2b9ca618fde0e05fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759038"
---
# <a name="inferring-relationships"></a>관계 유추
테이블로 유추되는 요소에 역시 테이블로 유추되는 자식 요소가 있으면 두 테이블 사이에 <xref:System.Data.DataRelation>이 만들어집니다. 이름으로 새 열 **ParentTableName_Id** 부모 요소에 대해 생성 된 테이블 및 자식 요소에 대해 생성 된 테이블 모두에 추가 됩니다. **ColumnMapping** id 열 속성으로 설정 됩니다 **MappingType.Hidden**합니다. 열을 부모 테이블에 대 한 자동 증분 기본 키 되며에 사용할는 **DataRelation** 두 테이블 사이입니다. 추가 된 id 열의 데이터 형식은 **System.Int32**, 다른 모든 유추 된 열의 데이터 형식, 달리 **System.String**합니다. A <xref:System.Data.ForeignKeyConstraint> 와 **DeleteRule** = **Cascade** 도 새 열을 사용 하 여 부모 및 자식 테이블에 생성 됩니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 두 개의 테이블이 생성 됩니다: **Element1** 및 **ChildElement1**합니다.  
  
 **Element1** 테이블 두 개의 열이 포함 됩니다. **Element1_Id** 및 **ChildElement2**합니다. **ColumnMapping** 의 속성은 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다. **ColumnMapping** 의 속성은 **ChildElement2** 열으로 설정 됩니다 **MappingType.Element**합니다. **Element1_Id** 의 기본 키로 열을 설정할 수는 **Element1** 테이블입니다.  
  
 **ChildElement1** 테이블 3 개의 열이 포함 됩니다. **attr1**, **attr2** 및 **Element1_Id**합니다. **ColumnMapping** 속성에 대 한는 **attr1** 및 **attr2** 열으로 설정 됩니다 **MappingType.Attribute**합니다. **ColumnMapping** 의 속성은 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다.  
  
 A **DataRelation** 및 **ForeignKeyConstraint** 를 사용 하 여 만들 수는 **Element1_Id** 모든 테이블의 열입니다.  
  
 **데이터 집합:** DocumentElement  
  
 **Table:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Table:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **중첩:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **열:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** 캐스케이드  
  
 **AcceptRejectRule:** 없음  
  
## <a name="see-also"></a>참고 항목  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [DataRelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
