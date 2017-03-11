---
title: "XML Value Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Value property [Visual Basic]"
  - "Visual Basic code, accessing XML"
  - "XML axis [Visual Basic], Value"
  - "XML Value property [Visual Basic]"
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# XML Value Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 첫 번째 요소의 값에 대한 액세스를 제공합니다.  
  
## 구문  
  
```  
  
object.Value  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`object`|필수 요소.  <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.|  
  
## 반환 값  
 컬렉션의 첫 번째 요소 값을 포함하는 `String` 또는 컬렉션이 비어 있는 경우 `Nothing`입니다.  
  
## 설명  
 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하면 <xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 첫 번째 요소의 값에 쉽게 액세스할 수 있습니다.  이 속성은 먼저 컬렉션에 적어도 하나의 개체가 포함되어 있는지 여부를 확인합니다.  컬렉션이 비어 있으면 이 속성은 `Nothing`을 반환합니다.  그렇지 않으면 이 속성은 컬렉션에 있는 첫 번째 요소의 <xref:System.Xml.Linq.XElement.Value%2A> 속성 값을 반환합니다.  
  
> [!NOTE]
>  '@' 식별자를 사용하여 XML 특성 값에 액세스하는 경우 특성 값은 `String`으로 반환되며 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 명시적으로 지정할 필요가 없습니다.  
  
 컬렉션의 다른 요소에 액세스하려면 요소에 XML 확장 인덱서 속성을 사용할 수 있습니다.  자세한 내용은 [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)를 참조하십시오.  
  
## 상속  
 대부분의 사용자는 <xref:System.Collections.Generic.IEnumerable%601>을 구현할 필요가 없으므로 이 단원을 무시해도 됩니다.  
  
 <xref:System.Xml.Linq.XElement.Value%2A> 속성은 `IEnumerable(Of XElement)`을 구현하는 형식의 확장 속성입니다.  이 확장 속성의 바인딩은 확장 메서드의 바인딩과 같습니다. 형식에서 인터페이스 중 하나를 구현하고 이름이 "Value"인 속성을 정의하는 경우 해당 속성이 확장 속성보다 우선합니다.  즉, `IEnumerable(Of XElement)`을 구현하는 클래스에서 새 속성을 정의하여 이 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 재정의할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하여 <xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 첫 번째 노드에 액세스하는 방법을 보여 줍니다.  이 예제에서는 자식 축 속성을 사용하여 `contact` 개체에 있는 `phone`이라는 모든 자식 노드의 컬렉션을 가져옵니다.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-value-property_1.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Phone number: 206-555-0144`  
  
## 예제  
 다음 예제에서는 <xref:System.Xml.Linq.XAttribute> 개체의 컬렉션에서 XML 특성 값을 가져오는 방법을 보여 줍니다.  이 예제에서는 특성 축 속성을 사용하여 모든 `phone` 요소의 `type` 특성 값을 표시합니다.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-value-property_2.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `home`  
  
 `work`  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)   
 [XML Child Axis Property](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [XML Attribute Axis Property](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)