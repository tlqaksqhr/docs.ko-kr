---
title: "XPathNavigator를 사용하여 XML 데이터 선택"
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
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f63f23b1a07fbe77e77598cd05dcd25ee8ec158
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="select-xml-data-using-xpathnavigator"></a><span data-ttu-id="91e35-102">XPathNavigator를 사용하여 XML 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="91e35-102">Select XML Data Using XPathNavigator</span></span>
<span data-ttu-id="91e35-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XPath 식을 사용하여 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체의 노드 집합을 선택하는 데 사용되는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="91e35-104">선택한 후에는 선택한 노드 집합을 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-104">Once selected, you can iterate over the selected set of nodes.</span></span>  
  
## <a name="xpathnavigator-selection-methods"></a><span data-ttu-id="91e35-105">XPathNavigator 선택 메서드</span><span class="sxs-lookup"><span data-stu-id="91e35-105">XPathNavigator Selection Methods</span></span>  
 <span data-ttu-id="91e35-106"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XPath 식을 사용하여 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체의 노드 집합을 선택하는 데 사용되는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-106">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="91e35-107">또한 <xref:System.Xml.XPath.XPathNavigator> 클래스는 XPath 식을 사용하는 것보다 더 빠르게 상위, 자식 및 하위 노드를 선택할 수 있는 최적화된 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-107">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of optimized methods for selecting ancestor, child and descendant nodes faster than using an XPath expression.</span></span> <span data-ttu-id="91e35-108">선택한 노드 집합이 <xref:System.Xml.XPath.XPathNodeIterator> 개체 또는 <xref:System.Xml.XPath.XPathNavigator> 개체(선택한 노드가 하나일 경우)에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-108">The selected set of nodes is returned in an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
### <a name="selecting-nodes-using-xpath-expressions"></a><span data-ttu-id="91e35-109">XPath 식을 사용하여 노드 선택</span><span class="sxs-lookup"><span data-stu-id="91e35-109">Selecting Nodes Using XPath Expressions</span></span>  
 <span data-ttu-id="91e35-110">XPath 식을 사용하여 노드 집합을 선택하려면 다음 선택 메서드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-110">To select a set of nodes using an XPath expression, use one of the following selection methods.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="91e35-111">이러한 메서드를 호출하면 <xref:System.Xml.XPath.XPathNodeIterator> 개체 또는 <xref:System.Xml.XPath.XPathNavigator> 개체(선택한 노드가 하나일 경우)를 사용하여 자유롭게 탐색할 수 있는 노드 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-111">When called, these methods return a set of nodes that you can navigate freely using an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
 <span data-ttu-id="91e35-112"><xref:System.Xml.XPath.XPathNodeIterator> 개체를 사용하여 탐색해도 개체를 만들 때 사용한 <xref:System.Xml.XPath.XPathNavigator> 개체의 위치에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-112">Navigating with an <xref:System.Xml.XPath.XPathNodeIterator> object does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span> <span data-ttu-id="91e35-113"><xref:System.Xml.XPath.XPathNavigator> 메서드에서 반환된 <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> 개체는 반환된 단일 노드에 위치하며 개체를 만들 때 사용한 <xref:System.Xml.XPath.XPathNavigator> 개체의 위치에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-113">The <xref:System.Xml.XPath.XPathNavigator> object returned from the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> methods is positioned on the single returned node and also does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span>  
  
 <span data-ttu-id="91e35-114">다음 예제에서는 <xref:System.Xml.XPath.XPathNavigator> 개체로부터 <xref:System.Xml.XPath.XPathDocument> 개체를 만들고 <xref:System.Xml.XPath.XPathNavigator.Select%2A> 메서드를 사용하여 <xref:System.Xml.XPath.XPathDocument> 개체에서 노드를 선택하고 <xref:System.Xml.XPath.XPathNodeIterator> 개체를 사용하여 선택한 노드를 반복하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-114">The following example shows the creation of an <xref:System.Xml.XPath.XPathNavigator> object from an <xref:System.Xml.XPath.XPathDocument> object, the use of the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method to select nodes in the <xref:System.Xml.XPath.XPathDocument> object, and the use of the <xref:System.Xml.XPath.XPathNodeIterator> object to iterate over the selected nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 <span data-ttu-id="91e35-115">이 예제에서는 `books.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-115">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a><span data-ttu-id="91e35-116">최적화된 선택 메서드</span><span class="sxs-lookup"><span data-stu-id="91e35-116">Optimized Selection Methods</span></span>  
 <span data-ttu-id="91e35-117"><xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 메서드는 일반적으로 자식, 하위 및 상위 노드를 검색하는 데 사용하는 XPath 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-117">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class represent XPath expressions commonly used to retrieve child, descendant, and ancestor nodes.</span></span> <span data-ttu-id="91e35-118">이러한 메서드는 성능을 위해 최적화되었으며 해당 XPath 식보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-118">These methods are optimized for performance and are faster than their corresponding XPath expressions.</span></span> <span data-ttu-id="91e35-119"><xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> 및 <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> 메서드는 선택할 노드의 <xref:System.Xml.XPath.XPathNodeType> 값 또는 로컬 이름과 네임스페이스 URI를 기반으로 상위, 자식 및 하위 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-119">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods selects ancestor, child, and descendant nodes based on an <xref:System.Xml.XPath.XPathNodeType> value or the local name and namespace URI of the nodes to select.</span></span> <span data-ttu-id="91e35-120">선택된 상위, 자식 및 하위 노드는 <xref:System.Xml.XPath.XPathNodeIterator> 개체에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e35-120">The selected ancestor, child, and descendant nodes are returned in an <xref:System.Xml.XPath.XPathNodeIterator> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e35-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91e35-121">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="91e35-122">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="91e35-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="91e35-123">XPathNavigator를 사용 하 여 XPath 식 계산</span><span class="sxs-lookup"><span data-stu-id="91e35-123">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="91e35-124">XPathNavigator를 사용 하 여 노드 일치 시키기</span><span class="sxs-lookup"><span data-stu-id="91e35-124">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="91e35-125">XPath 쿼리에서 인식 하는 노드 형식</span><span class="sxs-lookup"><span data-stu-id="91e35-125">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="91e35-126">XPath 쿼리 및 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="91e35-126">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="91e35-127">컴파일된 XPath 식</span><span class="sxs-lookup"><span data-stu-id="91e35-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
