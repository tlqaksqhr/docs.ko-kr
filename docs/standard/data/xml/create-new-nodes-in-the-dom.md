---
title: "DOM에서 새 노드 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec624a02f98fda4352b5ba8ff43681fba040c676
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="cb99b-102">DOM에서 새 노드 만들기</span><span class="sxs-lookup"><span data-stu-id="cb99b-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="cb99b-103"><xref:System.Xml.XmlDocument>에는 모든 노드 형식에 대한 create 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="cb99b-104">필요에 따라 메서드에 이름을 제공하고, 텍스트 노드처럼 내용이 있는 노드에 대한 내용이나 기타 매개 변수를 지정하면 노드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="cb99b-105">다음은 적합한 노드를 만들기 위해 이름 및 몇 개의 매개 변수를 제공해야 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="cb99b-106">다른 노드 형식에는 매개 변수에 데이터를 제공하는 것 이상의 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="cb99b-107">특성에 대 한 자세한 내용은 참조 하십시오. [DOM에서 요소의 새 특성 만들기](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="cb99b-108">요소 및 특성 이름 유효성 검사에 대 한 자세한 내용은 참조 하십시오. [XML 요소 및 특성 이름 확인을 만들 때 새 노드](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="cb99b-109">참조 엔터티 참조를 만드는 [새 엔터티 참조 만들기](../../../../docs/standard/data/xml/creating-new-entity-references.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-109">For creating entity references, see [Creating New Entity References](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span></span> <span data-ttu-id="cb99b-110">네임 스페이스 엔터티 참조의 확장에 미치는 영향에 대 한 정보를 참조 하십시오. [새 노드가 포함 된 요소와 특성에 대 한 엔터티 참조 확장에 Namespace 영향](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="cb99b-111">새 노드를 만든 후에 트리에 해당 노드를 삽입하는 데 사용할 수 있는 몇 가지 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="cb99b-112">다음 표에는 XML DOM(문서 개체 모델)에서 새 노드가 나타나는 위치에 대한 설명과 함께 해당 메서드가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="cb99b-113">메서드</span><span class="sxs-lookup"><span data-stu-id="cb99b-113">Method</span></span>|<span data-ttu-id="cb99b-114">노드 배치</span><span class="sxs-lookup"><span data-stu-id="cb99b-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="cb99b-115">참조 노드 앞에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-115">Inserted before the reference node.</span></span> <span data-ttu-id="cb99b-116">예를 들어, 위치 5에 새 노드를 삽입하려면 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="cb99b-117">자세한 내용은 <xref:System.Xml.XmlNode.InsertBefore%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb99b-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="cb99b-118">참조 노드 다음에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-118">Inserted after the reference node.</span></span> <span data-ttu-id="cb99b-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="cb99b-120">자세한 내용은 <xref:System.Xml.XmlNode.InsertAfter%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb99b-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="cb99b-121">노드를 지정된 노드의 자식 노드 목록 끝에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="cb99b-122">추가되는 노드가 <xref:System.Xml.XmlDocumentFragment>이면 문서 조각의 전체 내용이 이 노드의 자식 목록으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="cb99b-123">자세한 내용은 <xref:System.Xml.XmlNode.AppendChild%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb99b-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="cb99b-124">노드를 지정된 노드의 자식 노드 목록 시작 부분에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="cb99b-125">추가되는 노드가 <xref:System.Xml.XmlDocumentFragment>이면 문서 조각의 전체 내용이 이 노드의 자식 목록으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="cb99b-126">자세한 내용은 <xref:System.Xml.XmlNode.PrependChild%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb99b-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="cb99b-127"><xref:System.Xml.XmlAttribute> 노드를 요소와 연관된 특성 컬렉션의 끝에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb99b-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="cb99b-128">자세한 내용은 <xref:System.Xml.XmlAttributeCollection.Append%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb99b-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb99b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb99b-129">See Also</span></span>  
 [<span data-ttu-id="cb99b-130">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="cb99b-130">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
