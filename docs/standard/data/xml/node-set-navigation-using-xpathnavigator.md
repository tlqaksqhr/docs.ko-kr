---
title: XPathNavigator를 사용하여 노드 집합 탐색
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6dfba9bb6cd253f4bc866f445a324a046c8cad2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="node-set-navigation-using-xpathnavigator"></a><span data-ttu-id="e7f68-102">XPathNavigator를 사용하여 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="e7f68-102">Node Set Navigation Using XPathNavigator</span></span>
<span data-ttu-id="e7f68-103"><xref:System.Xml.XPath.XPathDocument> 클래스의 노드 집합 탐색 메서드를 사용하여 <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathNavigator> 개체에서 노드를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-103">You can navigate over nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="e7f68-104">모든 노드를 탐색하거나 <xref:System.Xml.XPath.XPathNavigator> 클래스의 선택 메서드에서 하나가 반환한 노드 중 선택한 노드 집합을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-104">You can navigate over all the nodes or over a selected set of nodes returned by one of the selection methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="element-node-set-navigation"></a><span data-ttu-id="e7f68-105">요소 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="e7f68-105">Element Node Set Navigation</span></span>  
 <span data-ttu-id="e7f68-106"><xref:System.Xml.XPath.XPathNavigator> 클래스는 요소 노드를 탐색하는 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-106">The <xref:System.Xml.XPath.XPathNavigator> class provides several methods used to navigate element nodes.</span></span> <span data-ttu-id="e7f68-107">다음 표에서는 사용 가능한 탐색 메서드 및 이러한 메서드의 이동 방법에 대한 설명을 보여 줍니다. 여기에는 특성 및 네임스페이스 노드를 탐색하는 메서드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-107">The following table shows the navigation methods available and a description of how they move; this does not include methods used to navigate attribute and namespace nodes.</span></span>  
  
 <span data-ttu-id="e7f68-108"><xref:System.Xml.XPath.XPathNavigator> 개체에서 노드를 선택하는 방법에 대한 자세한 내용은 [XPathNavigator를 사용하여 XML 데이터 선택, 평가 및 일치시키기](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7f68-108">For more information about selecting nodes in an <xref:System.Xml.XPath.XPathNavigator> object, see [Selecting, Evaluating and Matching XML Data using XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span></span> <span data-ttu-id="e7f68-109">특성 및 네임스페이스 노드 탐색에 대한 자세한 내용은 [XPathNavigator를 사용하여 특성 및 네임스페이스 노드 탐색](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7f68-109">For more information about navigating attribute and namespace nodes, see [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span></span>  
  
|<span data-ttu-id="e7f68-110">메서드</span><span class="sxs-lookup"><span data-stu-id="e7f68-110">Method</span></span>|<span data-ttu-id="e7f68-111">설명</span><span class="sxs-lookup"><span data-stu-id="e7f68-111">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|<span data-ttu-id="e7f68-112">지정된 <xref:System.Xml.XPath.XPathNavigator>와 동일한 위치로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-112">Moves the <xref:System.Xml.XPath.XPathNavigator> to the same position of the <xref:System.Xml.XPath.XPathNavigator> specified.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|<span data-ttu-id="e7f68-113">현재 노드의 자식 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-113">Moves the <xref:System.Xml.XPath.XPathNavigator> to a child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|<span data-ttu-id="e7f68-114">현재 노드의 첫 번째 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-114">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|<span data-ttu-id="e7f68-115">현재 노드의 첫 번째 자식 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-115">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|<span data-ttu-id="e7f68-116">문서 순서에서 지정된 요소로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-116">Moves the <xref:System.Xml.XPath.XPathNavigator> to the specified element in document order.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|<span data-ttu-id="e7f68-117">주어진 <xref:System.Xml.XPath.XPathNavigator>과 값이 일치하는 `ID` 형식의 특성을 갖춘 노드로 <xref:System.String>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-117">Moves the <xref:System.Xml.XPath.XPathNavigator> to the node that has an attribute of type `ID` with a value that matches the given <xref:System.String>.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|<span data-ttu-id="e7f68-118">현재 노드의 다음 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-118">Moves the <xref:System.Xml.XPath.XPathNavigator> to the next sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|<span data-ttu-id="e7f68-119">현재 노드의 부모 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-119">Moves the <xref:System.Xml.XPath.XPathNavigator> to the parent node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|<span data-ttu-id="e7f68-120">현재 노드의 이전 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-120">Moves the <xref:System.Xml.XPath.XPathNavigator> to the previous sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|<span data-ttu-id="e7f68-121">XML 문서의 루트 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-121">Moves the <xref:System.Xml.XPath.XPathNavigator> to the root node of the XML document.</span></span>|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a><span data-ttu-id="e7f68-122">주석 및 처리 명령 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="e7f68-122">Comments and Processing Instruction Node Navigation</span></span>  
 <span data-ttu-id="e7f68-123">다음 <xref:System.Xml.XPath.XPathNavigator> 클래스 메서드를 XML 문서의 다른 노드에서 주석 또는 처리 명령으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7f68-123">The following <xref:System.Xml.XPath.XPathNavigator> class methods are valid for moving to comments or processing instructions from other nodes in an XML document.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a><span data-ttu-id="e7f68-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7f68-124">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="e7f68-125">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="e7f68-125">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="e7f68-126">XPathNavigator를 사용하여 특성 및 네임스페이스 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="e7f68-126">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="e7f68-127">XPathNavigator를 사용하여 XML 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="e7f68-127">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="e7f68-128">XPathNavigator를 사용하여 강력한 형식의 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="e7f68-128">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
