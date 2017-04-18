---
title: "XML 문서에서 스키마 유추 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# XML 문서에서 스키마 유추
이 항목에서는 <xref:System.Xml.Schema.XmlSchemaInference> 클래스를 사용하여 XML 문서 구조에서 XSD\(XML 스키마 정의 언어\) 스키마를 유추하는 방법을 설명합니다.  
  
## 스키마 유추 과정  
 <xref:System.Xml.Schema?displayProperty=fullName> 네임스페이스의 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 XML 문서 구조에서 XSD\(XML 스키마 정의 언어\) 스키마를 하나 이상 생성하는 데 사용됩니다.  생성된 스키마는 원래 XML 문서의 유효성을 검사하는 데 사용될 수 있습니다.  
  
 <xref:System.Xml.Schema.XmlSchemaInference> 클래스에서 XML 문서를 처리할 때 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 XML 문서의 요소와 특성을 설명하는 스키마 구성 요소에 대해 가정합니다.  또한 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 특정 요소 또는 특성에 대해 가장 제한적인 형식을 유추함으로써 제약된 방식으로 스키마 구성 요소를 유추합니다.  XML 문서에 대한 상세한 정보가 수집되면 이 제약 조건은 덜 제한적인 형식을 유추하여 완화됩니다.  유추되는 형식 중 가장 제한이 적은 형식은 `xs:string`입니다.  
  
 다음 XML 문서의 일부를 예로 들 수 있습니다.  
  
```  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A">  
```  
  
 위의 예제에서 `attribute1` 특성이 <xref:System.Xml.Schema.XmlSchemaInference> 프로세스에 의해 값 `6`을 발견하면 `xs:unsignedByte` 형식으로 간주됩니다.  <xref:System.Xml.Schema.XmlSchemaInference> 프로세스가 두 번째 `parent` 요소를 발견하면 해당 `attribute1` 특성 값이 `A`이므로 `xs:string` 형식으로 수정하여 제약 조건을 완화합니다.  마찬가지로 스키마에서 유추되는 모든 `child` 요소의 `minOccurs` 특성은 두 번째 부모 요소에 자식 요소가 없기 때문에 `minOccurs="0"`으로 완화됩니다.  
  
## XML 문서에서 스키마 유추  
 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 오버로드된 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드 두 개를 사용하여 XML 문서에서 스키마를 유추합니다.  
  
 첫 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=fullName> 메서드는 XML 문서를 기반으로 스키마를 만드는 데 사용됩니다.  두 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=fullName> 메서드는 여러 XML 문서를 설명하는 스키마를 유추하는 데 사용됩니다.  예를 들어, 여러 XML 문서를 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=fullName> 메서드에 한 번에 하나씩 공급하여 전체 XML 문서 집합을 설명하는 스키마를 만들 수 있습니다.  
  
 첫 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=fullName> 메서드는 <xref:System.Xml.XmlReader> 개체에 들어 있는 XML 문서에서 스키마를 유추하고 유추된 스키마가 들어 있는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반환합니다.  두 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=fullName> 메서드는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 검색하여 <xref:System.Xml.XmlReader> 개체에 들어 있는 XML 문서와 같은 대상 네임스페이스를 가진 스키마를 찾고 기존 스키마를 구체화한 다음 유추된 스키마가 들어 있는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반환합니다.  
  
 구체화된 스키마에 대한 변경 내용은 XML 문서에 나타나는 새로운 구조를 기반으로 합니다.  예를 들어, XML 문서를 살펴볼 때 발견한 데이터 형식에 대해 가정하고 이 가정을 기반으로 스키마를 만듭니다.  하지만 원래 가정과 다른 두 번째 유추 과정에서 데이터가 발견되면 스키마는 구체화됩니다.  다음 예제에서는 구체화 과정을 보여 줍니다.  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 이 예제에서는 다음 `item1.xml` 파일을 첫 번째 입력으로 사용합니다.  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 그런 다음 `item2.xml` 파일을 두 번째 입력으로 사용합니다.  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 첫 번째 XML 문서에서 `productID` 특성이 발견되면 `123456789` 값은 `xs:unsignedInt` 형식으로 간주됩니다.  하지만 두 번째 XML 문서를 읽고 `A53-246` 값이 있으면 더 이상 `xs:unsignedInt` 형식으로 간주되지 않습니다.  스키마가 구체화되고 `productID`의 형식이 `xs:string`으로 변경됩니다.  또한 두 번째 XML 문서에 `supplierID` 요소가 없기 때문에 `supplierID` 요소에 대한 `minOccurs` 특성이 `0`으로 설정됩니다.  
  
 다음은 첫 번째 XML 문서에서 유추된 스키마입니다.  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 다음은 첫 번째 XML 문서에서 유추되고 두 번째 XML 문서에서 구체화된 스키마입니다.  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## 인라인 스키마  
 <xref:System.Xml.Schema.XmlSchemaInference> 프로세스에서 인라인 XSD\(XML 스키마 정의 언어\) 스키마가 발견되면 <xref:System.Xml.Schema.XmlSchemaInferenceException>이 throw됩니다.  예를 들어, 다음 인라인 스키마는 <xref:System.Xml.Schema.XmlSchemaInferenceException>을 throw합니다.  
  
```  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## 구체화할 수 없는 스키마  
 구체화하고 예외를 throw할 형식이 지정될 경우 XSD\(XML 스키마 정의 언어\) 스키마 <xref:System.Xml.Schema.XmlSchemaInference> 프로세스에서 처리할 수 없는 W3C XML 스키마 구문이 있습니다.  최상위 compositor가 시퀀스가 아닌 복합 형식 등이 이에 해당됩니다.  SOM\(스키마 개체 모델\)에서 이 스키마는 <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> 속성이 <xref:System.Xml.Schema.XmlSchemaSequence>의 인스턴스가 아닌 <xref:System.Xml.Schema.XmlSchemaComplexType>에 해당합니다.  
  
## 참고 항목  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [XML SOM\(스키마 개체 모델\)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)   
 [XML 스키마 유추](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)   
 [스키마 노드 형식 및 구조 유추 규칙](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)   
 [단순 형식 유추 규칙](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)