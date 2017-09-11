---
title: "요소, 특성 및 XML Tree1에서 노드를 수정 합니다. | Microsoft 문서"
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
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88531f2af88074f4406c4859354860829efda69f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="7ce36-102">XML 트리에서 요소, 특성 및 노드 수정</span><span class="sxs-lookup"><span data-stu-id="7ce36-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="7ce36-103">다음 표에는 요소, 해당 요소의 자식 요소 또는 특성을 수정하는 데 사용할 수 있는 메서드와 속성이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="7ce36-104">다음 방법 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 수정</span><span class="sxs-lookup"><span data-stu-id="7ce36-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="7ce36-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7ce36-105">Method</span></span>|<span data-ttu-id="7ce36-106">설명</span><span class="sxs-lookup"><span data-stu-id="7ce36-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7ce36-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-108">요소를 구문 분석된 XML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-108">Replaces an element with parsed XML.</span></span>|  
|<span data-ttu-id="7ce36-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-110">요소의 모든 내용(자식 노드와 특성)을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-110">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="7ce36-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-112">요소의 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-112">Removes the attributes of an element.</span></span>|  
|<span data-ttu-id="7ce36-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-114">요소의 모든 내용(자식 노드와 특성)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-114">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="7ce36-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-116">요소의 특성을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-116">Replaces the attributes of an element.</span></span>|  
|<span data-ttu-id="7ce36-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-118">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-118">Sets the value of an attribute.</span></span> <span data-ttu-id="7ce36-119">특성이 없으면 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-119">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="7ce36-120">값이 `null`로 설정되어 있으면 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-120">If the value is set to `null`, removes the attribute.</span></span>|  
|<span data-ttu-id="7ce36-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-122">자식 요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-122">Sets the value of a child element.</span></span> <span data-ttu-id="7ce36-123">요소가 없으면 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-123">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="7ce36-124">값이 `null`로 설정되어 있으면 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-124">If the value is set to `null`, removes the element.</span></span>|  
|<span data-ttu-id="7ce36-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-126">요소의 내용(자식 노드)을 지정된 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-126">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<span data-ttu-id="7ce36-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-128">요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-128">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="7ce36-129">다음 방법 <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> 수정</span><span class="sxs-lookup"><span data-stu-id="7ce36-129">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="7ce36-130">메서드</span><span class="sxs-lookup"><span data-stu-id="7ce36-130">Method</span></span>|<span data-ttu-id="7ce36-131">설명</span><span class="sxs-lookup"><span data-stu-id="7ce36-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7ce36-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-133">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-133">Sets the value of an attribute.</span></span>|  
|<span data-ttu-id="7ce36-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-135">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-135">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="7ce36-136">다음 메서드를 수정 된 <xref:System.Xml.Linq.XNode>(포함 하는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="7ce36-136">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="7ce36-137">메서드</span><span class="sxs-lookup"><span data-stu-id="7ce36-137">Method</span></span>|<span data-ttu-id="7ce36-138">설명</span><span class="sxs-lookup"><span data-stu-id="7ce36-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7ce36-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-140">노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-140">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="7ce36-141">다음 메서드를 수정 된 <xref:System.Xml.Linq.XContainer>(한 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="7ce36-141">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="7ce36-142">메서드</span><span class="sxs-lookup"><span data-stu-id="7ce36-142">Method</span></span>|<span data-ttu-id="7ce36-143">설명</span><span class="sxs-lookup"><span data-stu-id="7ce36-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7ce36-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7ce36-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="7ce36-145">자식 노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ce36-145">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ce36-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ce36-146">See Also</span></span>  
 [<span data-ttu-id="7ce36-147">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ce36-147">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
