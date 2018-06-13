---
title: '방법: LINQ to (Visual Basic) XSLT 스타일에서 XML 트리 변형 하려면 주석을 사용'
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: c19d290e5b7acdf2702e24383a176ed06c9c7a1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650259"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="6617a-102">방법: LINQ to (Visual Basic) XSLT 스타일에서 XML 트리 변형 하려면 주석을 사용</span><span class="sxs-lookup"><span data-stu-id="6617a-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>
<span data-ttu-id="6617a-103">주석을 사용하여 XML 트리를 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="6617a-104">일부 XML 문서는 "혼합 내용이 포함된 문서 중심적"입니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="6617a-105">이러한 문서를 사용하는 경우 요소의 자식 노드 모양을 반드시 알아야 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="6617a-106">예를 들어, 텍스트가 포함된 노드는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="6617a-107">지정된 텍스트 노드에는 자식 `<b>` 및 `<i>` 요소가 임의의 개수만큼 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="6617a-108">이 방법은 많은 다른 상황으로 확장 됩니다: 예: 다양 한 일반 단락, 글머리 기호 단락 및 비트맵 같은 자식 요소를 포함할 수 있는 페이지.</span><span class="sxs-lookup"><span data-stu-id="6617a-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="6617a-109">표의 셀에는 텍스트, 드롭다운 목록 또는 비트맵이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="6617a-110">문서 중심 XML의 기본 특징 중 하나는 특정 요소에 포함될 자식 요소에 대해 알 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="6617a-111">변환할 요소의 자식에 대해 반드시 자세히 알아야 할 필요가 없는 트리에서 요소를 변환하려면 주석을 사용하는 이 방법이 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="6617a-112">이 방법을 요약하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-112">The summary of the approach is:</span></span>  
  
-   <span data-ttu-id="6617a-113">첫째, 트리의 요소에 대체 요소로 주석을 답니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
-   <span data-ttu-id="6617a-114">둘째, 전체 트리를 반복하여 각 요소를 주석으로 대체하는 새 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="6617a-115">이 예제에서는 `XForm`이라는 함수에서 새 트리의 반복과 생성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="6617a-116">이 방법을 자세히 살펴보면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-116">In detail, the approach consists of:</span></span>  
  
-   <span data-ttu-id="6617a-117">모양을 변환할 요소의 집합을 반환하는 LINQ to XML 쿼리를 하나 이상 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="6617a-118">쿼리의 각 요소에 새 <xref:System.Xml.Linq.XElement> 개체를 주석으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="6617a-119">이 새 요소는 변환된 새 트리에서 주석이 달린 요소를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="6617a-120">예제에 나와 있듯이 이 코드는 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
-   <span data-ttu-id="6617a-121">주석으로 추가된 새 요소는 새 자식 노드를 포함할 수 있으며 원하는 모양의 하위 트리를 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
-   <span data-ttu-id="6617a-122">한 가지 특별한 규칙이 있습니다. 새 요소의 자식 노드가 이 목적을 위해 구성된 다른 네임스페이스(이 예제에서는 `http://www.microsoft.com/LinqToXmlTransform/2007`)에 있으면 해당 자식 요소가 새 트리에 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="6617a-123">대신 네임스페이스가 위에서 언급한 특수 네임스페이스이고 요소의 로컬 이름이 `ApplyTransforms`이면 소스 트리에 있는 요소의 자식 노드가 반복되고 새 트리에 복사됩니다. 단, 주석이 달린 자식 요소는 이러한 규칙에 따라 스스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
-   <span data-ttu-id="6617a-124">이 방법은 XSL의 변환 사양과 다소 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="6617a-125">일련의 노드를 선택하는 쿼리는 템플릿에 대한 XPath 식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="6617a-126">주석으로 저장된 새 <xref:System.Xml.Linq.XElement>를 만들 코드는 XSL의 시퀀스 생성자와 유사하고 `ApplyTransforms` 요소는 XSL의 `xsl:apply-templates` 요소와 기능 면에서 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
-   <span data-ttu-id="6617a-127">이 방법을 사용하는 경우의 한 가지 이점은 쿼리를 만들 때 항상 수정되지 않은 소스 트리에 대한 쿼리를 작성한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="6617a-128">트리의 수정이 작성하고 있는 쿼리에 미치는 영향에 대해 우려할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="6617a-129">트리 변환</span><span class="sxs-lookup"><span data-stu-id="6617a-129">Transforming a Tree</span></span>  
 <span data-ttu-id="6617a-130">이 첫 번째 예제에서는 모든 `Paragraph` 노드의 이름을 `para`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
                <Paragraph>More text.</Paragraph>  
            </Root>  
  
        ' Replace Paragraph with p.  
        For Each el In root...<Paragraph>  
            ' same idea as xsl:apply-templates  
            el.AddAnnotation( _  
                <para>  
                    <<%= at %>></>  
                </para>)  
        Next  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newRoot As XElement = XForm(root)  
        Console.WriteLine(newRoot)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="6617a-131">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="6617a-132">더욱 복잡한 변환</span><span class="sxs-lookup"><span data-stu-id="6617a-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="6617a-133">다음 예제에서는 트리를 쿼리하고 `Data` 요소의 평균과 합계를 계산한 다음 계산 결과를 새 요소로 트리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim data As XElement = _  
            <Root>  
                <Data>20</Data>  
                <Data>10</Data>  
                <Data>3</Data>  
            </Root>  
  
        ' While adding annotations, you can query the source tree all you want,  
        ' as the tree is not mutated while annotating.  
        data.AddAnnotation( _  
            <Root>  
                <<%= at %>/>  
                <Average>  
                    <%= _  
                        String.Format("{0:F4}", _  
                        data.Elements("Data") _  
                        .Select(Function(z) CDec(z)).Average()) _  
                    %>  
                </Average>  
                <Sum>  
                    <%= _  
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _  
                    %>  
                </Sum>  
            </Root> _  
        )  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(data)  
        Console.WriteLine(vbNewLine)  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newData As XElement = XForm(data)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newData)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="6617a-134">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-134">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="6617a-135">변환에 영향 미치기</span><span class="sxs-lookup"><span data-stu-id="6617a-135">Effecting the Transform</span></span>  
 <span data-ttu-id="6617a-136">작은 함수인 `XForm`은 주석이 달린 원래 트리에서 변환된 새 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
-   <span data-ttu-id="6617a-137">이 함수의 의사(pseudo) 코드는 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-137">The pseudo code for the function is quite simple:</span></span>  
  
```  
The function takes an XElement as an argument and returns an XElement.   
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="6617a-138">이 함수의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-138">Following is the implementation of this function:</span></span>  
  
```vb  
' Build a transformed XML tree per the annotations.  
Function XForm(ByVal source As XElement) As XElement  
    If source.Annotation(Of XElement)() IsNot Nothing Then  
        Dim anno As XElement = source.Annotation(Of XElement)()  
        Return _  
            <<%= anno.Name.ToString() %>>  
                <%= anno.Attributes() %>  
                <%= anno.Nodes().Select(Function(n As XNode) _  
                    GetSubNodes(n, source)) %>  
            </>  
    Else  
        Return _  
            <<%= source.Name %>>  
                <%= source.Attributes() %>  
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
            </>  
    End If  
End Function  
  
Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
    Dim annoEl As XElement = TryCast(n, XElement)  
    If annoEl IsNot Nothing Then  
        If annoEl.Name = at Then  
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
        End If  
    End If  
    Return n  
End Function  
  
Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
    Dim e2 As XElement = TryCast(n2, XElement)  
    If e2 Is Nothing Then  
        Return n2  
    Else  
        Return XForm(e2)  
    End If  
End Function  
```  
  
## <a name="complete-example"></a><span data-ttu-id="6617a-139">완성된 예제</span><span class="sxs-lookup"><span data-stu-id="6617a-139">Complete Example</span></span>  
 <span data-ttu-id="6617a-140">다음 코드는 `XForm` 함수가 포함된 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="6617a-141">이 코드에는 이러한 유형의 변환에 대한 몇 가지 일반적인 사용이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports System.Xml  
Imports System.Xml.Linq  
  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    ' Build a transformed XML tree per the annotations.  
    Function XForm(ByVal source As XElement) As XElement  
        If source.Annotation(Of XElement)() IsNot Nothing Then  
            Dim anno As XElement = source.Annotation(Of XElement)()  
            Return _  
                <<%= anno.Name.ToString() %>>  
                    <%= anno.Attributes() %>  
                    <%= anno.Nodes().Select(Function(n As XNode) _  
                        GetSubNodes(n, source)) %>  
                </>  
        Else  
            Return _  
                <<%= source.Name %>>  
                    <%= source.Attributes() %>  
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
                </>  
        End If  
    End Function  
  
    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
        Dim annoEl As XElement = TryCast(n, XElement)  
        If annoEl IsNot Nothing Then  
            If annoEl.Name = at Then  
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
            End If  
        End If  
        Return n  
    End Function  
  
    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
        Dim e2 As XElement = TryCast(n2, XElement)  
        If e2 Is Nothing Then  
            Return n2  
        Else  
            Return XForm(e2)  
        End If  
    End Function  
  
    Sub Main()  
        Dim root As XElement = _  
<Root Att1='123'>  
    <!--A comment-->  
    <Child>1</Child>  
    <Child>2</Child>  
    <Other>  
        <GC>3</GC>  
        <GC>4</GC>  
    </Other>  
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
    <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
        ' Each of the following serves the same semantic purpose as  
        ' XSLT templates and sequence constructors.  
  
        ' Replace Child with NewChild.  
        For Each el In root.<Child>  
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)  
        Next  
  
        ' Replace first GC with GrandChild, add an attribute.  
        For Each el In root...<GC>.Take(1)  
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)  
        Next  
  
        ' Replace Other with NewOther, add new child elements around original content.  
        For Each el In root.<Other>  
            el.AddAnnotation( _  
                <NewOther>  
                    <MyNewChild>1</MyNewChild>  
                    <<%= at %>></>  
                    <ChildThatComesAfter/>  
                </NewOther>)  
        Next  
  
        ' Change name of element that has mixed content.  
        root...<SomeMixedContent>(0).AddAnnotation( _  
                <MixedContent><<%= at %>></></MixedContent>)  
  
        ' Replace <b> with <Bold>.  
        For Each el In root...<b>  
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)  
        Next  
  
        ' Replace <i> with <Italic>.  
        For Each el In root...<i>  
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)  
        Next  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(root)  
        Console.WriteLine(vbNewLine)  
        Dim newRoot As XElement = XForm(root)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newRoot)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="6617a-142">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6617a-142">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6617a-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6617a-143">See Also</span></span>  
 [<span data-ttu-id="6617a-144">고급 LINQ to XML 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6617a-144">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
