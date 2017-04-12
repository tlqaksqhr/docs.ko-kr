---
title: "Visual Basic의 XML IntelliSense | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8c43db3d2010e4fa92eebeec8a973c50052b1340
ms.lasthandoff: 03/13/2017

---
# <a name="xml-intellisense-in-visual-basic"></a>Visual Basic의 XML IntelliSense
Visual Basic 코드 편집기에는 XML 스키마에 정의 된 요소에 대 한 단어 완성을 제공 하는 XML에 대 한 IntelliSense 기능이 포함 됩니다. 프로젝트에 XML 스키마 정의 (XSD) 파일을 포함 하 고 사용 하 여 스키마의 대상 네임 스페이스를 가져오는 경우는 `Imports` 문, 코드 편집기에 대 한 올바른 멤버 변수의 IntelliSense 목록에서 XSD 스키마에서 요소를 포함 됩니다 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 다음 그림에 대 한 IntelliSense 멤버 목록에 나와 있는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
 ![Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")  
XML IntelliSense  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a>Visual Basic의 XML IntelliSense 사용  
 Visual Basic의 XML IntelliSense를 사용 하려면 Visual Basic 프로젝트에 XSD 스키마 파일을 포함 해야 합니다. 또한 가져와야 XSD 스키마에 대 한 대상 네임 스페이스 코드 파일에 사용 하 여는 `Imports` 문입니다. 사용 하 여 프로젝트 수준의 네임 스페이스 목록에는 대상 네임 스페이스를 추가할 수는 또는 **참조** Visual Basic 프로젝트 디자이너의 페이지입니다. 예를 보려면 [하는 방법: Visual Basic의 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)합니다. 자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 및 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.  
  
 기본적 하는 Visual Basic 프로젝트에서 XSD 스키마 파일을 볼 수 없습니다. 클릭 해야 할 수 있습니다는 **모든 파일 표시** 단추를 XSD 파일을 프로젝트에 포함을 선택 합니다.  
  
### <a name="generating-a-schema-file-schema-inference"></a>스키마 파일 (스키마 유추)를 생성합니다.  
 Visual Studio XML 도구를 사용 하 여 XSD 스키마를 유추 하 여 기존 XML 파일에 대 한 XSD 스키마를 만들 수 있습니다.  
  
-   S p&1; 부터는, 하나 이상의 XML 문서에서 유추 되는 XML 스키마 집합을 만들고 프로젝트를 포함 하는 XML to Schema 마법사를 사용할 수 있습니다. HTTP 인터넷 주소에서 XML 또는 형식화 하거나 XML to Schema 마법사에 붙여 넣은 XML 텍스트 파일의 형태로 XML 문서의 모든 조합을 사용할 수 있습니다. XML to Schema 마법사에 액세스 하려면 **새 항목 추가** 에 **프로젝트** 메뉴 추가 **XML 스키마를** 템플릿 중 하나에서 **데이터** 또는 **공통 항목** 템플릿 그룹입니다. 모든 XML 문서 소스에서 XML 스키마 집합을 유추를 포함 한 후 클릭 **확인** 유추 된 스키마를 만들려면 다음을 설정 합니다. 자세한 내용은 참조 [XML to Schema 마법사](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)합니다.  
  
-   또한 XML 파일에서 설정 하는 XSD 스키마를 유추 하는 Visual Studio XML 편집기를 사용할 수 있습니다. XML 편집기를 사용 하 여 설정 하는 XML 스키마를 만들려면 Visual Studio XML 디자이너에서 XML 파일을 열고 하 고 클릭 한 다음 **Create Schema** 에 **XML** 메뉴. XSD 스키마 집합을 만든 후에 하나 이상의 XSD 파일에 생성된 된 스키마 집합을 저장할 수 있으며 프로젝트에 포함할 수 있습니다. 자세한 내용은 참조[하는 방법: Visual Basic의 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)합니다.  
  
 Note 상이한 XSD 스키마가 동일한 스키마를 유추 하는 여러 XML 문서에서 유추 될 수 있습니다. 이 XML 파일 한 개 안 되며, 발견 된 특정 요소 및 특성 또는 요소 예를 들어 다른 순서에 포함 된 경우 발생할 수 있습니다. XSD 스키마 유추를 사용 하는 경우에 완결성 및 정확도 대해 유추 된 XSD 스키마 집합을 검토 해야 합니다.  
  
## <a name="member-list"></a>멤버 목록  
 인스턴스를 구분 하는 마침표 (.)를 입력 한 후는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체 (또는 인스턴스의 `IEnumerable(Of XElement)` 또는 `IEnumerable(Of XDocument)`), Visual Basic IntelliSense에는 가능한 개체 멤버의 목록이 표시 됩니다.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 초기 목록에는 다음 목록에 설명 된 대로 XML 축 속성을 나타내는 세 가지 옵션이 포함 됩니다.  
  
|옵션|설명|  
|---|---|  
|**\< >**|목록이 가능한 자식 요소를 표시 하려면이 옵션을 선택 합니다. 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
|**@**|가능한 특성의 목록을 표시 하려면이 옵션을 선택 합니다. 자세한 내용은 참조 [XML 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)합니다. 이 옵션은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 형식의 개체에 대해서만 사용할 수|  
|**…\< >**|가능한 하위 요소의 목록이 표시 하려면이 옵션을 선택 합니다. 자세한 내용은 참조 [하는 방법: XML 하위 요소 액세스](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
  
 선택 하거나 목록에서 XML 옵션 중 하나를 입력 하기 시작 합니다. 멤버 목록에는 선택한 옵션에만 적용 되는 XML 스키마의 잠재적 구성원 그러면 표시 됩니다. XML 네임 스페이스를 가져온 특정 XML 네임 스페이스 접두사와 연결 된 경우 멤버 목록에 잠재적인 XML 네임 스페이스 접두사의 목록이 포함 됩니다.  
  
 예를 들어 다음 XSD 스키마를 고려해 야 합니다.  
  
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
  
 XSD 스키마에 대 한 유효한 XML은 다음과 유사 합니다.  
  
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
  
 프로젝트에서이 XSD 스키마 파일을 포함 하 고 코드 파일이 나 프로젝트에 XSD 스키마에서 대상 네임 스페이스를 가져오는 Visual Basic IntelliSense는 Visual Basic 코드를 입력할 때 스키마에서 멤버를 표시 합니다. IntelliSense에 대 한 가능한 자식 요소 목록이 표시 됩니다 XSD 스키마에 대 한 대상 네임 스페이스는 기본 네임 스페이스에서 가져오는 경우 다음을 입력 하면는 `PurchaseOrder` XML 요소입니다.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 목록 주소, 설명 및 항목 요소로 구성 됩니다.  
  
### <a name="certainty-levels-for-intellisense-list-items"></a>IntelliSense 목록 항목에 대 한 확실 하 게 수준  
 IntelliSense를 사용 하 여 XSD 형식을 결정 하는 정확 하지 않은 합니다. 결과적으로 XML IntelliSense 보이며 가능한 멤버의 확장된 된 목록이 있습니다. IntelliSense 멤버 목록에서 항목을 선택 하면 지원 하기 위해 항목 수준 XML IntelliSense에 특정 멤버에 대 한 확신을 표시 하 여 표시 됩니다.  
  
 경우에 따라 XML IntelliSense에는 XSD 스키마에서 특정 형식을 식별할 수 있습니다. 이러한 경우에 가능한 자식 요소, 특성 또는 하위 요소가 해당 XSD 형식에 대 한 확신도의 높은 수준으로 표시 됩니다. 이러한 항목은 확인 표시로 식별 됩니다.  
  
 그러나 때로는 XML IntelliSense 수 없는 XSD 스키마에서 특정 형식을 식별 합니다. 이러한 경우에는 낮은 수준의 확신도의 가능한 자식 요소, 특성 또는 하위 요소는 프로젝트에 대 한 XSD 스키마에서 확장된 된 목록이 표시 됩니다 것. 이러한 항목은 물음표로 식별 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Basic에서 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [XML to Schema 마법사](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [XML 하위 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
