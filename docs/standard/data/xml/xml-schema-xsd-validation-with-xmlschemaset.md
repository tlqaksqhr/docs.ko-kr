---
title: "XmlSchemaSet을 사용하여 XSD(XML 스키마) 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a6cf857ccecbdac88453fd1fba6e93d609196b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>XmlSchemaSet을 사용하여 XSD(XML 스키마) 유효성 검사
<xref:System.Xml.Schema.XmlSchemaSet>의 XSD(XML 스키마 정의 언어) 스키마에 대해 XML 문서의 유효성을 검사할 수 있습니다.  
  
## <a name="validating-xml-documents"></a>XML 문서 유효성 검사  
 <xref:System.Xml.XmlReader.Create%2A> 클래스의 <xref:System.Xml.XmlReader> 메서드를 사용하여 XML 문서의 유효성을 검사할 수 있습니다. XML 문서의 유효성을 검사하려면 XML 문서의 유효성을 검사하는 데 사용할 XSD(XML 스키마 정의 언어) 스키마가 포함된 <xref:System.Xml.XmlReaderSettings> 개체를 만듭니다.  
  
> [!NOTE]
>  <xref:System.Xml.Schema> 네임 스페이스에는 쉽게 사용 하는 경우 XSD 파일에 대해 XML 트리를 검사할 수 있도록 하는 확장 메서드가 포함 되어 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)합니다. LINQ to XML 사용 하 여 XML 문서 유효성 검사에 대 한 자세한 내용은 참조 하십시오. [하는 방법: XSD를 사용 하 여 유효성을 검사](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b)합니다.  
  
 개별 스키마 또는 스키마 집합(<xref:System.Xml.Schema.XmlSchemaSet>) 중 하나를 <xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드에 대한 매개 변수로 전달하여 개별 스키마 또는 스키마 집합을 <xref:System.Xml.Schema.XmlSchemaSet>에 추가할 수 있습니다. 문서 유효성을 확인할 때 문서의 대상 네임스페이스는 스키마 집합에 있는 스키마의 대상 네임스페이스와 일치해야 합니다.  
  
 다음은 XML 문서 예제입니다.  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 다음은 XML 문서 예제의 유효성을 검사하는 스키마입니다.  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 다음 코드 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet> 개체의 <xref:System.Xml.XmlReaderSettings.Schemas%2A><xref:System.Xml.XmlReaderSettings> 속성에 위 스키마가 추가됩니다. 위 XML 문서의 유효성을 검사하는 <xref:System.Xml.XmlReaderSettings> 개체의 <xref:System.Xml.XmlReader.Create%2A> 메서드에 <xref:System.Xml.XmlReader> 개체가 매개 변수로 전달됩니다.  
  
 <xref:System.Xml.XmlReaderSettings.ValidationType%2A> 개체의 <xref:System.Xml.XmlReaderSettings> 메서드에 의해 XML 문서의 유효성이 검사되도록 `Schema` 개체의 <xref:System.Xml.XmlReader.Create%2A> 속성이 <xref:System.Xml.XmlReader>로 설정됩니다. <xref:System.Xml.Schema.ValidationEventHandler>가 <xref:System.Xml.XmlReaderSettings> 개체에 추가되어 XML 문서와 스키마의 유효성을 검사하는 동안 발견된 오류로 인해 발생한 <xref:System.Xml.Schema.XmlSeverityType.Warning> 또는 <xref:System.Xml.Schema.XmlSeverityType.Error> 이벤트를 처리합니다.  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [스키마 컴파일 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [XML 스키마 사용](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
