---
title: "방법: 요소 (LINQ to XML)의 값을 검색 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e688872ea514e822a81b4b3e285ad0d0aa8a0f17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="5601e-102">방법: 요소 (LINQ to XML)의 값을 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5601e-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5601e-103">이 항목에서는 요소의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="5601e-104">두 가지 주요 방법으로 요소의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-104">There are two main ways to do this.</span></span> <span data-ttu-id="5601e-105">한 가지 방법은 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="5601e-106">명시적 변환 연산자는 요소나 특성의 내용을 지정된 형식으로 변환하고 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="5601e-107">또는 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> 속성이나 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="5601e-108">Visual Basic에서 가장 좋은 방법은 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> 속성을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5601e-109">예제</span><span class="sxs-lookup"><span data-stu-id="5601e-109">Example</span></span>  
 <span data-ttu-id="5601e-110">요소의 값을 검색하려면 <xref:System.Xml.Linq.XElement> 개체를 원하는 형식으로 캐스팅하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="5601e-111">다음과 같이 요소를 문자열로 항상 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="5601e-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-112">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="5601e-113">예제</span><span class="sxs-lookup"><span data-stu-id="5601e-113">Example</span></span>  
 <span data-ttu-id="5601e-114">또한 요소를 문자열 이외의 형식으로 캐스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="5601e-115">예를 들어, 정수가 포함된 요소가 있는 경우 다음 코드에서와 같이 요소를 `int`로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="5601e-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-116">This example produces the following output:</span></span>  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="5601e-117">에서는 `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` 및 `GUID?` 데이터 형식에 대해 명시적 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-117"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="5601e-118">에서는 <xref:System.Xml.Linq.XAttribute> 개체에 대해 동일한 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-118"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5601e-119">예제</span><span class="sxs-lookup"><span data-stu-id="5601e-119">Example</span></span>  
 <span data-ttu-id="5601e-120"><xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하여 요소의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="5601e-121">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-121">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="5601e-122">예제</span><span class="sxs-lookup"><span data-stu-id="5601e-122">Example</span></span>  
 <span data-ttu-id="5601e-123">요소가 있는지 확실하지 않은 경우에도 요소의 값을 검색하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="5601e-124">이 경우 캐스팅된 요소를 nullable 형식(`string` 또는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 nullable 형식 중 하나)에 할당할 때 요소가 없으면 할당된 변수가 `Nothing`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="5601e-125">다음 코드에서는 요소가 존재하지 않을 수도 있을 때 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하는 것보다 캐스팅을 사용하는 것이 더 쉽다는 사실을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 <span data-ttu-id="5601e-126">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-126">This code produces the following output:</span></span>  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="5601e-127">일반적으로 요소 및 특성 내용을 검색하는 데 캐스팅을 사용하면 보다 간단한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5601e-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5601e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5601e-128">See Also</span></span>  
 [<span data-ttu-id="5601e-129">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5601e-129">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
