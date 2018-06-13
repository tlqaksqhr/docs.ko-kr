---
title: XPathNavigator를 사용하여 XML 데이터 제거
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87dc7d83692f081f2c48a34cef8a33564f0e3089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577035"
---
# <a name="remove-xml-data-using-xpathnavigator"></a><span data-ttu-id="8bf15-102">XPathNavigator를 사용하여 XML 데이터 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-102">Remove XML Data using XPathNavigator</span></span>
<span data-ttu-id="8bf15-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에서 노드와 값을 제거하는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="8bf15-104">이러한 메서드를 사용하려면 <xref:System.Xml.XPath.XPathNavigator> 개체가 편집 가능한 상태여야 합니다. 즉, <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 속성이 `true`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="8bf15-105"><xref:System.Xml.XPath.XPathNavigator> 클래스의 <xref:System.Xml.XmlDocument.CreateNavigator%2A> 메서드에서는 XML 문서를 편집할 수 있는 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="8bf15-106"><xref:System.Xml.XPath.XPathNavigator> 클래스에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체는 읽기 전용이며, <xref:System.Xml.XPath.XPathNavigator> 개체에서 만든 <xref:System.Xml.XPath.XPathDocument> 개체의 편집 메서드를 사용하려고 하면 <xref:System.NotSupportedException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="8bf15-107">편집 가능한 <xref:System.Xml.XPath.XPathNavigator> 개체를 만드는 방법에 대한 자세한 내용은 [XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf15-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="removing-nodes"></a><span data-ttu-id="8bf15-108">노드 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-108">Removing Nodes</span></span>  
 <span data-ttu-id="8bf15-109"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에서 노드를 제거하는 <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-109">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to remove nodes from an XML document.</span></span>  
  
### <a name="removing-a-node"></a><span data-ttu-id="8bf15-110">노드 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-110">Removing a Node</span></span>  
 <span data-ttu-id="8bf15-111"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에서 <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 개체가 현재 위치하고 있는 현재 노드를 삭제하는 <xref:System.Xml.XPath.XPathNavigator> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-111">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to delete the current node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on from an XML document.</span></span>  
  
 <span data-ttu-id="8bf15-112"><xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 메서드를 사용하여 노드를 삭제한 후에는 더 이상 <xref:System.Xml.XmlDocument> 개체의 루트에서 이 노드에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-112">After a node has been deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method, it is no longer reachable from the root of the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="8bf15-113">노드를 삭제한 후 <xref:System.Xml.XPath.XPathNavigator>는 삭제된 노드의 부모 노드에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-113">After a node has been deleted, the <xref:System.Xml.XPath.XPathNavigator> is positioned on the parent node of the deleted node.</span></span>  
  
 <span data-ttu-id="8bf15-114">노드를 삭제해도 삭제된 노드에 위치한 <xref:System.Xml.XPath.XPathNavigator> 개체의 위치에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-114">A delete operation doesn't affect the position of any <xref:System.Xml.XPath.XPathNavigator> object positioned on the deleted node.</span></span> <span data-ttu-id="8bf15-115">이러한 <xref:System.Xml.XPath.XPathNavigator> 개체는 삭제된 하위 트리 내에서 이동할 수 있다는 점에서 유효하지만 <xref:System.Xml.XPath.XPathNavigator> 클래스의 일반 노드 집합 탐색 메서드를 사용하여 기본 노드 트리로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-115">These <xref:System.Xml.XPath.XPathNavigator> objects are valid in the sense that they can move within the deleted subtree, but cannot be moved to the main node tree using the regular node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bf15-116"><xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드를 사용하여 이러한 <xref:System.Xml.XPath.XPathNavigator> 개체를 다시 기본 노드 트리로 이동하거나 기본 노드 트리에서 삭제된 하위 트리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-116">The <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class can be used to move these <xref:System.Xml.XPath.XPathNavigator> objects back into the main node tree, or from the main node tree to the deleted subtree.</span></span>  
  
 <span data-ttu-id="8bf15-117">다음 예제에서는 `price` 메서드를 사용하여 `book` 파일의 첫 번째 `contosoBooks.xml` 요소에서 <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 요소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-117">In the following example, the `price` element of the first `book` element of the `contosoBooks.xml` file is deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span> <span data-ttu-id="8bf15-118"><xref:System.Xml.XPath.XPathNavigator> 요소를 삭제한 후 `price` 개체는 부모 `book` 요소에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-118">The position of the <xref:System.Xml.XPath.XPathNavigator> object after the `price` element is deleted is on the parent `book` element.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="8bf15-119">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-119">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a><span data-ttu-id="8bf15-120">특성 노드 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-120">Removing an Attribute Node</span></span>  
 <span data-ttu-id="8bf15-121"><xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 메서드를 사용하여 XML 문서에서 특성 노드를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-121">Attribute nodes are removed from an XML document using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span>  
  
 <span data-ttu-id="8bf15-122">특성 노드를 삭제한 후에는 더 이상 <xref:System.Xml.XmlDocument> 개체의 루트 노드에서 이 노드에 연결할 수 없으며 <xref:System.Xml.XPath.XPathNavigator> 개체는 부모 요소에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-122">After an attribute node has been deleted, it is no longer reachable from the root node of an <xref:System.Xml.XmlDocument> object and the <xref:System.Xml.XPath.XPathNavigator> object is positioned on the parent element.</span></span>  
  
#### <a name="default-attributes"></a><span data-ttu-id="8bf15-123">기본 특성</span><span class="sxs-lookup"><span data-stu-id="8bf15-123">Default Attributes</span></span>  
 <span data-ttu-id="8bf15-124">특성을 제거하는 데 사용한 메서드와 상관없이 XML 문서의 DTD 또는 XML 스키마에 기본 특성으로 정의된 특성을 제거할 때는 특별한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-124">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the DTD or XML Schema for the XML document.</span></span> <span data-ttu-id="8bf15-125">기본 특성이 속해 있는 요소도 제거해야 기본 특성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-125">Default attributes cannot be removed unless the element they belong to is also removed.</span></span> <span data-ttu-id="8bf15-126">기본 특성을 선언한 요소에 대해 기본 특성이 항상 있으므로 결과적으로 기본 특성을 삭제하면 대체 특성이 요소에 삽입되고 선언된 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-126">Default attributes are always present for elements that have default attributes declared, and as a result, deleting a default attribute results in a replacement attribute being inserted into the element and initialized to the default value that was declared.</span></span>  
  
## <a name="removing-values"></a><span data-ttu-id="8bf15-127">값 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-127">Removing Values</span></span>  
 <span data-ttu-id="8bf15-128"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XML 문서에서 형식화되지 않은 값과 형식화된 값을 제거하는 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 및 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-128">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to remove untyped and typed values from an XML document.</span></span>  
  
### <a name="removing-untyped-values"></a><span data-ttu-id="8bf15-129">형식화되지 않은 값 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-129">Removing Untyped Values</span></span>  
 <span data-ttu-id="8bf15-130"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드는 형식화되지 않은 `string` 값을 간단히 삽입합니다. 이 값은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 값인 매개 변수로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-130">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="8bf15-131">빈 문자열을 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 메서드에 전달하면 현재 노드 값이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-131">Passing an empty string to the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method removes the value of the current node.</span></span>  
  
 <span data-ttu-id="8bf15-132">다음 예제에서는 `price` 메서드를 사용하여 `book` 파일에서 첫 번째 `contosoBooks.xml` 요소의 <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> 요소 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-132">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
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
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="8bf15-133">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-133">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a><span data-ttu-id="8bf15-134">형식화된 값 제거</span><span class="sxs-lookup"><span data-stu-id="8bf15-134">Removing Typed Values</span></span>  
 <span data-ttu-id="8bf15-135">노드의 형식이 W3C XML 스키마 단순 형식이면 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 메서드에서 삽입한 새 값은 설정되기 전에 단순 형식의 패싯에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-135">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="8bf15-136">노드의 형식에 따라 새 값이 유효하지 않은 경우, 예를 들면 `-1` 형식의 요소에 `xs:positiveInteger`의 값을 설정하는 경우에는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-136">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span> <span data-ttu-id="8bf15-137">또한 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>을 매개 변수로 `null` 메서드에 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-137">The <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method also cannot be passed `null` as a parameter.</span></span> <span data-ttu-id="8bf15-138">결과적으로 형식화된 노드 값을 제거하려면 노드의 스키마 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-138">As a result removing the value of a typed node must comply with the schema type of the node.</span></span>  
  
 <span data-ttu-id="8bf15-139">다음 예제에서는 값을 `price`으로 설정하여 `book` 메서드로 `contosoBooks.xml` 파일에서 첫 번째 <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> 요소의 `0` 요소 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-139">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method by setting the value to `0`.</span></span> <span data-ttu-id="8bf15-140">노드 값은 제거되지 않지만 `xs:decimal`의 데이터 형식에 따라 책 가격이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-140">The value of the node is not removed, but the price of the book has been removed according to its data type of `xs:decimal`.</span></span>  
  
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
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
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
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a><span data-ttu-id="8bf15-141">네임스페이스 노드</span><span class="sxs-lookup"><span data-stu-id="8bf15-141">Namespace Nodes</span></span>  
 <span data-ttu-id="8bf15-142"><xref:System.Xml.XmlDocument> 개체에서 네임스페이스 노드를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-142">Namespace nodes cannot be deleted from an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="8bf15-143"><xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> 메서드를 사용하여 네임스페이스 노드를 삭제하려고 시도하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-143">Attempts to delete namespace nodes using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method results in an exception.</span></span>  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="8bf15-144">InnerXml 및 OuterXml 속성</span><span class="sxs-lookup"><span data-stu-id="8bf15-144">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="8bf15-145"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 노드의 XML 태그를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-145">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="8bf15-146"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그를 주어진 XML `string`의 구문 분석된 내용과 함께 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-146">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="8bf15-147">마찬가지로, <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성은 <xref:System.Xml.XPath.XPathNavigator> 개체가 현재 위치하는 자식 노드의 XML 태그뿐만 아니라 현재 노드 자체도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-147">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="8bf15-148">이 항목에 설명된 메서드 외에도 <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성을 사용하여 XML 문서에서 노드와 값을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-148">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="8bf15-149"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 및 <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 속성을 사용하여 노드를 수정하는 방법에 대한 자세한 내용은 [XPathNavigator를 사용하여 XML 데이터 수정](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf15-149">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to modify nodes, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="8bf15-150">XML 문서 저장</span><span class="sxs-lookup"><span data-stu-id="8bf15-150">Saving an XML Document</span></span>  
 <span data-ttu-id="8bf15-151"><xref:System.Xml.XmlDocument> 클래스의 메서드를 사용하면 <xref:System.Xml.XmlDocument> 개체에서 변경된 내용을 이 항목에서 설명하는 메서드의 결과로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf15-151">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="8bf15-152"><xref:System.Xml.XmlDocument> 개체에서 변경된 내용을 저장하는 방법에 대한 자세한 내용은 [문서 작성 및 저장](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf15-152">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf15-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bf15-153">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="8bf15-154">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="8bf15-154">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="8bf15-155">XPathNavigator를 사용하여 XML 데이터 삽입</span><span class="sxs-lookup"><span data-stu-id="8bf15-155">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="8bf15-156">XPathNavigator를 사용하여 XML 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="8bf15-156">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
