---
title: "방법: 하위 요소 찾기(XPath 및 LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d3551054b345d9ec1d18b33f697cf5c139bfab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="cfeb1-102">방법: 하위 요소 찾기(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="cfeb1-102">How to: Find Descendant Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="cfeb1-103">이 항목에서는 특정 이름을 가진 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfeb1-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="cfeb1-104">XPath 식은 `//Name`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfeb1-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfeb1-105">예제</span><span class="sxs-lookup"><span data-stu-id="cfeb1-105">Example</span></span>  
 <span data-ttu-id="cfeb1-106">이 예제에서는 `Name`이라는 모든 하위 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cfeb1-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="cfeb1-107">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfeb1-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cfeb1-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfeb1-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfeb1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfeb1-109">See Also</span></span>  
 [<span data-ttu-id="cfeb1-110">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="cfeb1-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
