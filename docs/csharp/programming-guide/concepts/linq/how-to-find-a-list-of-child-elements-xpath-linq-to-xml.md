---
title: "방법: 자식 요소 목록 찾기(XPath 및 LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ac1516dd9917e6d19e7563c43ec5bee8da3ee963
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="064a6-102">방법: 자식 요소 목록 찾기(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="064a6-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="064a6-103">이 항목에서는 XPath 자식 요소 축과 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> 축을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="064a6-104">XPath 식은 `./*`입니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="064a6-105">예제</span><span class="sxs-lookup"><span data-stu-id="064a6-105">Example</span></span>  
 <span data-ttu-id="064a6-106">이 예제에서는 `Address` 요소의 모든 자식 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="064a6-107">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Elements();  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="064a6-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="064a6-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="064a6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="064a6-109">See Also</span></span>  
 [<span data-ttu-id="064a6-110">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="064a6-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
