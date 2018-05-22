---
title: XPath 쿼리 및 네임스페이스
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a121f58df93f88af851bbcc85d75e71fc067af78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xpath-queries-and-namespaces"></a><span data-ttu-id="e790e-102">XPath 쿼리 및 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e790e-102">XPath Queries and Namespaces</span></span>
<span data-ttu-id="e790e-103">XPath 쿼리는 XML 문서에서 네임스페이스를 인식하며 네임스페이스 접두사를 사용하여 요소 및 특성 이름을 정규화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-103">XPath queries are aware of namespaces in an XML document and can use namespace prefixes to qualify element and attribute names.</span></span> <span data-ttu-id="e790e-104">네임스페이스 접두사로 요소 및 특성 이름을 정규화하면 XPath 쿼리에 의해 반환되는 노드가 특정 네임스페이스에 속한 노드로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-104">Qualifying element and attribute names with a namespace prefix limits the nodes returned by an XPath query to only those nodes that belong to a specific namespace.</span></span>  
  
 <span data-ttu-id="e790e-105">예를 들어, 접두사 `books`를 네임스페이스 `http://www.contoso.com/books`에 매핑하면 다음 XPath 쿼리 `/books:books/books:book`은 네임스페이스 `book`에 있는 `http://www.contoso.com/books` 요소만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-105">For example if the prefix `books` maps to the namespace `http://www.contoso.com/books`, then the following XPath query `/books:books/books:book` selects only those `book` elements in the namespace `http://www.contoso.com/books`.</span></span>  
  
## <a name="the-xmlnamespacemanager"></a><span data-ttu-id="e790e-106">XmlNamespaceManager</span><span class="sxs-lookup"><span data-stu-id="e790e-106">The XmlNamespaceManager</span></span>  
 <span data-ttu-id="e790e-107">XPath 쿼리에서 네임스페이스를 사용할 수 있도록 <xref:System.Xml.IXmlNamespaceResolver> 클래스와 같은 <xref:System.Xml.XmlNamespaceManager> 인터페이스에서 파생된 개체가 XPath 쿼리에 포함할 네임스페이스 URI 및 접두사로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-107">To use namespaces in an XPath query, an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface like the <xref:System.Xml.XmlNamespaceManager> class is constructed with the namespace URI and prefix to include in the XPath query.</span></span>  
  
 <span data-ttu-id="e790e-108">다음과 같은 방법으로 쿼리에서 <xref:System.Xml.XmlNamespaceManager> 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-108">The <xref:System.Xml.XmlNamespaceManager> object may be used in the query in each of the following ways.</span></span>  
  
-   <span data-ttu-id="e790e-109"><xref:System.Xml.XmlNamespaceManager> 개체의 <xref:System.Xml.XPath.XPathExpression> 메서드를 사용하여 <xref:System.Xml.XPath.XPathExpression.SetContext%2A> 개체를 기존 <xref:System.Xml.XPath.XPathExpression> 개체와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-109">The <xref:System.Xml.XmlNamespaceManager> object is associated with an existing <xref:System.Xml.XPath.XPathExpression> object by using the <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method of the <xref:System.Xml.XPath.XPathExpression> object.</span></span> <span data-ttu-id="e790e-110">또한 XPath 식을 나타내는 문자열과 <xref:System.Xml.XPath.XPathExpression> 개체를 매개 변수로 사용하며 새 <xref:System.Xml.XPath.XPathExpression.Compile%2A> 개체를 반환하는 정적<xref:System.Xml.XmlNamespaceManager> 메서드를 사용하여 새 <xref:System.Xml.XPath.XPathExpression> 개체를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-110">You may also compile a new <xref:System.Xml.XPath.XPathExpression> object using the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method which takes a string representing the XPath expression and an <xref:System.Xml.XmlNamespaceManager> object as parameters and returns a new <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
-   <span data-ttu-id="e790e-111"><xref:System.Xml.XmlNamespaceManager> 개체 자체는 XPath 식을 나타내는 문자열과 함께 허용되는 <xref:System.Xml.XPath.XPathNavigator> 클래스 메서드에 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-111">The <xref:System.Xml.XmlNamespaceManager> object itself is passed as a parameter to an accepting <xref:System.Xml.XPath.XPathNavigator> class method along with a string representing the XPath expression.</span></span>  
  
 <span data-ttu-id="e790e-112">다음은 <xref:System.Xml.XPath.XPathNavigator> 인터페이스에서 파생된 개체를 매개 변수로 사용할 수 있는 <xref:System.Xml.IXmlNamespaceResolver> 클래스의 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-112">The following are the methods of the <xref:System.Xml.XPath.XPathNavigator> class that accept an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface as a parameter.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a><span data-ttu-id="e790e-113">기본 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e790e-113">The Default Namespace</span></span>  
 <span data-ttu-id="e790e-114">다음 XML 문서에서는 빈 접두사가 있는 기본 네임스페이스를 사용하여 `http://www.contoso.com/books` 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-114">In the XML document that follows, the default namespace with an empty prefix is used to declare the `http://www.contoso.com/books` namespace.</span></span>  
  
```xml  
<books xmlns="http://www.example.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="e790e-115">XPath는 빈 접두사를 `null` 네임스페이스로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-115">XPath treats the empty prefix as the `null` namespace.</span></span> <span data-ttu-id="e790e-116">즉, 네임스페이스에 매핑된 접두사만 XPath 쿼리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-116">In other words, only prefixes mapped to namespaces can be used in XPath queries.</span></span> <span data-ttu-id="e790e-117">그러므로 XML 문서의 네임스페이스에 대해 쿼리하려는 경우 기본 네임스페이스라 하더라도 이에 대한 접두사를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-117">This means that if you want to query against a namespace in an XML document, even if it is the default namespace, you need to define a prefix for it.</span></span>  
  
 <span data-ttu-id="e790e-118">예를 들어, 위의 XML 문서에 대한 접두사를 정의하지 않으면 XPath 쿼리 `/books/book`은 결과를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-118">For example, without defining a prefix for the XML document above, the XPath query `/books/book` would not return any results.</span></span>  
  
 <span data-ttu-id="e790e-119">네임스페이스에 없는 일부 노드와 기본 네임스페이스에 있는 일부 노드를 사용하여 문서를 쿼리하는 경우 접두사를 바인딩하여 모호성을 없애야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-119">A prefix must be bound to prevent ambiguity when querying documents with some nodes not in a namespace, and some in a default namespace.</span></span>  
  
 <span data-ttu-id="e790e-120">다음 코드는 기본 네임스페이스에 대한 접두사를 정의하고 `book` 네임스페이스에서 모든 `http://www.contoso.com/books` 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e790e-120">The following code defines a prefix for the default namespace and selects all the `book` elements from the `http://www.contoso.com/books` namespace.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e790e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e790e-121">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="e790e-122">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="e790e-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="e790e-123">XPathNavigator를 사용하여 XML 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="e790e-123">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="e790e-124">XPathNavigator를 사용하여 XPath 식 계산</span><span class="sxs-lookup"><span data-stu-id="e790e-124">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="e790e-125">XPathNavigator를 사용하여 노드 일치시키기</span><span class="sxs-lookup"><span data-stu-id="e790e-125">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="e790e-126">XPath 쿼리에서 인식하는 노드 형식</span><span class="sxs-lookup"><span data-stu-id="e790e-126">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="e790e-127">컴파일된 XPath 식</span><span class="sxs-lookup"><span data-stu-id="e790e-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
