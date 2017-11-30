---
title: "XPathNavigator를 사용하여 노드 집합 탐색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ac0135227599d6a72813bcf57b209705545da66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="node-set-navigation-using-xpathnavigator"></a><span data-ttu-id="6fdec-102">XPathNavigator를 사용하여 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="6fdec-102">Node Set Navigation Using XPathNavigator</span></span>
<span data-ttu-id="6fdec-103"><xref:System.Xml.XPath.XPathDocument> 클래스의 노드 집합 탐색 메서드를 사용하여 <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathNavigator> 개체에서 노드를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-103">You can navigate over nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="6fdec-104">모든 노드를 탐색하거나 <xref:System.Xml.XPath.XPathNavigator> 클래스의 선택 메서드에서 하나가 반환한 노드 중 선택한 노드 집합을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-104">You can navigate over all the nodes or over a selected set of nodes returned by one of the selection methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="element-node-set-navigation"></a><span data-ttu-id="6fdec-105">요소 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="6fdec-105">Element Node Set Navigation</span></span>  
 <span data-ttu-id="6fdec-106"><xref:System.Xml.XPath.XPathNavigator> 클래스는 요소 노드를 탐색하는 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-106">The <xref:System.Xml.XPath.XPathNavigator> class provides several methods used to navigate element nodes.</span></span> <span data-ttu-id="6fdec-107">다음 표에서는 사용 가능한 탐색 메서드 및 이러한 메서드의 이동 방법에 대한 설명을 보여 줍니다. 여기에는 특성 및 네임스페이스 노드를 탐색하는 메서드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-107">The following table shows the navigation methods available and a description of how they move; this does not include methods used to navigate attribute and namespace nodes.</span></span>  
  
 <span data-ttu-id="6fdec-108">에 대 한 노드를 선택 하는 방법에 대 한 자세한 내용은 <xref:System.Xml.XPath.XPathNavigator> 개체, 참조 [선택, 평가 및 XPathNavigator를 사용 하 여 일치 하는 XML 데이터](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-108">For more information about selecting nodes in an <xref:System.Xml.XPath.XPathNavigator> object, see [Selecting, Evaluating and Matching XML Data using XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span></span> <span data-ttu-id="6fdec-109">특성 및 네임 스페이스 노드를 탐색 하는 방법에 대 한 자세한 내용은 참조 [특성 및 XPathNavigator를 사용 하 여 노드 탐색 Namespace](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-109">For more information about navigating attribute and namespace nodes, see [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span></span>  
  
|<span data-ttu-id="6fdec-110">메서드</span><span class="sxs-lookup"><span data-stu-id="6fdec-110">Method</span></span>|<span data-ttu-id="6fdec-111">설명</span><span class="sxs-lookup"><span data-stu-id="6fdec-111">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|<span data-ttu-id="6fdec-112">지정된 <xref:System.Xml.XPath.XPathNavigator>와 동일한 위치로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-112">Moves the <xref:System.Xml.XPath.XPathNavigator> to the same position of the <xref:System.Xml.XPath.XPathNavigator> specified.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|<span data-ttu-id="6fdec-113">현재 노드의 자식 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-113">Moves the <xref:System.Xml.XPath.XPathNavigator> to a child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|<span data-ttu-id="6fdec-114">현재 노드의 첫 번째 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-114">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|<span data-ttu-id="6fdec-115">현재 노드의 첫 번째 자식 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-115">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|<span data-ttu-id="6fdec-116">문서 순서에서 지정된 요소로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-116">Moves the <xref:System.Xml.XPath.XPathNavigator> to the specified element in document order.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|<span data-ttu-id="6fdec-117">주어진 <xref:System.Xml.XPath.XPathNavigator>과 값이 일치하는 `ID` 형식의 특성을 갖춘 노드로 <xref:System.String>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-117">Moves the <xref:System.Xml.XPath.XPathNavigator> to the node that has an attribute of type `ID` with a value that matches the given <xref:System.String>.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|<span data-ttu-id="6fdec-118">현재 노드의 다음 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-118">Moves the <xref:System.Xml.XPath.XPathNavigator> to the next sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|<span data-ttu-id="6fdec-119">현재 노드의 부모 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-119">Moves the <xref:System.Xml.XPath.XPathNavigator> to the parent node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|<span data-ttu-id="6fdec-120">현재 노드의 이전 형제 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-120">Moves the <xref:System.Xml.XPath.XPathNavigator> to the previous sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|<span data-ttu-id="6fdec-121">XML 문서의 루트 노드로 <xref:System.Xml.XPath.XPathNavigator>를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-121">Moves the <xref:System.Xml.XPath.XPathNavigator> to the root node of the XML document.</span></span>|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a><span data-ttu-id="6fdec-122">주석 및 처리 명령 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="6fdec-122">Comments and Processing Instruction Node Navigation</span></span>  
 <span data-ttu-id="6fdec-123">다음 <xref:System.Xml.XPath.XPathNavigator> 클래스 메서드를 XML 문서의 다른 노드에서 주석 또는 처리 명령으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-123">The following <xref:System.Xml.XPath.XPathNavigator> class methods are valid for moving to comments or processing instructions from other nodes in an XML document.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a><span data-ttu-id="6fdec-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fdec-124">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="6fdec-125">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6fdec-125">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="6fdec-126">특성 및 XPathNavigator를 사용 하 여 Namespace 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="6fdec-126">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="6fdec-127">XPathNavigator를 사용 하 여 XML 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdec-127">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6fdec-128">강력한 형식의 XPathNavigator를 사용 하 여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="6fdec-128">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
