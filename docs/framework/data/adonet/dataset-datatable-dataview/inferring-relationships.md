---
title: "관계 유추 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 관계 유추
테이블로 유추되는 요소에 역시 테이블로 유추되는 자식 요소가 있으면 두 테이블 사이에 <xref:System.Data.DataRelation>이 만들어집니다.  **ParentTableName\_Id**라는 이름의 새 열이 부모 요소에 대해 만들어진 테이블과 자식 요소에 대해 만들어진 테이블에 모두 추가됩니다.  이 ID 열의 **ColumnMapping** 속성은 **MappingType.Hidden**으로 설정됩니다.  이 열은 부모 테이블에 대한 자동 증분 기본 키가 되며 두 테이블 사이의 **DataRelation**에 사용됩니다.  추가된 ID 열의 데이터 형식은 다른 모든 유추된 열의 데이터 형식인 **System.String**과는 달리 **System.Int32**가 됩니다.  부모 및 자식 테이블에 모두 포함된 새 열을 사용하여 **DeleteRule** \= **Cascade**인 <xref:System.Data.ForeignKeyConstraint>도 만들어집니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 **Element1** 및 **ChildElement1**이라는 두 개의 테이블이 생성됩니다.  
  
 **Element1** 테이블에는 **Element1\_Id** 및 **ChildElement2**라는 두 개의 열이 포함됩니다.  **Element1\_Id** 열의 **ColumnMapping** 속성은 **MappingType.Hidden**으로 설정됩니다.  **ChildElement2** 열의 **ColumnMapping** 속성은 **MappingType.Element**로 설정됩니다.  **Element1\_Id** 열은 **Element1** 테이블의 기본 키로 설정됩니다.  
  
 **ChildElement1** 테이블에는 **attr1**, **attr2** 및 **Element1\_Id**라는 세 개의 열이 포함됩니다.  **attr1** 및 **attr2**열의 **ColumnMapping** 속성은 **MappingType.Attribute**로 설정됩니다.  **Element1\_Id** 열의 **ColumnMapping** 속성은 **MappingType.Hidden**으로 설정됩니다.  
  
 **DataRelation** 및 **ForeignKeyConstraint**는 두 테이블의 **Element1\_Id** 열을 사용하여 만들어집니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Table:** ChildElement1  
  
|attr1|attr2|Element1\_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1\_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1\_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1\_Id  
  
 **Nested:** True  
  
 **ForeignKeyConstraint:** Element1\_ChildElement1  
  
 **Column:** Element1\_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataRelations 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)