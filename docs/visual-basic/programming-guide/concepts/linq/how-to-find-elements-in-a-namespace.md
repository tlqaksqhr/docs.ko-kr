---
title: "방법: Namespace (XPath 및 LINQ to XML)에서 요소 찾기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: c7cb3b77-3424-4b54-9efa-4dc715948e41
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d665ddc1e7ad7340b05c97e790195abbc53e4f95
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-visual-basic"></a>방법: Namespace (XPath 및 LINQ to XML)에서 요소 찾기 (Visual Basic)
XPath 식은 특정 네임스페이스에서 노드를 찾을 수 있습니다. XPath 식은 네임스페이스를 지정하는 데 네임스페이스 접두사를 사용합니다. 네임 스페이스 접두사를 포함 하는 XPath 식을 구문 분석에 <xref:System.Xml.IXmlNamespaceResolver>.</xref:System.Xml.IXmlNamespaceResolver> 를 구현 하는 XPath 메서드에 개체를 전달 해야 이 예제에서는 <xref:System.Xml.XmlNamespaceManager>.</xref:System.Xml.XmlNamespaceManager> 사용  
  
 XPath 식은 다음과 같습니다.  
  
 `./aw:*`  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 네임스페이스가 포함된 XML 트리를 읽습니다. 사용 하 여는 <xref:System.Xml.XmlReader>XML 문서를 읽고.</xref:System.Xml.XmlReader> 그런 다음 가져옵니다는 <xref:System.Xml.XmlNameTable>에서 <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlNamespaceManager> <xref:System.Xml.XmlNameTable>.</xref:System.Xml.XmlNameTable> </xref:System.Xml.XmlNamespaceManager> </xref:System.Xml.XmlReader> </xref:System.Xml.XmlNameTable> 사용 하 여는 <xref:System.Xml.XmlNamespaceManager>요소를 선택할 때.</xref:System.Xml.XmlNamespaceManager>  
  
```vb  
Dim reader As XmlReader = _  
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")  
Dim root As XElement = XElement.Load(reader)  
Dim nameTable As XmlNameTable = reader.NameTable  
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")  
  
Dim list1 As IEnumerable(Of XElement) = _  
        root.XPathSelectElements("./aw:*", namespaceManager)  
Dim list2 As IEnumerable(Of XElement) = _  
    From el In root.Elements() _  
    Where el.Name.Namespace = "http://www.adventure-works.com" _  
    Select el  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
