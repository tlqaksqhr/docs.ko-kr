---
title: "시각적 Basic2의 XML 리터럴 소개 | Microsoft 문서"
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
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a3aff4755c23664153ce1dc0ec2df58a96d29c66
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="7dfec-102">Visual Basic의 XML 리터럴 소개</span><span class="sxs-lookup"><span data-stu-id="7dfec-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="7dfec-103">이 단원에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 XML 트리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-103">This section provides information about creating XML trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="7dfec-104">XML 트리에 대 한 내용으로 LINQ 쿼리 결과 사용 하는 방법에 대 한 정보를 참조 하십시오. [함수 생성 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7dfec-105">XML 리터럴에 대 한 자세한 내용은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 참조 [Visual Basic의 XML LINQ의 개요](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-105">For more information on XML literals in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], see [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="7dfec-106">XML 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="7dfec-106">Creating XML Trees</span></span>  
 <span data-ttu-id="7dfec-107">다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XElement>,이 경우 `contacts`:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7dfec-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="7dfec-108">단순 내용을 사용하여 XElement 만들기</span><span class="sxs-lookup"><span data-stu-id="7dfec-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="7dfec-109">만들 수는 <xref:System.Xml.Linq.XElement>다음과 같이 단순 내용이 포함 된 있는:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7dfec-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)   
```  
  
 <span data-ttu-id="7dfec-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="7dfec-111">빈 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="7dfec-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="7dfec-112">빈을 만들 수 있습니다 <xref:System.Xml.Linq.XElement>다음과 같이:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7dfec-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="7dfec-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="7dfec-114">포함 식 사용</span><span class="sxs-lookup"><span data-stu-id="7dfec-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="7dfec-115">XML 리터럴의 중요한 특징은 포함 식을 허용한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="7dfec-116">포함 식을 통해 식을 계산하고 식의 결과를 XML 트리에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="7dfec-117">식의 형식으로 계산 되는 경우 <xref:System.Xml.Linq.XElement>, 요소를 트리에 삽입 됩니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7dfec-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="7dfec-118">식의 형식으로 계산 되는 경우 <xref:System.Xml.Linq.XAttribute>, 특성을 트리에 삽입 됩니다.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="7dfec-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="7dfec-119">유효한 경우에만 요소와 특성을 트리에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="7dfec-120">단일 식만 포함 식에 들어갈 수 있는 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="7dfec-121">여러 문을 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="7dfec-122">식이 한 줄을 넘으면 줄 연속 문자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="7dfec-123">포함 식을 사용하여 기존 노드(요소 포함)와 특성을 새 XML 트리에 추가하는 경우 기존 노드에 이미 부모가 있으면 노드가 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="7dfec-124">새로 복제된 노드는 새 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="7dfec-125">기존 노드에 부모가 없으면 노드가 새 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="7dfec-126">이 항목의 마지막 예제에서는 이에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="7dfec-127">다음 예제에서는 포함 식을 사용하여 요소를 트리에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="7dfec-128">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="7dfec-129">내용에 대해 포함 식 사용</span><span class="sxs-lookup"><span data-stu-id="7dfec-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="7dfec-130">포함 식을 사용하여 요소의 내용을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="7dfec-131">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="7dfec-132">포함 식에서 LINQ 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="7dfec-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="7dfec-133">LINQ 쿼리의 결과를 요소의 내용으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="7dfec-134">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="7dfec-135">노드 이름에 대해 포함 식 사용</span><span class="sxs-lookup"><span data-stu-id="7dfec-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="7dfec-136">포함 식을 사용하여 특성 이름, 특성 값, 요소 이름 및 요소 값을 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="7dfec-137">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="7dfec-138">복제와 추가 비교</span><span class="sxs-lookup"><span data-stu-id="7dfec-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="7dfec-139">앞에서 설명했듯이 포함 식을 사용하여 기존 노드(요소 포함)와 특성을 새 XML 트리에 추가하는 경우 기존 노드에 이미 부모가 있으면 노드가 복제되고 새로 복제된 노드가 새 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="7dfec-140">기존 노드에 부모가 없으면 노드가 새 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="7dfec-141">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfec-141">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dfec-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dfec-142">See Also</span></span>  
 [<span data-ttu-id="7dfec-143">XML 트리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="7dfec-143">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
