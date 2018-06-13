---
title: (Visual Basic)는 XML 트리에서 요소, 특성 및 노드 제거
ms.date: 07/20/2015
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
ms.openlocfilehash: dbc5cfd7bf6e1f1b77dd14a6771c387fac29d062
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645932"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="70330-102">(Visual Basic)는 XML 트리에서 요소, 특성 및 노드 제거</span><span class="sxs-lookup"><span data-stu-id="70330-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="70330-103">XML 트리를 수정하여 요소, 특성 및 다른 형식의 노드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70330-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="70330-104">XML 문서에서 요소나 특성을 하나만 제거하는 것은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="70330-105">그러나 요소나 특성의 컬렉션을 제거하는 경우 먼저 컬렉션을 목록으로 구체화한 다음 요소나 특성을 목록에서 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="70330-106">가장 좋은 방법은 이 작업을 수행하는 <xref:System.Xml.Linq.Extensions.Remove%2A> 확장 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70330-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="70330-107">이렇게 하는 주요 이유는 XML 트리에서 검색하는 대부분의 컬렉션이 지연된 실행을 사용하여 생성되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="70330-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="70330-108">컬렉션을 먼저 목록으로 구체화하지 않거나 확장명 메서드를 사용하지 않는 경우 특정 유형의 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70330-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="70330-109">자세한 내용은 참조 [혼합 된 선언적 코드/명령적 코드 버그 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="70330-110">다음 메서드는 XML 트리에서 노드와 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="70330-111">메서드</span><span class="sxs-lookup"><span data-stu-id="70330-111">Method</span></span>|<span data-ttu-id="70330-112">설명</span><span class="sxs-lookup"><span data-stu-id="70330-112">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-113">부모에서 <xref:System.Xml.Linq.XAttribute>를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-113">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-114"><xref:System.Xml.Linq.XContainer>에서 자식 노드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-114">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-115"><xref:System.Xml.Linq.XElement>에서 내용과 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-115">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-116"><xref:System.Xml.Linq.XElement>의 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-116">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-117">값으로 `null`을 전달하면 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-117">If you pass `null` for value, then removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-118">값으로 `null`을 전달하면 자식 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-118">If you pass `null` for value, then removes the child element.</span></span>|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-119">부모에서 <xref:System.Xml.Linq.XNode>를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-119">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="70330-120">부모 요소에서 소스 컬렉션의 모든 특성이나 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-120">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="70330-121">예제</span><span class="sxs-lookup"><span data-stu-id="70330-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70330-122">설명</span><span class="sxs-lookup"><span data-stu-id="70330-122">Description</span></span>  
 <span data-ttu-id="70330-123">이 예제에서는 요소를 제거하는 세 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70330-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="70330-124">첫째, 단일 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-124">First, it removes a single element.</span></span> <span data-ttu-id="70330-125">둘째, 요소의 컬렉션을 검색하고 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 연산자를 사용하여 구체화한 다음 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and removes the collection.</span></span> <span data-ttu-id="70330-126">마지막으로, 요소의 컬렉션을 검색하고 <xref:System.Xml.Linq.Extensions.Remove%2A> 확장 메서드를 사용하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="70330-127">대 한 자세한 내용은 <xref:System.Linq.Enumerable.ToList%2A> 연산자 참조 [데이터 형식 변환 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70330-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="70330-128">코드</span><span class="sxs-lookup"><span data-stu-id="70330-128">Code</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a><span data-ttu-id="70330-129">설명</span><span class="sxs-lookup"><span data-stu-id="70330-129">Comments</span></span>  
 <span data-ttu-id="70330-130">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70330-130">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 <span data-ttu-id="70330-131">`Child1`에서는 첫 번째 손자 요소가 제거되었고,</span><span class="sxs-lookup"><span data-stu-id="70330-131">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="70330-132">`Child2`와 `Child3`에서는 모든 손자 요소가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70330-132">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70330-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70330-133">See Also</span></span>  
 [<span data-ttu-id="70330-134">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70330-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
