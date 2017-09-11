---
title: "XML 트리 (Visual Basic)를 요소, 특성 및 노드 추가 | Microsoft 문서"
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
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8ee26aef896a2f404e815823ade83e204270613
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="663f9-102">XML 트리 (Visual Basic)를 요소, 특성 및 노드 추가</span><span class="sxs-lookup"><span data-stu-id="663f9-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="663f9-103">내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="663f9-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="663f9-104">내용을 추가하는 메서드</span><span class="sxs-lookup"><span data-stu-id="663f9-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="663f9-105">다음 방법 자식 콘텐츠를 추가 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="663f9-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="663f9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="663f9-106">Method</span></span>|<span data-ttu-id="663f9-107">설명</span><span class="sxs-lookup"><span data-stu-id="663f9-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="663f9-108"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="663f9-108"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="663f9-109"><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 끝에 콘텐츠를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="663f9-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="663f9-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="663f9-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="663f9-111"><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 시작 부분에 내용을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="663f9-111">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="663f9-112">다음 방법 <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 의 형제 노드로 내용을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="663f9-112">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="663f9-113"><xref:System.Xml.Linq.XElement>유효한 형제 콘텐츠 노드 <xref:System.Xml.Linq.XText>또는 <xref:System.Xml.Linq.XComment>.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XText> 와 같은 다른 형식에 추가할 수는 있지만,</xref:System.Xml.Linq.XElement> 형제 내용을 추가할 가장 일반적인 노드는</span><span class="sxs-lookup"><span data-stu-id="663f9-113">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="663f9-114">메서드</span><span class="sxs-lookup"><span data-stu-id="663f9-114">Method</span></span>|<span data-ttu-id="663f9-115">설명</span><span class="sxs-lookup"><span data-stu-id="663f9-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="663f9-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="663f9-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="663f9-117"><xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 후 콘텐츠를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="663f9-117">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="663f9-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="663f9-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="663f9-119"><xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="663f9-119">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="663f9-120">예제</span><span class="sxs-lookup"><span data-stu-id="663f9-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="663f9-121">설명</span><span class="sxs-lookup"><span data-stu-id="663f9-121">Description</span></span>  
 <span data-ttu-id="663f9-122">다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="663f9-122">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="663f9-123">코드</span><span class="sxs-lookup"><span data-stu-id="663f9-123">Code</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
  
```  
  
### <a name="comments"></a><span data-ttu-id="663f9-124">설명</span><span class="sxs-lookup"><span data-stu-id="663f9-124">Comments</span></span>  
 <span data-ttu-id="663f9-125">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="663f9-125">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="663f9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="663f9-126">See Also</span></span>  
 [<span data-ttu-id="663f9-127">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="663f9-127">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
