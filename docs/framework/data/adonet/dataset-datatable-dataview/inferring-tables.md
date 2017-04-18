---
title: "테이블 유추 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 테이블 유추
XML 문서로부터 <xref:System.Data.DataSet>의 스키마를 유추할 때 ADO.NET에서는 우선 테이블을 나타내는 XML 요소를 결정합니다.  다음 XML 구조는 **DataSet** 스키마의 테이블이 됩니다.  
  
-   특성이 있는 요소  
  
-   자식 요소가 있는 요소  
  
-   반복되는 요소  
  
## 특성이 있는 요소  
 자신에 지정된 특성을 갖고 있는 요소는 유추된 테이블이 됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## 자식 요소가 있는 요소  
 자식 요소를 갖고 있는 요소는 유추된 테이블이 됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 문서 요소 또는 루트 요소는 열로 유추되는 특성이나 자식 요소를 갖고 있는 경우 유추된 테이블이 됩니다.  문서 요소에 열로 유추되는 특성이나 자식 요소가 없으면 문서 요소는 **DataSet**으로 유추됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "DocumentElement"라는 테이블이 생성됩니다.  
  
 **DataSet:** NewDataSet  
  
 **Table:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 또는 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 포함된 "DocumentElement"라는 **DataSet**이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## 반복되는 요소  
 반복되는 요소는 하나의 유추된 테이블이 됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)