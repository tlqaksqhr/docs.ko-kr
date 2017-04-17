---
title: "열 유추 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 열 유추
ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.  ADO.NET 2.0에는 각 **simpleType** 요소에 대해 강력한 형식의 데이터 형식을 유추하는 새로운 스키마 유추 엔진이 추가되었습니다.  이전 버전에서 유추된 **simpleType** 요소의 데이터 형식은 항상 **xsd:string**이었습니다.  
  
## 마이그레이션 및 이전 버전과의 호환성  
 **ReadXml** 메서드는 **InferSchema** 형식의 인수를 사용합니다.  이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.  다음 표에서는 **InferSchema** 열거형에서 사용할 수 있는 값을 보여 줍니다.  
  
 <xref:System.Data.XmlReadMode>  
 항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.  
  
 <xref:System.Data.XmlReadMode>  
 강력한 형식의 데이터 형식을 유추합니다.  <xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.  
  
 <xref:System.Data.XmlReadMode>  
 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.  
  
## 특성  
 [테이블 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)에서 정의된 것처럼 특성이 있는 요소는 테이블로 유추됩니다.  그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.  열의 **ColumnMapping** 속성은 스키마를 다시 XML로 작성하는 경우 열 이름이 특성으로 작성되도록 **MappingType.Attribute**로 설정됩니다.  특성 값은 테이블의 행에 저장됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 위 유추 과정에서는 **attr1** 및 **attr2**라는 두 개의 열을 가진 **Element1**이라는 테이블이 생성됩니다.  두 열의 **ColumnMapping** 속성은 **MappingType.Attribute**로 설정됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## 특성이나 자식 요소가 없는 요소  
 요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.  해당 열의 **ColumnMapping** 속성은 **MappingType.Element**로 설정됩니다.  자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.  예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서는 **ChildElement1** 및 **ChildElement2**라는 두 개의 열을 가진 **Element1**이라는 테이블이 생성됩니다.  두 열의 **ColumnMapping** 속성은 **MappingType.Element**로 설정됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)