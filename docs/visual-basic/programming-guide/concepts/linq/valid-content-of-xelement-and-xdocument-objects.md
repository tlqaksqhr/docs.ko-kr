---
title: "XElement 및 XDocument Objects2의 올바른 콘텐츠 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ecdcd4c2c0ec61cf248c9e210d42abb750e0546b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="b67d0-102">XElement 및 XDocument 개체의 올바른 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b67d0-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="b67d0-103">이 항목에서는 생성자에 전달될 수 있는 유효한 인수에 대해 설명하고 내용을 요소와 문서에 추가하는 데 사용하는 메서드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="b67d0-104">유효한 내용</span><span class="sxs-lookup"><span data-stu-id="b67d0-104">Valid Content</span></span>  
 <span data-ttu-id="b67d0-105">쿼리는 종종 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> 로 평가</span><span class="sxs-lookup"><span data-stu-id="b67d0-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="b67d0-106">컬렉션을 전달할 수 있습니다 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체는 <xref:System.Xml.Linq.XElement>생성자.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b67d0-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="b67d0-107">따라서 XML 트리를 채우는 데 사용하는 메서드와 생성자에 쿼리의 결과를 내용으로 전달하는 것이 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="b67d0-108">간단한 내용을 추가할 때 다양한 형식이 이 메서드에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="b67d0-109">유효한 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-109">Valid types include the following:</span></span>  
  
-   <span data-ttu-id="b67d0-110"><xref:System.String></xref:System.String></span><span class="sxs-lookup"><span data-stu-id="b67d0-110"><xref:System.String></span></span>  
  
-   <span data-ttu-id="b67d0-111"><xref:System.Double></xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="b67d0-111"><xref:System.Double></span></span>  
  
-   <span data-ttu-id="b67d0-112"><xref:System.Single></xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="b67d0-112"><xref:System.Single></span></span>  
  
-   <span data-ttu-id="b67d0-113"><xref:System.Decimal></xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="b67d0-113"><xref:System.Decimal></span></span>  
  
-   <span data-ttu-id="b67d0-114"><xref:System.Boolean></xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="b67d0-114"><xref:System.Boolean></span></span>  
  
-   <span data-ttu-id="b67d0-115"><xref:System.DateTime></xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="b67d0-115"><xref:System.DateTime></span></span>  
  
-   <span data-ttu-id="b67d0-116"><xref:System.TimeSpan></xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="b67d0-116"><xref:System.TimeSpan></span></span>  
  
-   <span data-ttu-id="b67d0-117"><xref:System.DateTimeOffset></xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="b67d0-117"><xref:System.DateTimeOffset></span></span>  
  
-   <span data-ttu-id="b67d0-118">`Object.ToString`을 구현하는 임의의 형식</span><span class="sxs-lookup"><span data-stu-id="b67d0-118">Any type that implements `Object.ToString`.</span></span>  
  
-   <span data-ttu-id="b67d0-119"><xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 형식</span><span class="sxs-lookup"><span data-stu-id="b67d0-119">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="b67d0-120">복잡한 내용을 추가할 때 다양한 형식이 이 메서드에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-120">When adding complex content, various types can be passed to this method:</span></span>  
  
-   <span data-ttu-id="b67d0-121"><xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="b67d0-121"><xref:System.Xml.Linq.XObject></span></span>  
  
-   <span data-ttu-id="b67d0-122"><xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="b67d0-122"><xref:System.Xml.Linq.XNode></span></span>  
  
-   <span data-ttu-id="b67d0-123"><xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="b67d0-123"><xref:System.Xml.Linq.XAttribute></span></span>  
  
-   <span data-ttu-id="b67d0-124">구현 하는 모든 형식<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b67d0-124">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="b67d0-125">개체를 구현 하는 경우 <xref:System.Collections.Generic.IEnumerable%601>, 개체의 컬렉션이 열거 되 고 컬렉션의 모든 항목이 추가 됩니다.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b67d0-125">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="b67d0-126">컬렉션에 있으면 <xref:System.Xml.Linq.XNode>또는 <xref:System.Xml.Linq.XAttribute>개체를 컬렉션의 각 항목은 개별적으로 추가 됩니다.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="b67d0-126">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="b67d0-127">컬렉션에 텍스트(또는 텍스트로 변환된 개체)가 포함되어 있으면 컬렉션의 텍스트가 연결되어 단일 텍스트 노드로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-127">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="b67d0-128">내용이 `null`이면 아무 것도 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-128">If content is `null`, nothing is added.</span></span> <span data-ttu-id="b67d0-129">컬렉션을 전달할 때 컬렉션의 항목은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-129">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="b67d0-130">컬렉션의 `null` 항목은 트리에 아무 영향도 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-130">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="b67d0-131">추가된 특성은 포함하는 요소에서 고유한 이름을 갖고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-131">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="b67d0-132">추가 하는 경우 <xref:System.Xml.Linq.XNode>또는 <xref:System.Xml.Linq.XAttribute>개체를 새 내용에 부모가 없는 경우 다음 개체 되기만 XML 트리에.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="b67d0-132">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="b67d0-133">새 내용이 이미 부모를 갖고 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-133">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="b67d0-134">문서의 유효한 내용</span><span class="sxs-lookup"><span data-stu-id="b67d0-134">Valid Content for Documents</span></span>  
 <span data-ttu-id="b67d0-135">특성과 간단한 내용은 문서에 추가될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-135">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="b67d0-136">만들 <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> 을 해야 하는 시나리오도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-136">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="b67d0-137">대신 사용 하 여 XML 트리를 일반적으로 만들 수는 <xref:System.Xml.Linq.XElement>루트 노드.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b67d0-137">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="b67d0-138">하지 않는 한 문서를 만듭니다 (예를 들어 때문에 최상위 수준에서 처리 명령과 주석을 만들어야 하거나 문서 형식을 지원 해야 합니다.)는 특정 요구 사항,이 사용 하기 어려운 <xref:System.Xml.Linq.XElement>를 루트 노드로.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b67d0-138">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="b67d0-139">문서의 유효한 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-139">Valid content for a document includes the following:</span></span>  
  
-   <span data-ttu-id="b67d0-140">0 개 또는 한 <xref:System.Xml.Linq.XDocumentType>개체.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="b67d0-140">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="b67d0-141">문서 형식이 요소 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-141">The document types must come before the element.</span></span>  
  
-   <span data-ttu-id="b67d0-142">0개나&1;개의 요소</span><span class="sxs-lookup"><span data-stu-id="b67d0-142">Zero or one element.</span></span>  
  
-   <span data-ttu-id="b67d0-143">0개 이상의 주석</span><span class="sxs-lookup"><span data-stu-id="b67d0-143">Zero or more comments.</span></span>  
  
-   <span data-ttu-id="b67d0-144">0개 이상의 처리 명령</span><span class="sxs-lookup"><span data-stu-id="b67d0-144">Zero or more processing instructions.</span></span>  
  
-   <span data-ttu-id="b67d0-145">공백만 포함된&0;개 이상의 텍스트 노드</span><span class="sxs-lookup"><span data-stu-id="b67d0-145">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="b67d0-146">내용 추가를 허용하는 생성자 및 함수</span><span class="sxs-lookup"><span data-stu-id="b67d0-146">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="b67d0-147">다음 메서드를 사용 <xref:System.Xml.Linq.XElement>하거나 <xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 자식 콘텐츠를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-147">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="b67d0-148">메서드</span><span class="sxs-lookup"><span data-stu-id="b67d0-148">Method</span></span>|<span data-ttu-id="b67d0-149">설명</span><span class="sxs-lookup"><span data-stu-id="b67d0-149">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b67d0-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></span></span>|<span data-ttu-id="b67d0-151"><xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-151">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="b67d0-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></span></span>|<span data-ttu-id="b67d0-153"><xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> 를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-153">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="b67d0-154"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-154"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="b67d0-155">자식 콘텐츠 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 의 끝에 추가</span><span class="sxs-lookup"><span data-stu-id="b67d0-155">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="b67d0-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="b67d0-157"><xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 후 콘텐츠를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-157">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="b67d0-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="b67d0-159"><xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="b67d0-159">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="b67d0-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="b67d0-161"><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 시작 부분에 내용을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="b67d0-161">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="b67d0-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></span></span>|<span data-ttu-id="b67d0-163"><xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 의 모든 콘텐츠 (자식 노드와 특성)를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-163">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="b67d0-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span></span>|<span data-ttu-id="b67d0-165"><xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 의 특성을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-165">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="b67d0-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span></span>|<span data-ttu-id="b67d0-167">자식 노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-167">Replaces the children nodes with new content.</span></span>|  
|<span data-ttu-id="b67d0-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A></span><span class="sxs-lookup"><span data-stu-id="b67d0-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></span></span>|<span data-ttu-id="b67d0-169">노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b67d0-169">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b67d0-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b67d0-170">See Also</span></span>  
 [<span data-ttu-id="b67d0-171">XML 트리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="b67d0-171">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
