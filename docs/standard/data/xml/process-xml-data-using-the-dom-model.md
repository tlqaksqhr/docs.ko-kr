---
title: "DOM 모델을 사용하여 XML 데이터 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: de7ca0ff08ae7183f92fd7caa1bfe977e01e616d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="4ae37-102">DOM 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="4ae37-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="4ae37-103">XML DOM(문서 개체 모델)은 XML 데이터를 표준 개체 집합으로 간주하며 메모리에서 XML 데이터를 처리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="4ae37-104">`System.Xml` 네임스페이스는 XML 문서, 조각, 노드 또는 노드 집합의 프로그래밍 방식 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="4ae37-105">또한 W3C(World Wide Web 컨소시엄) DOM Level 1 Core 및 DOM Level 2 Core 권장 사항을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="4ae37-106"><xref:System.Xml.XmlDocument> 클래스는 XML 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="4ae37-107">여기에는 다른 모든 XML 개체를 검색하고 만들기 위한 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="4ae37-108"><xref:System.Xml.XmlDocument> 및 관련 클래스를 사용하면 XML 문서를 생성하고, 데이터를 로드, 액세스 및 수정하고 변경 내용을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ae37-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4ae37-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4ae37-110">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="4ae37-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
-   [<span data-ttu-id="4ae37-111">XML 노드 형식</span><span class="sxs-lookup"><span data-stu-id="4ae37-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
-   [<span data-ttu-id="4ae37-112">XML DOM(문서 개체 모델) 계층 구조</span><span class="sxs-lookup"><span data-stu-id="4ae37-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
-   [<span data-ttu-id="4ae37-113">XML 데이터에 개체 계층 구조 매핑</span><span class="sxs-lookup"><span data-stu-id="4ae37-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
-   [<span data-ttu-id="4ae37-114">XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="4ae37-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
-   [<span data-ttu-id="4ae37-115">DOM에 XML 문서 읽어오기</span><span class="sxs-lookup"><span data-stu-id="4ae37-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
-   [<span data-ttu-id="4ae37-116">XML 문서에 노드 삽입</span><span class="sxs-lookup"><span data-stu-id="4ae37-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
-   [<span data-ttu-id="4ae37-117">XML 문서에서 노드, 내용 및 값 제거</span><span class="sxs-lookup"><span data-stu-id="4ae37-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
-   [<span data-ttu-id="4ae37-118">XML 문서에서 노드, 내용 및 값 수정</span><span class="sxs-lookup"><span data-stu-id="4ae37-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
-   [<span data-ttu-id="4ae37-119">DOM에서의 XML 문서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4ae37-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
-   [<span data-ttu-id="4ae37-120">문서 작성 및 저장</span><span class="sxs-lookup"><span data-stu-id="4ae37-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
-   [<span data-ttu-id="4ae37-121">XPath 탐색을 사용하여 노드 선택</span><span class="sxs-lookup"><span data-stu-id="4ae37-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
-   [<span data-ttu-id="4ae37-122">외부 리소스 확인</span><span class="sxs-lookup"><span data-stu-id="4ae37-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
-   [<span data-ttu-id="4ae37-123">XmlNameTable을 사용한 개체 비교</span><span class="sxs-lookup"><span data-stu-id="4ae37-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
-   [<span data-ttu-id="4ae37-124">NamedNodeMap 및 NodeList의 노드 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4ae37-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
-   [<span data-ttu-id="4ae37-125">NodeList 및 NamedNodeMap에 대한 동적 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ae37-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
-   [<span data-ttu-id="4ae37-126">DOM의 네임스페이스 지원</span><span class="sxs-lookup"><span data-stu-id="4ae37-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
-   [<span data-ttu-id="4ae37-127">XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="4ae37-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
-   [<span data-ttu-id="4ae37-128">DOM 확장</span><span class="sxs-lookup"><span data-stu-id="4ae37-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="4ae37-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4ae37-129">Related Sections</span></span>  
 [<span data-ttu-id="4ae37-130">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="4ae37-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="4ae37-131"><xref:System.Xml.XPath.XPathNavigator> 클래스를 사용하여 XML 데이터를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae37-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
