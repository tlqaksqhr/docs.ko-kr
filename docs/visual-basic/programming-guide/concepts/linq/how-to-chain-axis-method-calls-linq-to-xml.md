---
title: "방법: 축 메서드 호출 (LINQ to XML) 연결 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39579d08d339ed8964520936d28ee289de5fb15d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a><span data-ttu-id="a2062-102">방법: 축 메서드 호출 (LINQ to XML) 연결 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2062-102">How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a2062-103">코드에 사용할 수 있는 일반적인 방법은 축 메서드를 호출한 다음 확장명 메서드 축 중 하나를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="a2062-104">요소의 컬렉션을 반환하며 `Elements`의 이름이 포함된 두 축인 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> 메서드와 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a2062-105">이러한 두 축을 결합하여 트리의 특정 깊이에서 지정된 이름의 모든 요소를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2062-106">예제</span><span class="sxs-lookup"><span data-stu-id="a2062-106">Example</span></span>  
 <span data-ttu-id="a2062-107">이 예제에서는 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> 및 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>를 사용하여 모든 `Name` 요소의 모든 `Address` 요소에 있는 모든 `PurchaseOrder` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="a2062-108">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="a2062-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="a2062-110">이는 `Elements` 축의 구현 중 하나가 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XContainer>에 대한 확장 메서드이기 때문에 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="a2062-111"><xref:System.Xml.Linq.XElement>는 <xref:System.Xml.Linq.XContainer>에서 파생되므로 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> 메서드에 대한 호출의 결과에 대해 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2062-112">예제</span><span class="sxs-lookup"><span data-stu-id="a2062-112">Example</span></span>  
 <span data-ttu-id="a2062-113">중간에 상위 요소가 있을 수도 있고 없을 수도 있는 특정 요소 깊이에서 모든 요소를 검색하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="a2062-114">예를 들어, 다음 문서에서 `ConfigParameter` 요소의 자식인 모든 `Customer` 요소를 검색하고 `ConfigParameter` 요소의 자식인 `Root`는 검색하지 않으려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="a2062-115">이렇게 하려면 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> 축을 다음과 같이 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 <span data-ttu-id="a2062-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="a2062-117">예제</span><span class="sxs-lookup"><span data-stu-id="a2062-117">Example</span></span>  
 <span data-ttu-id="a2062-118">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="a2062-119">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-119">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="a2062-120">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 여러 구매 주문](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a2062-121">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2062-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2062-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2062-122">See Also</span></span>  
 [<span data-ttu-id="a2062-123">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2062-123">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
