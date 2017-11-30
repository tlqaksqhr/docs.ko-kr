---
title: "XPathNavigator를 사용하여 XML 데이터 수정"
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
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec2846dcac6bfe14746e038d592b7dfe49374993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="modify-xml-data-using-xpathnavigator"></a><span data-ttu-id="381d7-102">XPathNavigator를 사용하여 XML 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-102">Modify XML Data using XPathNavigator</span></span>
<span data-ttu-id="381d7-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에서 노드와 값을 수정하는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to modify nodes and values in an XML document.</span></span> <span data-ttu-id="381d7-104">이러한 메서드를 사용하려면 <xref:System.Xml.XPath.XPathNavigator> 개체가 편집 가능한 상태여야 합니다. 즉, <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 속성이 `true`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="381d7-105"><xref:System.Xml.XPath.XPathNavigator> 클래스의 <xref:System.Xml.XmlDocument.CreateNavigator%2A> 메서드에서는 XML 문서를 편집할 수 있는 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="381d7-106"><xref:System.Xml.XPath.XPathNavigator> 클래스에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체는 읽기 전용이며, <xref:System.Xml.XPath.XPathNavigator> 개체에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체의 편집 메서드를 사용하려고 하면 <xref:System.NotSupportedException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object result in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="381d7-107">편집 가능한 만들기에 대 한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 개체 참조 [XPathDocument 및 XmlDocument를 사용 하 여 XML 데이터를 읽는](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="modifying-nodes"></a><span data-ttu-id="381d7-108">노드 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-108">Modifying Nodes</span></span>  
 <span data-ttu-id="381d7-109"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 메서드를 사용하면 쉽게 노드 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-109">A simple technique for changing the value of a node is to use the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="381d7-110">다음 표에서는 여러 노드 형식에서 이러한 메서드를 사용한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-110">The following table lists the effects of these methods on different node types.</span></span>  
  
|<xref:System.Xml.XPath.XPathNodeType>|<span data-ttu-id="381d7-111">변경되는 데이터</span><span class="sxs-lookup"><span data-stu-id="381d7-111">Data Changed</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|<span data-ttu-id="381d7-112">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-112">Not supported.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|<span data-ttu-id="381d7-113">요소 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-113">The content of the element.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|<span data-ttu-id="381d7-114">특성 값</span><span class="sxs-lookup"><span data-stu-id="381d7-114">The value of the attribute.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|<span data-ttu-id="381d7-115">텍스트 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-115">The text content.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|<span data-ttu-id="381d7-116">대상을 제외한 내용</span><span class="sxs-lookup"><span data-stu-id="381d7-116">The content, excluding the target.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|<span data-ttu-id="381d7-117">주석의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-117">The content of the comment.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|<span data-ttu-id="381d7-118">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="381d7-118">Not Supported.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="381d7-119"><xref:System.Xml.XPath.XPathNodeType.Namespace> 노드나 <xref:System.Xml.XPath.XPathNodeType.Root> 노드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-119">Editing <xref:System.Xml.XPath.XPathNodeType.Namespace> nodes or the <xref:System.Xml.XPath.XPathNodeType.Root> node is not supported.</span></span>  
  
 <span data-ttu-id="381d7-120">또한 <xref:System.Xml.XPath.XPathNavigator> 클래스는 노드를 삽입하고 제거하는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-120">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of methods used to insert and remove nodes.</span></span> <span data-ttu-id="381d7-121">삽입 하 고 XML 문서에서 노드를 제거 하는 방법에 대 한 자세한 내용은 참조는 [XPathNavigator를 사용 하 여 XML 데이터 삽입](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md) 및 [XPathNavigator를 사용 하 여 XML 데이터 제거](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-121">For more information about inserting and removing nodes from an XML document, see the [Insert XML Data using XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md) and [Remove XML Data using XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md) topics.</span></span>  
  
### <a name="modifying-untyped-values"></a><span data-ttu-id="381d7-122">형식화되지 않은 값 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-122">Modifying Untyped Values</span></span>  
 <span data-ttu-id="381d7-123"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드는 형식화되지 않은 `string` 값을 간단히 삽입합니다. 이 값은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 값인 매개 변수로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-123">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="381d7-124">이 값은 스키마 정보를 사용할 수 있을 경우 노드 형식에 따라 새 값이 유효한지 여부를 확인하지 않거나 특정한 형식 없이 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-124">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="381d7-125">다음 예제에서는 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드를 사용하여 `price` 파일의 모든 `contosoBooks.xml` 요소를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-125">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="381d7-126">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-126">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a><span data-ttu-id="381d7-127">형식화된 값 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-127">Modifying Typed Values</span></span>  
 <span data-ttu-id="381d7-128">노드의 형식이 W3C XML 스키마 단순 형식이면 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드에서 삽입한 새 값은 설정되기 전에 단순 형식의 패싯에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-128">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="381d7-129">노드의 형식에 따라 새 값이 유효하지 않은 경우, 예를 들면 `-1` 형식의 요소에 `xs:positiveInteger`의 값을 설정하는 경우에는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-129">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="381d7-130">다음 예제에서는 `price` 파일에 있는 첫 번째 `book` 요소의 `contosoBooks.xml` 요소 값을 <xref:System.DateTime> 값으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-130">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="381d7-131">`price` 요소의 XML 스키마 형식은 `xs:decimal` 파일의 `contosoBooks.xsd`로 정의되므로 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-131">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="381d7-132">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-132">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="381d7-133">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-133">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a><span data-ttu-id="381d7-134">강력한 형식의 XML 데이터를 편집한 결과</span><span class="sxs-lookup"><span data-stu-id="381d7-134">The Effects of Editing Strongly Typed XML Data</span></span>  
 <span data-ttu-id="381d7-135"><xref:System.Xml.XPath.XPathNavigator> 클래스는 W3C XML 스키마를 사용해 강력한 형식의 XML을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-135">The <xref:System.Xml.XPath.XPathNavigator> class uses the W3C XML Schema as a basis for describing strongly-typed XML.</span></span> <span data-ttu-id="381d7-136">W3C XML 스키마 문서에 대한 유효성 검사를 기반으로 요소 및 특성에 형식 정보로 주석을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-136">Elements and attributes can be annotated with type information based on validation against a W3C XML Schema document.</span></span> <span data-ttu-id="381d7-137">다른 요소나 특성을 포함할 수 있는 요소를 복합 형식이라고 하며 텍스트 내용만 포함할 수 있는 요소를 단순 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-137">Elements that can contain other elements or attributes are called complex types, while those that can only contain textual content are called simple types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="381d7-138">특성에는 단순 형식만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-138">Attributes can only have simple types.</span></span>  
  
 <span data-ttu-id="381d7-139">특성이나 요소가 해당 형식 정의와 관련된 모든 규칙을 준수하는 경우 이 특성이나 요소는 스키마에 대해 유효한 것으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-139">An element or attribute can be considered to be schema-valid if it conforms to all the rules specific to its type definition.</span></span> <span data-ttu-id="381d7-140">스키마에 대해 유효하려면 단순 형식 `xs:int`가 포함된 요소에는 -2147483648에서 2147483647까지의 숫자 값이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-140">An element that has the simple type `xs:int` has to contain a numeric value between -2147483648 and 2147483647 to be schema-valid.</span></span> <span data-ttu-id="381d7-141">복합 형식의 경우 요소의 스키마 유효성 검사는 자식 요소 및 특성의 스키마 유효성 검사에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-141">For complex types, the schema-validity of the element is dependent on the schema-validity of its child elements and attributes.</span></span> <span data-ttu-id="381d7-142">그러므로 요소가 복합 형식 정의에 대해 유효할 경우 모든 자식 요소 및 특성은 해당 형식 정의에 대해 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-142">Thus if an element is valid against its complex type definition, all its child elements and attributes are valid against their type definitions.</span></span> <span data-ttu-id="381d7-143">마찬가지로 요소의 자식 요소 또는 특성 중 하나라도 형식 정의에 대해 유효하지 않을 경우 또는 유효성을 알 수 없는 경우 해당 요소도 유효하지 않거나 요소의 유효성을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-143">Similarly, if even one of the child elements or attributes of an element is invalid against its type definition, or has an unknown validity, the element is also either invalid or of unknown validity.</span></span>  
  
 <span data-ttu-id="381d7-144">요소의 유효성이 자식 요소 및 특성의 유효성에 따라 결정되는 경우 자식 요소나 특성을 수정하면 요소가 이전에 유효했더라도 요소의 유효성이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-144">Given that the validity of an element is dependent on the validity of its child elements and attributes, modifications to either result in altering the validity of the element if it was previously valid.</span></span> <span data-ttu-id="381d7-145">특히 요소의 자식 요소 또는 특성을 삽입, 업데이트 또는 삭제할 경우 요소의 유효성을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-145">Specifically, if the child elements or attributes of an element are inserted, updated, or deleted, then the validity of the element becomes unknown.</span></span> <span data-ttu-id="381d7-146">요소의 유효성은 요소의 <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> 속성의 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 속성을 <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>으로 설정하여 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-146">This is represented by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the element's <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property being set to <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>.</span></span> <span data-ttu-id="381d7-147">더욱이 요소의 부모 요소, 이 부모 요소의 부모 요소 등의 유효성도 알 수 없기 때문에 이 결과는 XML 문서에서 재귀적 상향 계단식으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-147">Furthermore, this effect cascades upwards recursively across the XML document, because the validity of the element's parent element (and its parent element, and so on) also becomes unknown.</span></span>  
  
 <span data-ttu-id="381d7-148">스키마 유효성 검사에 대 한 자세한 내용은 및 <xref:System.Xml.XPath.XPathNavigator> 클래스를 참조 하십시오. [XPathNavigator를 사용 하 여 스키마 유효성 검사](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-148">For more information about schema validation and the <xref:System.Xml.XPath.XPathNavigator> class, see [Schema Validation using XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md).</span></span>  
  
### <a name="modifying-attributes"></a><span data-ttu-id="381d7-149">특성 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-149">Modifying Attributes</span></span>  
 <span data-ttu-id="381d7-150"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 및 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드를 사용하여 형식화되지 않은 특성 노드와 형식화된 특성 노드 및 "노드 수정" 단원에 나열된 기타 노드 형식을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-150">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods can be used to modify untyped and typed attribute nodes as well as the other node types listed in the "Modifying Nodes" section.</span></span>  
  
 <span data-ttu-id="381d7-151">다음 예제에서는 `genre` 파일에서 첫 번째 `book` 요소의 `books.xml` 특성 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-151">The following example changes the value of the `genre` attribute of the first `book` element in the `books.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
navigator.MoveToChild("book", String.Empty)  
navigator.MoveToAttribute("genre", String.Empty)  
  
navigator.SetValue("non-fiction")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
navigator.MoveToChild("book", String.Empty);  
navigator.MoveToAttribute("genre", String.Empty);  
  
navigator.SetValue("non-fiction");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="381d7-152"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 및 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드에 대한 자세한 내용은 "형식화되지 않은 값 수정" 및 "형식화된 값 수정" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="381d7-152">For more information about the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods, see the "Modifying Untyped Values" and "Modifying Typed Values" sections.</span></span>  
  
## <a name="innerxml-and-outerxml-properties"></a><span data-ttu-id="381d7-153">InnerXml 및 OuterXml 속성</span><span class="sxs-lookup"><span data-stu-id="381d7-153">InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="381d7-154"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 XML 태그를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-154">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="381d7-155"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그를 주어진 XML `string`의 구문 분석된 내용과 함께 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-155">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="381d7-156">마찬가지로, <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그뿐만 아니라 현재 노드 자체도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-156">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="381d7-157">다음 예제에서는 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성을 사용하여 `price` 요소 값을 수정하고 `discount` 파일의 첫 번째 `book` 요소에 새 `contosoBooks.xml` 특성을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-157">The following example uses the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property to modify the value of the `price` element and insert a new `discount` attribute on the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml");  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>"  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>";  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="381d7-158">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-158">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a><span data-ttu-id="381d7-159">네임스페이스 노드 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-159">Modifying Namespace Nodes</span></span>  
 <span data-ttu-id="381d7-160">DOM(문서 개체 모델)에서 네임스페이스 선언은 삽입, 업데이트 및 삭제할 수 있는 정규 특성으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-160">In the Document Object Model (DOM), namespace declarations are treated as if they are regular attributes that can be inserted, updated and deleted.</span></span> <span data-ttu-id="381d7-161">다음 예제와 같이 네임스페이스 노드 값을 변경하면 네임스페이스 노드 범위 내에 있는 요소 및 특성의 ID가 변경될 수 있으므로 <xref:System.Xml.XPath.XPathNavigator> 클래스는 네임스페이스 노드에서 이러한 작업을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-161">The <xref:System.Xml.XPath.XPathNavigator> class does not allow such operations on namespace nodes because altering the value of a namespace node can change the identity of the elements and attributes within the scope of the namespace node as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="381d7-162">다음과 같은 방법으로 위의 XML 예제를 변경하면 각 요소의 네임스페이스 URI 값이 변경되기 때문에 문서에서 모든 요소의 이름을 효과적으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-162">If the XML example above is changed in the following way, this effectively renames every element in the document because the value of each element's namespace URI is changed.</span></span>  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="381d7-163"><xref:System.Xml.XPath.XPathNavigator> 클래스에서는 삽입하는 범위에서 네임스페이스 선언과 충돌하지 않는 네임스페이스 노드를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-163">Inserting namespace nodes that do not conflict with namespace declarations at the scope that they are inserted in is allowed by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="381d7-164">이러한 경우 XML 문서의 더 낮은 범위에서는 이 네임스페이스가 선언되지 않으며 다음 예제와 같이 이름이 바뀌지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-164">In this case, the namespace declarations are not declared at lower scopes in the XML document and does not result in renaming as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="381d7-165">다음과 같은 방법으로 위의 XML 예제를 변경하면 XML 문서에서 다른 네임스페이스 선언의 범위 아래에 네임스페이스 선언이 올바르게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-165">If the XML example above is changed in the following way, the namespace declarations are correctly propagated across the XML document below the scope of the other namespace declaration.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/">  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="381d7-166">위 XML 예제에서는 `a:parent-id` 네임스페이스의 `parent` 요소에 `http://www.contoso.com/parent-id` 특성을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-166">In the XML example above, the attribute `a:parent-id` is inserted on the `parent` element in the `http://www.contoso.com/parent-id` namespace.</span></span> <span data-ttu-id="381d7-167"><xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> 요소에서 `parent` 메서드를 사용하여 특성을 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-167">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method is used to insert the attribute while positioned on the `parent` element.</span></span> <span data-ttu-id="381d7-168">`http://www.contoso.com` 클래스에서 <xref:System.Xml.XPath.XPathNavigator> 네임스페이스 선언을 자동으로 삽입하여 XML 문서 나머지 부분의 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-168">The `http://www.contoso.com` namespace declaration is automatically inserted by the <xref:System.Xml.XPath.XPathNavigator> class to preserve the consistency of the rest of the XML document.</span></span>  
  
## <a name="modifying-entity-reference-nodes"></a><span data-ttu-id="381d7-169">엔터티 참조 노드 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-169">Modifying Entity Reference Nodes</span></span>  
 <span data-ttu-id="381d7-170"><xref:System.Xml.XmlDocument> 개체의 엔터티 참조 노드는 읽기 전용이므로 <xref:System.Xml.XPath.XPathNavigator> 또는 <xref:System.Xml.XmlNode> 클래스를 사용하여 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-170">Entity reference nodes in an <xref:System.Xml.XmlDocument> object are read-only and cannot be edited using either the <xref:System.Xml.XPath.XPathNavigator> or <xref:System.Xml.XmlNode> classes.</span></span> <span data-ttu-id="381d7-171">엔터티 참조 노드를 수정하려고 시도하면 <xref:System.InvalidOperationException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-171">Any attempt to modify an entity reference node results in an <xref:System.InvalidOperationException>.</span></span>  
  
## <a name="modifying-xsinil-nodes"></a><span data-ttu-id="381d7-172">xsi:nil 노드 수정</span><span class="sxs-lookup"><span data-stu-id="381d7-172">Modifying xsi:nil Nodes</span></span>  
 <span data-ttu-id="381d7-173">W3C XML 스키마 권장 사항에는 nillable 요소의 개념이 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-173">The W3C XML Schema recommendation introduces the concept of an element being nillable.</span></span> <span data-ttu-id="381d7-174">nillable 요소는 내용이 없고 여전히 유효할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-174">When an element is nillable, it is possible for the element to have no content and still be valid.</span></span> <span data-ttu-id="381d7-175">nillable 요소의 개념은 `null`인 개체의 개념과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-175">The concept of an element being nillable is similar to the concept of an object being `null`.</span></span> <span data-ttu-id="381d7-176">주요 차이점은 `null` 개체에는 액세스할 수 없으며 `xsi:nil` 요소에는 액세스할 수 있지만 자식 요소나 텍스트 등의 내용이 없는 특성과 같은 속성이 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-176">The main difference is that a `null` object cannot be accessed in any way, while an `xsi:nil` element still has properties such as attributes that can be accessed, but has no content (child elements or text).</span></span> <span data-ttu-id="381d7-177">XML 문서의 요소에서 `xsi:nil` 값의 `true` 특성을 사용하여 요소에 내용이 없음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-177">The existence of the `xsi:nil` attribute with a value of `true` on an element in an XML document is used to indicate that an element has no content.</span></span>  
  
 <span data-ttu-id="381d7-178"><xref:System.Xml.XPath.XPathNavigator> 개체를 사용하여 `xsi:nil` 값의 `true` 특성이 있는 유효한 요소에 내용을 추가하는 경우 `xsi:nil` 특성 값은 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-178">If an <xref:System.Xml.XPath.XPathNavigator> object is used to add content to a valid element with an `xsi:nil` attribute with a value of `true`, the value of its `xsi:nil` attribute is set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="381d7-179">`xsi:nil` 특성이 `false`로 설정된 요소의 내용을 삭제하면 이 특성 값은 `true`로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-179">If the content of an element with an `xsi:nil` attribute set to `false` is deleted, the value of the attribute is not changed to `true`.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="381d7-180">XML 문서 저장</span><span class="sxs-lookup"><span data-stu-id="381d7-180">Saving an XML Document</span></span>  
 <span data-ttu-id="381d7-181"><xref:System.Xml.XmlDocument> 클래스의 메서드를 사용하면 <xref:System.Xml.XmlDocument> 개체에서 변경된 내용을 이 항목에서 설명하는 편집 메서드의 결과로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-181">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the editing methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="381d7-182">변경 내용을 저장 하는 방법에 대 한 자세한 내용은 <xref:System.Xml.XmlDocument> 개체, 참조 [문서 작성 및 저장](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-182">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381d7-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="381d7-183">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="381d7-184">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="381d7-184">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="381d7-185">XPathNavigator를 사용 하 여 XML 데이터를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-185">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="381d7-186">XPathNavigator를 사용 하 여 XML 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="381d7-186">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
