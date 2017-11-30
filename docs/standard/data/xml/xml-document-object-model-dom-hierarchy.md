---
title: "XML DOM(문서 개체 모델) 계층 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="ceee7-102">XML DOM(문서 개체 모델) 계층 구조</span><span class="sxs-lookup"><span data-stu-id="ceee7-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="ceee7-103">다음 그림은 관련 위치에 클래스 이름과 함께 괄호 안에 W3C(World Wide Web 컨소시엄) 이름을 표시하여 XML DOM(문서 개체 모델)에 대한 클래스 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="ceee7-104">![XML 문서 개체 모델 &#40; DOM &#41; 계층 구조](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="ceee7-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="ceee7-105">XML DOM(문서 개체 모델) 계층 구조</span><span class="sxs-lookup"><span data-stu-id="ceee7-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="ceee7-106">다음 클래스에서 상속 하지 않습니다는 **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="ceee7-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="ceee7-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="ceee7-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="ceee7-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="ceee7-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="ceee7-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="ceee7-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="ceee7-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="ceee7-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="ceee7-111">**XmlImplementation** 클래스는 XML 문서를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="ceee7-112">자세한 내용은 참조 [XML 문서 만들기](../../../../docs/standard/data/xml/xml-document-creation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="ceee7-113">**XmlNamedNodeMap** 클래스를 순서가 지정 되지 않은 노드 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="ceee7-114">자세한 내용은 참조 [이름 또는 인덱스 별로 정렬 되지 않은 노드 검색](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="ceee7-115">**XmlNodeList** 클래스는 정렬 된 노드 목록을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="ceee7-116">자세한 내용은 참조 [인덱스 별로 정렬 된 노드 검색](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="ceee7-117">**XmlNodeChangedEventArgs** 에 등록 된 이벤트 처리기를 처리 하는 클래스는 **XmlDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="ceee7-118">자세한 내용은 참조 [XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="ceee7-119">**XmlLinkedNode** 클래스에서 상속 **XmlNode**합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="ceee7-120">메서드를 재정의 하기 위한 것 **XmlNode**:는 **PreviousSibling** 및 **NextSibling** 메서드.</span><span class="sxs-lookup"><span data-stu-id="ceee7-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="ceee7-121">이러한 재정의 된 메서드는 다음에서 상속 되며 사용 **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, 및 **XmlProcessingInstruction**, 이전 및 다음 형제 클래스인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceee7-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceee7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceee7-122">See Also</span></span>  
 [<span data-ttu-id="ceee7-123">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="ceee7-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
