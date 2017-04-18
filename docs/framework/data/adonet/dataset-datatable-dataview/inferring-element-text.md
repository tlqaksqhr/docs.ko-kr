---
title: "요소 텍스트 유추 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 요소 텍스트 유추
텍스트는 있지만 테이블로 유추될 자식 요소가 없는 요소 즉, 특성이나 반복되는 요소가 있는 요소의 경우에는 **TableName\_Text**라는 새 열이 해당 요소의 유추 테이블에 추가됩니다.  이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다.  새 열의 **ColumnMapping** 속성은 **MappingType.SimpleContent**로 설정됩니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 이 유추 프로세스에서는 **attr1** 및 **Element1\_Text**라는 두 개의 열이 있는 **Element1**이라는 테이블이 생성됩니다.  **attr1** 열의 **ColumnMapping** 속성은 **MappingType.Attribute**로 설정됩니다.  **Element1\_Text** 열의 **ColumnMapping** 속성은 **MappingType.SimpleContent**로 설정됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다.  따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 위 유추 과정에서 **ChildElement1**이라는 열이 하나 있는 **Element1**이라는 테이블이 생성됩니다.  **ChildElement1** 요소의 텍스트는 해당 테이블의 행에 포함됩니다.  다른 텍스트는 무시됩니다.  **ChildElement1** 열의 **ColumnMapping** 속성은 **MappingType.Element**로 설정됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)