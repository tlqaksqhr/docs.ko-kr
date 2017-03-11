---
title: "XML IntelliSense in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, XML"
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# XML IntelliSense in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic 코드 편집기에는 XML 스키마에 정의된 요소에 대한 단어 완성 기능을 제공하는 XML용 IntelliSense 기능이 포함되어 있습니다.  프로젝트에 XSD\(XML 스키마 정의\) 파일을 포함하고 `Imports` 문을 사용하여 스키마의 대상 네임스페이스를 가져오는 경우 코드 편집기는 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XDocument> 개체에 대한 IntelliSense의 유효한 멤버 변수 목록에 XSD 스키마의 요소를 포함합니다.  다음 그림에서는 <xref:System.Xml.Linq.XElement> 개체에 대한 IntelliSense 멤버 목록을 보여 줍니다.  
  
 ![Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/media/xml-intellisense.png "XML\_Intellisense")  
XML IntelliSense  
  
## Visual Basic에서 XML IntelliSense 사용  
 Visual Basic에서 XML IntelliSense를 사용하려면 사용자의 Visual Basic 프로젝트에 XSD 스키마 파일을 포함해야 합니다.  또한 `Imports` 문을 사용하여 XSD 스키마의 대상 네임스페이스를 사용자의 코드 파일로 가져와야 합니다.  또는 Visual Basic 프로젝트 디자이너의 **참조** 페이지를 사용하여 대상 네임스페이스를 프로젝트 수준의 네임스페이스 목록에 추가할 수 있습니다.  예제를 보려면 [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)을 참조하십시오.  자세한 내용은 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 및 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)을 참조하십시오.  
  
 기본적으로 Visual Basic 프로젝트에서는 XSD 스키마 파일을 볼 수 없습니다.  프로젝트에 포함할 XSD 파일을 선택하려면 **모든 파일 표시** 단추를 클릭해야 합니다.  
  
### 스키마 파일 생성\(스키마 유추\)  
 Visual Studio XML 도구를 통해 XSD 스키마를 유추하여 기존 XML 파일에 대한 XSD 스키마를 만들 수 있습니다.  
  
-   SP1부터 XML to Schema 마법사를 사용하여 하나 이상의 XML 문서에서 유추한 XML 스키마 집합을 만들고 이 집합을 프로젝트에 포함할 수 있습니다.  텍스트 파일 형식의 XML 문서, HTTP 인터넷 주소의 XML 또는 XML to Schema 마법사에 입력하거나 붙여넣은 XML을 임의로 조합하여 사용할 수 있습니다.  XML to Schema 마법사에 액세스하려면 **프로젝트** 메뉴에서 **새 항목 추가**를 클릭하고 **데이터** 또는 **공통 항목** 템플릿 그룹에서 **Xml to Schema** 템플릿을 추가합니다.  XML 스키마 집합을 유추할 XML 문서 소스를 모두 포함했으면 **확인**을 클릭하여 유추한 XML 스키마 집합을 만듭니다.  자세한 내용은 [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)를 참조하십시오.  
  
-   또한 Visual Studio XML 편집기를 사용하여 XML 파일에서 XSD 스키마 집합을 유추할 수도 있습니다.  XML 편집기를 사용하여 XML 스키마를 만들려면 Visual Studio XML 디자이너에서 XML 파일을 연 다음 **XML** 메뉴에서 **스키마 만들기**를 클릭합니다.  XSD 스키마 집합을 만든 후에는 만든 스키마 집합을 하나 이상의 XSD 파일에 저장하고 이 파일을 프로젝트에 포함할 수 있습니다.  자세한 내용은 [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)을 참조하십시오.  
  
 동일한 스키마가 유추되어야 하는 여러 XML 문서에서 서로 다른 XSD 스키마 집합이 유추될 수 있습니다.  특정 요소 및 특성이 한 XML 파일에서는 발견되고 다른 파일에서는 발견되지 않거나 요소가 서로 다른 순서로 포함되어 있는 경우 등에 이러한 현상이 발생할 수 있습니다.  XSD 스키마 유추를 사용할 때는 유추된 XSD 스키마 집합이 완전하고 정확한지 검토해야 합니다.  
  
## 멤버 목록  
 사용자가 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체의 인스턴스\(또는 `IEnumerable(Of XElement)` 또는 `IEnumerable(Of XDocument)`의 인스턴스\)를 구분하기 위해 마침표\(.\)를 입력하면 Visual Basic IntelliSense는 가능한 개체 멤버 목록을 표시합니다.  다음 목록에서 설명하는 대로 맨 처음 목록에는 XML 축 속성을 나타내는 세 가지 옵션이 포함됩니다.  
  
|||  
|-|-|  
|옵션|설명|  
|**\< \>**|이 옵션을 선택하면 가능한 자식 요소 목록이 표시됩니다.  자세한 내용은 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드를 참조하십시오.|  
|**@**|이 옵션을 선택하면 가능한 특성 목록이 표시됩니다.  자세한 내용은 [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)을 참조하십시오. 이 옵션은 형식이 <xref:System.Xml.Linq.XElement>인 개체에만 사용할 수 있습니다.|  
|**…\< \>**|이 옵션을 선택하면 가능한 하위 요소 목록이 표시됩니다.  자세한 내용은 [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드를 참조하십시오.|  
  
 목록에서 XML 옵션을 선택하거나 입력합니다.  그러면 선택한 옵션에 해당되는 XML 스키마의 가능한 멤버가 멤버 목록에 표시됩니다.  특정 XML 네임스페이스 접두사와 연관된 XML 네임스페이스를 가져온 경우 가능한 XML 네임스페이스 접두사 목록이 멤버 목록에 포함됩니다.  
  
 예를 들어 다음 XSD 스키마를 확인하십시오.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 XSD 스키마에 유효한 XML은 다음과 같습니다.  
  
```  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 이 XSD 스키마 파일을 프로젝트에 포함하고 대상 네임스페이스를 XSD 스키마에서 사용자의 코드 파일이나 프로젝트로 가져오는 경우 사용자가 Visual Basic 코드를 입력할 때 Visual Basic IntelliSense는 스키마의 멤버를 표시합니다.  XSD 스키마의 대상 네임스페이스를 기본 네임스페이스로 가져오고 다음을 입력하면 IntelliSense는 `PurchaseOrder` XML 요소에 대한 가능한 자식 요소 목록을 표시합니다.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 이 목록에는 Address, Comment 및 Items 요소가 포함됩니다.  
  
### IntelliSense 목록 항목의 확신도  
 IntelliSense에 사용할 XSD 형식을 판별하는 것은 정확하지 않습니다.  따라서 XML IntelliSense에서 가능한 멤버 목록을 광범위하게 표시하는 경우가 많습니다.  IntelliSense 멤버 목록에서의 항목 선택을 지원하기 위해 항목이 표시될 때 XML IntelliSense가 특정 멤버에 대해 갖고 있는 확신도가 함께 표시됩니다.  
  
 XML IntelliSense에서 XSD 스키마의 특정 형식을 식별할 수 있는 경우도 있습니다.  이 경우 해당 XSD 형식에 대해 매우 높은 수준 확신도의 가능한 자식 요소, 특성 또는 하위 요소를 표시합니다.  이러한 항목은 확인 표시로 식별됩니다.  
  
 그러나 XML IntelliSense가 XSD 스키마에서 특정 형식을 식별할 수 없는 경우도 있습니다.  이 경우 해당 프로젝트의 XSD 스키마에서 낮은 수준 확신도의 가능한 자식 요소, 특성 또는 하위 요소를 광범위하게 표시합니다.  이러한 항목은 물음표로 식별됩니다.  
  
## 참고 항목  
 [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)