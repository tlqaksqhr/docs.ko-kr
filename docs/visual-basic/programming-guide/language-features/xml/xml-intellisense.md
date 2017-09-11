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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 9a3c6f923bc9458997c388d4cf74ca113265a8cc
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017

---
# <a name="xml-intellisense-in-visual-basic"></a><span data-ttu-id="782c6-102">Visual Basic의 XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="782c6-102">XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="782c6-103">Visual Basic 코드 편집기에는 XML 스키마에 정의 된 요소에 대 한 단어 완성을 제공 하는 XML에 대 한 IntelliSense 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-103">The Visual Basic Code Editor includes IntelliSense features for XML that provide word completion for elements defined in an XML schema.</span></span> <span data-ttu-id="782c6-104">프로젝트에 XML 스키마 정의 (XSD) 파일을 포함 하 고 사용 하 여 스키마의 대상 네임 스페이스를 가져오는 경우는 `Imports` 문, 코드 편집기에 대 한 올바른 멤버 변수의 IntelliSense 목록에서 XSD 스키마에서 요소를 포함 됩니다 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="782c6-104">If you include an XML Schema Definition (XSD) file in your project and import the target namespace of the schema by using the `Imports` statement, the Code Editor will include elements from the XSD schema in the IntelliSense list of valid member variables for <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="782c6-105">다음 그림에 대 한 IntelliSense 멤버 목록에 나와 있는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="782c6-105">The following illustration shows the IntelliSense members list for an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="782c6-106">![Visual Basic의 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span><span class="sxs-lookup"><span data-stu-id="782c6-106">![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span></span>  
<span data-ttu-id="782c6-107">XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="782c6-107">XML IntelliSense</span></span>  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a><span data-ttu-id="782c6-108">Visual Basic의 XML IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="782c6-108">Enabling XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="782c6-109">Visual Basic의 XML IntelliSense를 사용 하려면 Visual Basic 프로젝트에 XSD 스키마 파일을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-109">To enable XML IntelliSense in Visual Basic, you must include an XSD schema file in your Visual Basic project.</span></span> <span data-ttu-id="782c6-110">또한 가져와야 XSD 스키마에 대 한 대상 네임 스페이스 코드 파일에 사용 하 여는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-110">You must also import the target namespace for the XSD schema into your code file by using the `Imports` statement.</span></span> <span data-ttu-id="782c6-111">사용 하 여 프로젝트 수준의 네임 스페이스 목록에는 대상 네임 스페이스를 추가할 수는 또는 **참조** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-111">Alternatively, you can add the target namespace to the project-level namespace list by using the **References** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="782c6-112">예를 보려면 [하는 방법: Visual Basic의 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-112">For examples, see [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span> <span data-ttu-id="782c6-113">자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) 및 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-113">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) and [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="782c6-114">기본적 하는 Visual Basic 프로젝트에서 XSD 스키마 파일을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-114">Note that by default you cannot see XSD schema files in Visual Basic projects.</span></span> <span data-ttu-id="782c6-115">클릭 해야 할 수 있습니다는 **모든 파일 표시** 단추를 XSD 파일을 프로젝트에 포함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-115">You may have to click the **Show All Files** button to select an XSD file to include in your project.</span></span>  
  
### <a name="generating-a-schema-file-schema-inference"></a><span data-ttu-id="782c6-116">스키마 파일 (스키마 유추)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-116">Generating a Schema File (Schema Inference)</span></span>  
 <span data-ttu-id="782c6-117">Visual Studio XML 도구를 사용 하 여 XSD 스키마를 유추 하 여 기존 XML 파일에 대 한 XSD 스키마를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-117">You can create an XSD schema for an existing XML file by inferring the XSD schema by using Visual Studio XML tools.</span></span>  
  
-   <span data-ttu-id="782c6-118">S p&1; 부터는, 하나 이상의 XML 문서에서 유추 되는 XML 스키마 집합을 만들고 프로젝트를 포함 하는 XML to Schema 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-118">Starting in SP1, you can use the XML to Schema Wizard to create an XML Schema set that is inferred from one or more XML documents and include it your project.</span></span> <span data-ttu-id="782c6-119">HTTP 인터넷 주소에서 XML 또는 형식화 하거나 XML to Schema 마법사에 붙여 넣은 XML 텍스트 파일의 형태로 XML 문서의 모든 조합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-119">You can use any combination of XML documents in the form of text files, XML from HTTP Internet addresses, or XML that is typed or pasted into the XML to Schema Wizard.</span></span> <span data-ttu-id="782c6-120">XML to Schema 마법사에 액세스 하려면 **새 항목 추가** 에 **프로젝트** 메뉴 추가 **XML 스키마를** 템플릿 중 하나에서 **데이터** 또는 **공통 항목** 템플릿 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-120">To access the XML to Schema Wizard, click **Add New Item** on the **Project** menu and add an **XML to Schema** template from either the **Data** or **Common Items** template group.</span></span> <span data-ttu-id="782c6-121">모든 XML 문서 소스에서 XML 스키마 집합을 유추를 포함 한 후 클릭 **확인** 유추 된 스키마를 만들려면 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-121">After you have included all the XML document sources to infer the XML Schema set from, click **OK** to create the inferred schema set.</span></span> <span data-ttu-id="782c6-122">자세한 내용은 참조 [XML to Schema 마법사](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-122">For more information, see [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span></span>  
  
-   <span data-ttu-id="782c6-123">또한 XML 파일에서 설정 하는 XSD 스키마를 유추 하는 Visual Studio XML 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-123">You can also use the Visual Studio XML Editor to infer an XSD schema set from an XML file.</span></span> <span data-ttu-id="782c6-124">XML 편집기를 사용 하 여 설정 하는 XML 스키마를 만들려면 Visual Studio XML 디자이너에서 XML 파일을 열고 하 고 클릭 한 다음 **Create Schema** 에 **XML** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="782c6-124">To create an XML schema set by using the XML Editor, open an XML file in the Visual Studio XML Designer and then click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="782c6-125">XSD 스키마 집합을 만든 후에 하나 이상의 XSD 파일에 생성된 된 스키마 집합을 저장할 수 있으며 프로젝트에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-125">After you create the XSD schema set, you can save the created schema set to one or more XSD files and include them in your project.</span></span> <span data-ttu-id="782c6-126">자세한 내용은 참조[하는 방법: Visual Basic의 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-126">For more information, see[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span>  
  
 <span data-ttu-id="782c6-127">Note 상이한 XSD 스키마가 동일한 스키마를 유추 하는 여러 XML 문서에서 유추 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-127">Note that different XSD schema sets might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="782c6-128">이 XML 파일 한 개 안 되며, 발견 된 특정 요소 및 특성 또는 요소 예를 들어 다른 순서에 포함 된 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-128">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="782c6-129">XSD 스키마 유추를 사용 하는 경우에 완결성 및 정확도 대해 유추 된 XSD 스키마 집합을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-129">You should review inferred XSD schema sets for completeness and accuracy when you use XSD schema inference.</span></span>  
  
## <a name="member-list"></a><span data-ttu-id="782c6-130">멤버 목록</span><span class="sxs-lookup"><span data-stu-id="782c6-130">Member List</span></span>  
 <span data-ttu-id="782c6-131">인스턴스를 구분 하는 마침표 (.)를 입력 한 후는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체 (또는 인스턴스의 `IEnumerable(Of XElement)` 또는 `IEnumerable(Of XDocument)`), Visual Basic IntelliSense에는 가능한 개체 멤버의 목록이 표시 됩니다.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="782c6-131">After you type a period (.) to delimit an instance of an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object (or an instance of `IEnumerable(Of XElement)` or `IEnumerable(Of XDocument)`), Visual Basic IntelliSense displays a list of possible object members.</span></span> <span data-ttu-id="782c6-132">초기 목록에는 다음 목록에 설명 된 대로 XML 축 속성을 나타내는 세 가지 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-132">The initial list includes three options that represent XML axis properties, as described in the following list.</span></span>  
  
|<span data-ttu-id="782c6-133">옵션</span><span class="sxs-lookup"><span data-stu-id="782c6-133">Option</span></span>|<span data-ttu-id="782c6-134">설명</span><span class="sxs-lookup"><span data-stu-id="782c6-134">Description</span></span>|  
|---|---|  
|**\< >**|<span data-ttu-id="782c6-135">목록이 가능한 자식 요소를 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-135">Select this option to show a list of possible child elements.</span></span> <span data-ttu-id="782c6-136">자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="782c6-136">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
|**@**|<span data-ttu-id="782c6-137">가능한 특성의 목록을 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-137">Select this option to show a list of possible attributes.</span></span> <span data-ttu-id="782c6-138">자세한 내용은 참조 [XML 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)합니다. 이 옵션은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 형식의 개체에 대해서만 사용할 수</span><span class="sxs-lookup"><span data-stu-id="782c6-138">For more information, see [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).This option is available only for objects of type <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="782c6-139">**…\< >**</span><span class="sxs-lookup"><span data-stu-id="782c6-139">**…\< >**</span></span>|<span data-ttu-id="782c6-140">가능한 하위 요소의 목록이 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-140">Select this option to show a list of possible descendant elements.</span></span> <span data-ttu-id="782c6-141">자세한 내용은 참조 [하는 방법: XML 하위 요소 액세스](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) 및 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="782c6-141">For more information, see [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
  
 <span data-ttu-id="782c6-142">선택 하거나 목록에서 XML 옵션 중 하나를 입력 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-142">Select or begin typing any of the XML options from the list.</span></span> <span data-ttu-id="782c6-143">멤버 목록에는 선택한 옵션에만 적용 되는 XML 스키마의 잠재적 구성원 그러면 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-143">The member list will then display potential members from the XML schema that are specific to the selected option.</span></span> <span data-ttu-id="782c6-144">XML 네임 스페이스를 가져온 특정 XML 네임 스페이스 접두사와 연결 된 경우 멤버 목록에 잠재적인 XML 네임 스페이스 접두사의 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-144">If you have XML namespaces imported that are associated with a specific XML namespace prefix, a list of potential XML namespace prefixes is included in the member list.</span></span>  
  
 <span data-ttu-id="782c6-145">예를 들어 다음 XSD 스키마를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-145">For example, consider the following XSD schema.</span></span>  
  
```xml  
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
  
 <span data-ttu-id="782c6-146">XSD 스키마에 대 한 유효한 XML은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-146">Valid XML for the XSD schema would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 <span data-ttu-id="782c6-147">프로젝트에서이 XSD 스키마 파일을 포함 하 고 코드 파일이 나 프로젝트에 XSD 스키마에서 대상 네임 스페이스를 가져오는 Visual Basic IntelliSense는 Visual Basic 코드를 입력할 때 스키마에서 멤버를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-147">If you include this XSD schema file in a project and import the target namespace from the XSD schema into your code file or project, Visual Basic IntelliSense displays members from the schema as you type your Visual Basic code.</span></span> <span data-ttu-id="782c6-148">IntelliSense에 대 한 가능한 자식 요소 목록이 표시 됩니다 XSD 스키마에 대 한 대상 네임 스페이스는 기본 네임 스페이스에서 가져오는 경우 다음을 입력 하면는 `PurchaseOrder` XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-148">If the target namespace for the XSD schema is imported as the default namespace and you type the following, IntelliSense displays a list of possible child elements for the `PurchaseOrder` XML element.</span></span>  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 <span data-ttu-id="782c6-149">목록 주소, 설명 및 항목 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-149">The list consists of the Address, Comment, and Items elements.</span></span>  
  
### <a name="certainty-levels-for-intellisense-list-items"></a><span data-ttu-id="782c6-150">IntelliSense 목록 항목에 대 한 확실 하 게 수준</span><span class="sxs-lookup"><span data-stu-id="782c6-150">Certainty Levels for IntelliSense List Items</span></span>  
 <span data-ttu-id="782c6-151">IntelliSense를 사용 하 여 XSD 형식을 결정 하는 정확 하지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-151">Determining the XSD type to use for IntelliSense is not exact.</span></span> <span data-ttu-id="782c6-152">결과적으로 XML IntelliSense 보이며 가능한 멤버의 확장된 된 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-152">As a result, XML IntelliSense will often show an expanded list of possible members.</span></span> <span data-ttu-id="782c6-153">IntelliSense 멤버 목록에서 항목을 선택 하면 지원 하기 위해 항목 수준 XML IntelliSense에 특정 멤버에 대 한 확신을 표시 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-153">To aid you in selecting an item from the IntelliSense member list, items are displayed with an indication of the level of certainty that XML IntelliSense has for a particular member.</span></span>  
  
 <span data-ttu-id="782c6-154">경우에 따라 XML IntelliSense에는 XSD 스키마에서 특정 형식을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-154">Sometimes XML IntelliSense can identify a specific type from the XSD schema.</span></span> <span data-ttu-id="782c6-155">이러한 경우에 가능한 자식 요소, 특성 또는 하위 요소가 해당 XSD 형식에 대 한 확신도의 높은 수준으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-155">In these cases, it will display possible child elements, attributes, or descendant elements for that XSD type with a high degree of certainty.</span></span> <span data-ttu-id="782c6-156">이러한 항목은 확인 표시로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-156">These items are identified with a check mark.</span></span>  
  
 <span data-ttu-id="782c6-157">그러나 때로는 XML IntelliSense 수 없는 XSD 스키마에서 특정 형식을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-157">However, sometimes XML IntelliSense is not able to identify a specific type from the XSD schema.</span></span> <span data-ttu-id="782c6-158">이러한 경우에는 낮은 수준의 확신도의 가능한 자식 요소, 특성 또는 하위 요소는 프로젝트에 대 한 XSD 스키마에서 확장된 된 목록이 표시 됩니다 것.</span><span class="sxs-lookup"><span data-stu-id="782c6-158">In these cases, it will display an expanded list of possible child elements, attributes, or descendant elements from the XSD schema for the project with a low degree of certainty.</span></span> <span data-ttu-id="782c6-159">이러한 항목은 물음표로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="782c6-159">These items are identified with a question mark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782c6-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="782c6-160">See Also</span></span>  
 <span data-ttu-id="782c6-161">[방법: Visual Basic에서 XML IntelliSense 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-161">[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span></span>  
<span data-ttu-id="782c6-162"> [XML to Schema 마법사](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-162"> [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span></span>  
<span data-ttu-id="782c6-163"> [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-163"> [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="782c6-164"> [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="782c6-165"> [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-165"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="782c6-166"> [XML 하위 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="782c6-166"> [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span></span>  
<span data-ttu-id="782c6-167"> [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="782c6-167"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
