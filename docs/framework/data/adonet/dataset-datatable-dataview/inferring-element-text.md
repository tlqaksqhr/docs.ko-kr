---
title: "요소 텍스트 유추"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 239c70ca0e7f8894b988f17d248b2e5b3b98bf6a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-element-text"></a>요소 텍스트 유추
요소 텍스트를 포함 하 고 테이블로 유추 될 (특성이 있는 요소) 또는 반복된 요소와 같은 이름의 새 열에 자식 요소가 없는 경우 **TableName_Text** 요소의 유추 테이블에 추가 됩니다. 이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다. **ColumnMapping** 새 열의 속성이로 설정 됩니다 **MappingType.SimpleContent**합니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 열이 두 개: **attr1** 및 **Element1_Text**합니다. **ColumnMapping** 의 속성은 **attr1** 열으로 설정 됩니다 **MappingType.Attribute**합니다. **ColumnMapping** 의 속성은 **Element1_Text** 열으로 설정 됩니다 **MappingType.SimpleContent**합니다.  
  
 **데이터 집합:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다. 따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 라는 열이 하나인 **ChildElement1**합니다. 에 대 한 텍스트는 **ChildElement1** 요소는 테이블의 행에 포함 됩니다. 다른 텍스트는 무시됩니다. **ColumnMapping** 의 속성은 **ChildElement1** 열으로 설정 됩니다 **MappingType.Element**합니다.  
  
 **데이터 집합:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>참고 항목  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
