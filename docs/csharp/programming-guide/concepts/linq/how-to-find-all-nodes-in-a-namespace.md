---
title: "방법: 네임스페이스에서 모든 노드 찾기(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 3a38b913-a53e-4d0e-a19d-8782bffd3364
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e3a132834527f3a13a678fc56a593f7b442deb56
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-all-nodes-in-a-namespace-c"></a><span data-ttu-id="c70b3-102">방법: 네임스페이스에서 모든 노드 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="c70b3-102">How to: Find All Nodes in a Namespace (C#)</span></span>
<span data-ttu-id="c70b3-103">해당 특정 네임스페이스에서 모든 노드를 찾기 위해 각 요소나 특성의 네임스페이스를 기준으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-103">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c70b3-104">예제</span><span class="sxs-lookup"><span data-stu-id="c70b3-104">Example</span></span>  
 <span data-ttu-id="c70b3-105">다음 예제에서는 두 네임스페이스가 포함된 XML 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-105">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="c70b3-106">그런 다음 트리를 반복하고 이러한 네임스페이스 중 하나에 있는 모든 요소 및 특성의 이름을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-106">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>  
  
```csharp  
string markup = @"<aw:Root xmlns:aw='http://www.adventure-works.com' xmlns:fc='www.fourthcoffee.com'>  
  <fc:Child1>abc</fc:Child1>  
  <fc:Child2>def</fc:Child2>  
  <aw:Child3>ghi</aw:Child3>  
  <fc:Child4>  
    <fc:GrandChild1>jkl</fc:GrandChild1>  
    <aw:GrandChild2>mno</aw:GrandChild2>  
  </fc:Child4>  
</aw:Root>";  
XElement xmlTree = XElement.Parse(markup);  
Console.WriteLine("Nodes in the http://www.adventure-works.com namespace");  
IEnumerable<XElement> awElements =  
    from el in xmlTree.Descendants()  
    where el.Name.Namespace == "http://www.adventure-works.com"  
    select el;  
foreach (XElement el in awElements)  
    Console.WriteLine(el.Name.ToString());  
```  
  
 <span data-ttu-id="c70b3-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-107">This code produces the following output:</span></span>  
  
```  
Nodes in the http://www.adventure-works.com namespace  
{http://www.adventure-works.com}Child3  
{http://www.adventure-works.com}GrandChild2  
```  
  
## <a name="example"></a><span data-ttu-id="c70b3-108">예제</span><span class="sxs-lookup"><span data-stu-id="c70b3-108">Example</span></span>  
 <span data-ttu-id="c70b3-109">다음 쿼리에서 액세스하는 XML 파일에는 두 가지 네임스페이스의 구매 주문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-109">The XML file accessed by the following query contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="c70b3-110">쿼리에서는 네임스페이스 중 하나에 있는 요소만 포함된 트리를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-110">The query creates a new tree with just the elements in one of the namespaces.</span></span>  
  
 <span data-ttu-id="c70b3-111">이 예제에서는 XML 문서 [샘플 XML 파일: 통합된 구매 주문](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-111">This example uses the following XML document: [Sample XML File: Consolidated Purchase Orders](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("ConsolidatedPurchaseOrders.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement newTree = new XElement("Root",  
    from el in cpo.Root.Elements()  
    where el.Name.Namespace == aw  
    select el  
);  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="c70b3-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c70b3-112">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">  
    <aw:ShippingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:ShippingAddress>  
    <aw:BillingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:BillingAddress>  
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>  
    <aw:Item PartNum="LIT-01">  
      <aw:ProductID>Litware Networking Card</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>20.99</aw:Price>  
    </aw:Item>  
    <aw:Item PartNum="LIT-25">  
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>199.99</aw:Price>  
    </aw:Item>  
  </aw:PurchaseOrder>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c70b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c70b3-113">See Also</span></span>  
 [<span data-ttu-id="c70b3-114">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="c70b3-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

