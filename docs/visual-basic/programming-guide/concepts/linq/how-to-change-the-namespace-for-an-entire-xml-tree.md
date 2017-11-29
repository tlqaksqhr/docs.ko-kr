---
title: "방법: 전체 XML 트리에 (Visual Basic)에 대 한는 Namespace를 변경"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1837324b-5cb5-4fa8-95b9-3071efa0f913
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c5ee83840f9d8b4105e7af53008a329dfde37d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-visual-basic"></a><span data-ttu-id="ddf6d-102">방법: 전체 XML 트리에 (Visual Basic)에 대 한는 Namespace를 변경</span><span class="sxs-lookup"><span data-stu-id="ddf6d-102">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>
<span data-ttu-id="ddf6d-103">요소나 특성의 네임스페이스를 프로그래밍 방식으로 변경해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="ddf6d-104">LINQ to XML을 사용하면 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="ddf6d-105"><xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> 속성은 설정될 수 있지만,</span><span class="sxs-lookup"><span data-stu-id="ddf6d-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="ddf6d-106"><xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> 속성은 설정될 수 없습니다. 하지만 쉽게 특성을 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>에 복사하고 기존 특성을 제거한 다음 원하는 새 네임스페이스에 있는 새 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="ddf6d-107">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-107">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddf6d-108">예제</span><span class="sxs-lookup"><span data-stu-id="ddf6d-108">Example</span></span>  
 <span data-ttu-id="ddf6d-109">다음 코드에서는 네임스페이스에 없는 두 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="ddf6d-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="ddf6d-110">각 트리의 네임스페이스를 변경하고 이러한 트리를 단일 트리로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```vb  
Dim tree1 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim tree2 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim ad As XNamespace = "http://www.adatum.com"  
' change the namespace of every element and attribute in the first tree  
For Each el As XElement In tree1.DescendantsAndSelf  
    el.Name = aw.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' change the namespace of every element and attribute in the second tree  
For Each el As XElement In tree2.DescendantsAndSelf()  
    el.Name = ad.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' add attribute namespaces so that the tree will be serialized with  
' the aw and ad namespace prefixes  
tree1.Add( _  
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _  
)  
tree2.Add( _  
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _  
)  
' create a new composite tree  
Dim root As XElement = _  
    <Root>  
        <%= tree1 %>  
        <%= tree2 %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="ddf6d-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf6d-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddf6d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddf6d-112">See Also</span></span>  
 [<span data-ttu-id="ddf6d-113">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddf6d-113">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
