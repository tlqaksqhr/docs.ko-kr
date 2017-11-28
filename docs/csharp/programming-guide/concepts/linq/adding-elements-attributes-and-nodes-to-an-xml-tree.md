---
title: "요소, 특성 및 노드를 XML 트리에 추가(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bbe7d00dc1a0b0ad5dcc7cbbedb1f2886f6ff2de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="5e49e-102">요소, 특성 및 노드를 XML 트리에 추가(C#)</span><span class="sxs-lookup"><span data-stu-id="5e49e-102">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="5e49e-103">내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="5e49e-104">내용을 추가하는 메서드</span><span class="sxs-lookup"><span data-stu-id="5e49e-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="5e49e-105">다음 메서드는 자식 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="5e49e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5e49e-106">Method</span></span>|<span data-ttu-id="5e49e-107">설명</span><span class="sxs-lookup"><span data-stu-id="5e49e-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="5e49e-108"><xref:System.Xml.Linq.XContainer>의 자식 내용 끝 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="5e49e-109"><xref:System.Xml.Linq.XContainer>의 자식 내용 시작 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="5e49e-110">다음 메서드는 <xref:System.Xml.Linq.XNode>의 형제 노드로 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="5e49e-111">유효한 형제 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XText>와 같은 다른 형식의 노드에 추가할 수 있지만, 형제 내용을 추가할 가장 일반적인 노드는 <xref:System.Xml.Linq.XComment>입니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="5e49e-112">메서드</span><span class="sxs-lookup"><span data-stu-id="5e49e-112">Method</span></span>|<span data-ttu-id="5e49e-113">설명</span><span class="sxs-lookup"><span data-stu-id="5e49e-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="5e49e-114"><xref:System.Xml.Linq.XNode> 뒤에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="5e49e-115"><xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5e49e-116">예제</span><span class="sxs-lookup"><span data-stu-id="5e49e-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5e49e-117">설명</span><span class="sxs-lookup"><span data-stu-id="5e49e-117">Description</span></span>  
 <span data-ttu-id="5e49e-118">다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5e49e-119">코드</span><span class="sxs-lookup"><span data-stu-id="5e49e-119">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",   
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="5e49e-120">설명</span><span class="sxs-lookup"><span data-stu-id="5e49e-120">Comments</span></span>  
 <span data-ttu-id="5e49e-121">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e49e-121">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e49e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e49e-122">See Also</span></span>  
 [<span data-ttu-id="5e49e-123">XML 트리 수정(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5e49e-123">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
