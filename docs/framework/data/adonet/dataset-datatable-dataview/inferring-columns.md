---
title: "열 유추"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 858a23fb8fec7b7f2eee95a1365d16e846beb548
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-columns"></a>열 유추
ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다. ADO.NET 2.0에는 각각에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 **simpleType** 요소입니다. 유추 된 데이터 형식이 이전 버전에서는 **simpleType** 요소가 항상 **xsd: string**합니다.  
  
## <a name="migration-and-backward-compatibility"></a>마이그레이션 및 이전 버전과의 호환성  
 **ReadXml** 형식의 인수를 사용 하는 메서드 **InferSchema**합니다. 이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다. 에 대 한 사용 가능한 값은 **InferSchema** 열거형 다음 표에 나와 있습니다.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 강력한 형식의 데이터 형식을 유추합니다. <xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.  
  
## <a name="attributes"></a>특성  
 에 정의 된 대로 [테이블 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), 특성이 있는 요소는 테이블로 유추 됩니다. 그러면 해당 요소의 특성은 테이블의 열로 유추됩니다. **ColumnMapping** 열의 속성을로 설정 됩니다 **MappingType.Attribute**, 스키마가 XML에 다시 기록 하는 경우 열 이름이 특성으로 작성 되도록 되도록 합니다. 특성 값은 테이블의 행에 저장됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열이 있는 **attr1** 및 **attr2**합니다. **ColumnMapping** 두 열 모두의 속성으로 설정 됩니다 **MappingType.Attribute**합니다.  
  
 **데이터 집합:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>특성이나 자식 요소가 없는 요소  
 요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다. **ColumnMapping** 열의 속성이로 설정 됩니다 **MappingType.Element**합니다. 자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열이 있는 **ChildElement1** 및 **ChildElement2**합니다. **ColumnMapping** 두 열 모두의 속성으로 설정 됩니다 **MappingType.Element**합니다.  
  
 **데이터 집합:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>참고 항목  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
