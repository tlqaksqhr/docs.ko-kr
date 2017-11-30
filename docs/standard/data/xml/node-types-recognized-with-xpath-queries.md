---
title: "XPath 쿼리에서 인식하는 노드 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c1e48bbfd6388686fdb83f08668f7f0234275a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="e7504-102">XPath 쿼리에서 인식하는 노드 형식</span><span class="sxs-lookup"><span data-stu-id="e7504-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="e7504-103">XPath 쿼리에서 인식하는 노드 형식은 DOM(문서 개체 모델)에 있는 노드 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="e7504-104">W3C XPath 노드 형식</span><span class="sxs-lookup"><span data-stu-id="e7504-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="e7504-105">XPath 쿼리에서 인식하는 노드 형식은 DOM(문서 개체 모델)에 있는 노드 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="e7504-106">다음은 <xref:System.Xml.XPath.XPathNodeType> 열거형이 나타내는 XPath 노드 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNodeType.All>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Element>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Root>  
  
-   <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Text>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="e7504-107">이 노드 형식은 XML 정보 집합에서 노드가 파생되는 XPath 데이터 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="e7504-108"><xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> 및 <xref:System.Xml.XPath.XPathNodeType.Whitespace> 노드 형식은 XPath 데이터 모델에서 설명하는 기본 노드 형식에 대한 Microsoft .NET Framework 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="e7504-109">XPath 데이터 모델에서는 DOM에서와 다른 방식으로 특성 노드 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="e7504-110">XPath 데이터 모델에서 요소 노드는 관련된 특성 노드 집합을 가지고 있으며 요소 노드는 각 특성 노드의 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="e7504-111">그러나 DOM에서 요소 노드는 부모가 아니라 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="e7504-112">두 모델에서 특성 및 네임스페이스 노드는 요소 노드의 자식 노드로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="e7504-113">네임스페이스 노드 형식은 XPath 데이터 모델에 추가된 것이며 인식되는 DOM 노드 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="e7504-114">요소, 특성 및 네임 스페이스 노드를 탐색 하는 방법에 대 한 자세한 내용은 참조는 [노드 집합 탐색을 사용 하 여 XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) 및 [특성 및 XPathNavigator를 사용 하 여 노드 탐색 Namespace](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7504-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7504-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="e7504-116">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="e7504-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="e7504-117">XPathNavigator를 사용 하 여 XML 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7504-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="e7504-118">XPathNavigator를 사용 하 여 XPath 식 계산</span><span class="sxs-lookup"><span data-stu-id="e7504-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="e7504-119">XPathNavigator를 사용 하 여 노드 일치 시키기</span><span class="sxs-lookup"><span data-stu-id="e7504-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="e7504-120">XPath 쿼리 및 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="e7504-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="e7504-121">컴파일된 XPath 식</span><span class="sxs-lookup"><span data-stu-id="e7504-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
