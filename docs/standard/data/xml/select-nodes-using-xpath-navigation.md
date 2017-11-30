---
title: "XPath 탐색을 사용하여 노드 선택"
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
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34fe3d74adc94930710cf7ee55013b471a2bd43c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="select-nodes-using-xpath-navigation"></a><span data-ttu-id="b580b-102">XPath 탐색을 사용하여 노드 선택</span><span class="sxs-lookup"><span data-stu-id="b580b-102">Select Nodes Using XPath Navigation</span></span>
<span data-ttu-id="b580b-103">XML DOM(문서 개체 모델)에는 XPath(XML Path Language) 탐색을 사용하여 DOM의 정보를 쿼리할 수 있는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-103">The XML Document Object Model (DOM) contains methods that allow you to use XML Path Language (XPath) navigation to query information in the DOM.</span></span> <span data-ttu-id="b580b-104">XPath를 사용하여 단일 노드를 찾거나 특정 기준과 일치하는 모든 노드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-104">You can use XPath to find a single, specific node or to find all nodes that match some criteria.</span></span>  
  
## <a name="xpath-select-methods"></a><span data-ttu-id="b580b-105">XPath Select 메서드</span><span class="sxs-lookup"><span data-stu-id="b580b-105">XPath Select Methods</span></span>  
 <span data-ttu-id="b580b-106">DOM 클래스는 XPath 선택을 위해 <xref:System.Xml.XmlNode.SelectSingleNode%2A> 메서드와 <xref:System.Xml.XmlNode.SelectNodes%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-106">The DOM classes provide two methods for XPath selection: the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method and the <xref:System.Xml.XmlNode.SelectNodes%2A> method.</span></span> <span data-ttu-id="b580b-107"><xref:System.Xml.XmlNode.SelectSingleNode%2A> 메서드는 선택 기준과 일치하는 첫 번째 노드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-107">The <xref:System.Xml.XmlNode.SelectSingleNode%2A> method returns the first node that matches the selection criteria.</span></span> <span data-ttu-id="b580b-108"><xref:System.Xml.XmlNode.SelectNodes%2A> 메서드는 일치하는 노드가 포함된 <xref:System.Xml.XmlNodeList>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-108">The <xref:System.Xml.XmlNode.SelectNodes%2A> method returns an <xref:System.Xml.XmlNodeList> that contains the matching nodes.</span></span>  
  
 <span data-ttu-id="b580b-109">다음 예제에서는 <xref:System.Xml.XmlNode.SelectSingleNode%2A> 메서드를 사용하여 저자의 성이 지정된 기준을 충족하는 첫 번째 `book` 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-109">The following example uses the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method to select the first `book` node in which the author's last name meets the specified criteria.</span></span> <span data-ttu-id="b580b-110">이 항목의 끝에서 제공되는 bookstore.xml 파일이 입력 파일로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-110">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's   
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's   
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 <span data-ttu-id="b580b-111">다음 예제에서는 <xref:System.Xml.XmlNode.SelectNodes%2A> 메서드를 사용하여 가격이 지정된 금액보다 높은 모든 책 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-111">The next example uses the <xref:System.Xml.XmlNode.SelectNodes%2A> method to select all the book nodes in which the price is greater than a specified amount.</span></span> <span data-ttu-id="b580b-112">선택된 목록에 있는 각 책의 가격은 프로그래밍 방식으로 10% 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-112">The price for each book in the selected list is then programmatically reduced by ten percent.</span></span> <span data-ttu-id="b580b-113">마지막으로, 업데이트된 파일이 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-113">Finally, the updated file is written to the console.</span></span> <span data-ttu-id="b580b-114">이 항목의 끝에서 제공되는 bookstore.xml 파일이 입력 파일로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-114">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 <span data-ttu-id="b580b-115">위의 예제에서는 문서 요소에서 XPath 쿼리를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-115">The examples above start the XPath query at the document element.</span></span> <span data-ttu-id="b580b-116">XPath 쿼리의 시작 지점을 설정하면 XPath 쿼리의 시작점인 컨텍스트 노드가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-116">Setting the starting point for the XPath query sets the context node, which is the starting point for the XPath query.</span></span> <span data-ttu-id="b580b-117">문서 요소에서 시작하지 않고 문서 요소의 첫 번째 자식에서 시작하려면 다음과 같이 select 문을 코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-117">If you do not want to start at the document element, but want to start from the first child of the document element, you can code the select statement as follows:</span></span>  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 <span data-ttu-id="b580b-118">모든 <xref:System.Xml.XmlNodeList> 개체는 기본 문서와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-118">All <xref:System.Xml.XmlNodeList> objects are synchronized with the underlying document.</span></span> <span data-ttu-id="b580b-119">그러므로 노드 목록을 반복하고 노드 값을 수정하는 경우 원래 노드가 있는 문서에서도 이 노드가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-119">Therefore, if you iterate through the node list and modify the value of a node, that node is also updated in the document it came from.</span></span> <span data-ttu-id="b580b-120">이전 예제에서는 노드가 선택된 <xref:System.Xml.XmlNodeList>에서 수정될 때 기본 문서도 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-120">Notice in the previous example that when a node is modified in the selected <xref:System.Xml.XmlNodeList> the underlying document is also modified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b580b-121">기본 문서를 수정한 경우 select 문을 다시 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-121">When the underlying document is modified, it is advisable to rerun the select.</span></span> <span data-ttu-id="b580b-122">수정된 노드가 이전에 없던 노드를 노드 목록에 추가하거나 제거할 수 있는 노드라면 노드 목록이 정확하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-122">If the node modified is one that could cause the node to be added to the node list when it was not previously, or would now cause it to be removed from the node list, there is no guarantee that the node list is now accurate.</span></span>  
  
## <a name="namespaces-in-xpath-expressions"></a><span data-ttu-id="b580b-123">XPath 식의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b580b-123">Namespaces in XPath Expressions</span></span>  
 <span data-ttu-id="b580b-124">XPath 식에 네임스페이스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-124">XPath expressions can include namespaces.</span></span> <span data-ttu-id="b580b-125">네임스페이스는 <xref:System.Xml.XmlNamespaceManager>를 사용하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-125">Namespace resolution is supported using the <xref:System.Xml.XmlNamespaceManager>.</span></span> <span data-ttu-id="b580b-126">XPath 식에 접두사가 포함된 경우 접두사와 네임스페이스 URI 쌍을 <xref:System.Xml.XmlNamespaceManager>에 추가해야 하며 <xref:System.Xml.XmlNamespaceManager>는 <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> 또는 <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29> 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-126">If the XPath expression includes a prefix, the prefix and namespace URI pair must be added to the <xref:System.Xml.XmlNamespaceManager>, and the <xref:System.Xml.XmlNamespaceManager> is passed to the <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> or <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29> method.</span></span> <span data-ttu-id="b580b-127">위의 코드 예제에서는 <xref:System.Xml.XmlNamespaceManager>를 사용하여 bookstore.xml 문서의 네임스페이스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-127">Notice that the code examples above use the <xref:System.Xml.XmlNamespaceManager> to resolve the namespace of the bookstore.xml document.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b580b-128">XPath 식에 접두사가 포함되지 않은 경우 네임스페이스 URI(Uniform Resource Identifier)를 빈 네임스페이스로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-128">If the XPath expression does not include a prefix, it is assumed that the namespace Uniform Resource Identifier (URI) is the empty namespace.</span></span> <span data-ttu-id="b580b-129">XML에 기본 네임스페이스가 포함된 경우에도 접두사 및 네임스페이스 URI를 <xref:System.Xml.XmlNamespaceManager>에 추가해야 합니다. 이렇게 하지 않으면 노드를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-129">If your XML includes a default namespace, you must still add a prefix and namespace URI to the <xref:System.Xml.XmlNamespaceManager>; otherwise, no nodes will be selected.</span></span>  
  
#### <a name="input-file"></a><span data-ttu-id="b580b-130">입력 파일</span><span class="sxs-lookup"><span data-stu-id="b580b-130">Input File</span></span>  
 <span data-ttu-id="b580b-131">다음은 이 항목의 예제에서 입력 파일로 사용되는 bookstore.xml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b580b-131">The following is the bookstore.xml file that is used as the input file in the examples in this topic:</span></span>  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b580b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b580b-132">See Also</span></span>  
 [<span data-ttu-id="b580b-133">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="b580b-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
