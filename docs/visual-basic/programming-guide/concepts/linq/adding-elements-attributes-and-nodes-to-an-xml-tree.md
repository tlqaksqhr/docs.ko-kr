---
title: "요소, 특성 및 노드 (Visual Basic)를 XML 트리에 추가"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 710397e2a2a200dc5129ed42ca34f25617a071c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="20b98-102">요소, 특성 및 노드 (Visual Basic)를 XML 트리에 추가</span><span class="sxs-lookup"><span data-stu-id="20b98-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="20b98-103">내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="20b98-104">내용을 추가하는 메서드</span><span class="sxs-lookup"><span data-stu-id="20b98-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="20b98-105">다음 메서드는 자식 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="20b98-106">메서드</span><span class="sxs-lookup"><span data-stu-id="20b98-106">Method</span></span>|<span data-ttu-id="20b98-107">설명</span><span class="sxs-lookup"><span data-stu-id="20b98-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="20b98-108"><xref:System.Xml.Linq.XContainer>의 자식 내용 끝 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="20b98-109"><xref:System.Xml.Linq.XContainer>의 자식 내용 시작 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="20b98-110">다음 메서드는 <xref:System.Xml.Linq.XNode>의 형제 노드로 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="20b98-111">유효한 형제 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XText>와 같은 다른 형식의 노드에 추가할 수 있지만, 형제 내용을 추가할 가장 일반적인 노드는 <xref:System.Xml.Linq.XComment>입니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="20b98-112">메서드</span><span class="sxs-lookup"><span data-stu-id="20b98-112">Method</span></span>|<span data-ttu-id="20b98-113">설명</span><span class="sxs-lookup"><span data-stu-id="20b98-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="20b98-114"><xref:System.Xml.Linq.XNode> 뒤에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="20b98-115"><xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="20b98-116">예제</span><span class="sxs-lookup"><span data-stu-id="20b98-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="20b98-117">설명</span><span class="sxs-lookup"><span data-stu-id="20b98-117">Description</span></span>  
 <span data-ttu-id="20b98-118">다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="20b98-119">코드</span><span class="sxs-lookup"><span data-stu-id="20b98-119">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="20b98-120">설명</span><span class="sxs-lookup"><span data-stu-id="20b98-120">Comments</span></span>  
 <span data-ttu-id="20b98-121">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20b98-121">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20b98-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b98-122">See Also</span></span>  
 [<span data-ttu-id="20b98-123">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20b98-123">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
