---
title: "DataSet 스키마 유추 과정에 대한 요약 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 스키마 유추 과정에 대한 요약
유추 과정에서는 우선 XML 문서에서 테이블로 유추될 요소를 결정합니다.  그런 다음 남아 있는 XML에서 해당 테이블의 열을 결정합니다.  중첩된 테이블인 경우에는 유추 과정에서 중첩된 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체를 생성합니다.  
  
 다음은 유추 규칙에 대해 간략히 요약한 것입니다.  
  
-   특성이 있는 요소는 테이블로 유추됩니다.  
  
-   자식 요소가 있는 요소는 테이블로 유추됩니다.  
  
-   반복되는 요소는 하나의 테이블로 유추됩니다.  
  
-   문서 요소에 열로 유추되는 특성이나 자식 요소가 없으면 문서 요소 또는 루트 요소는 <xref:System.Data.DataSet>으로 유추됩니다.  그렇지 않으면 문서 요소는 테이블로 유추됩니다.  
  
-   특성은 열로 유추됩니다.  
  
-   특성이나 자식 요소가 없거나 반복되지 않는 요소는 열로 유추됩니다.  
  
-   테이블로 유추되는 다른 요소 내에 중첩된 테이블로 유추되는 요소인 경우 중첩된 **DataRelation**이 두 테이블 사이에 만들어집니다.  **TableName\_Id**라는 새로운 기본 키 열이 두 테이블에 모두 추가되어 **DataRelation**에서 사용됩니다.  **TableName\_Id** 열을 사용하여 **ForeignKeyConstraint**가 두 테이블 사이에 만들어집니다.  
  
-   테이블로 유추되고 텍스트를 포함하지만 자식 요소가 없는 요소인 경우 각 요소의 텍스트에 대해 **TableName\_Text**라는 새 열이 만들어집니다.  테이블로 유추되는 요소에 텍스트와 자식 요소가 모두 있으면 해당 텍스트는 무시됩니다.  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)