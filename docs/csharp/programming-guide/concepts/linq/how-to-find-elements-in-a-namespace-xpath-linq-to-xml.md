---
title: "방법: 네임스페이스에서 요소 찾기(XPath 및 LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f1804731a39eebce74a38a4e8b296747e535c0b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="d3f46-102">방법: 네임스페이스에서 요소 찾기(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="d3f46-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="d3f46-103">XPath 식은 특정 네임스페이스에서 노드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="d3f46-104">XPath 식은 네임스페이스를 지정하는 데 네임스페이스 접두사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="d3f46-105">네임스페이스 접두사가 포함된 XPath 식의 구문을 분석하려면 <xref:System.Xml.IXmlNamespaceResolver>를 구현하는 XPath 메서드에 개체를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="d3f46-106">이 예제에서는 <xref:System.Xml.XmlNamespaceManager>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="d3f46-107">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="d3f46-108">예제</span><span class="sxs-lookup"><span data-stu-id="d3f46-108">Example</span></span>  
 <span data-ttu-id="d3f46-109">다음 예제에서는 두 네임스페이스가 포함된 XML 트리를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="d3f46-110">여기에서는 <xref:System.Xml.XmlReader>를 사용하여 XML 문서를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="d3f46-111">그런 다음 <xref:System.Xml.XmlNameTable>에서 <xref:System.Xml.XmlReader>을 가져오고 <xref:System.Xml.XmlNamespaceManager>에서 <xref:System.Xml.XmlNameTable>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="d3f46-112">또한 요소를 선택할 때 <xref:System.Xml.XmlNamespaceManager>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");  
XElement root = XElement.Load(reader);  
XmlNameTable nameTable = reader.NameTable;  
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");  
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);  
IEnumerable<XElement> list2 =  
    from el in root.Elements()  
    where el.Name.Namespace == "http://www.adventure-works.com"  
    select el;  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d3f46-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f46-113">This example produces the following output:</span></span>  
  
```  
Results are identical  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="d3f46-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3f46-114">See Also</span></span>  
 [<span data-ttu-id="d3f46-115">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="d3f46-115">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
