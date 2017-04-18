---
title: "유추 제한 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 유추 제한 사항
XML에서 <xref:System.Data.DataSet> 스키마를 유추하는 과정을 통해 만들어지는 스키마는 각 문서의 XML 요소에 따라 다를 수 있습니다.  예를 들어, 다음과 같은 XML 문서를 가정해 봅시다.  
  
 Document1:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 "Document1"의 경우 "Element1"이 반복되는 요소이므로 유추 과정에서 "DocumentElement"라는 **DataSet**과 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 그러나 "Document2"의 경우에는 유추 과정에서 "NewDataSet"이라는 **DataSet**과 "DocumentElement"라는 테이블이 생성됩니다. "Element1"은 특성이나 자식 요소가 없으므로 열로 유추됩니다.  
  
 **DataSet:** NewDataSet  
  
 **Table:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 이러한 두 XML 문서는 동일한 스키마를 생성하려는 의도로 만들어졌겠지만, 각 문서에 포함된 요소에 따라 유추 과정의 결과가 크게 달라졌습니다.  
  
 XML 문서에서 스키마를 생성할 때 발생할 수 있는 이러한 차이를 방지하려면 XML에서 **DataSet**을 로드할 때 XSD\(XML 스키마 정의 언어\)나 XDR\(XML\-Data Reduced\)을 사용하여 스키마를 명시적으로 지정하는 것이 좋습니다.  XML 스키마로 **DataSet** 스키마를 명시적으로 지정하는 방법에 대한 자세한 내용은 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조하세요.  
  
## 참고 항목  
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)