---
title: '방법: 하위 요소 (XPath 및 LINQ to XML) 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: e5915eb06af427c0631049af6dfc30399cb775e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640228"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="6f169-102">방법: 하위 요소 (XPath 및 LINQ to XML) 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f169-102">How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="6f169-103">이 항목에서는 특정 이름을 가진 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f169-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="6f169-104">XPath 식은 `//Name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6f169-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f169-105">예제</span><span class="sxs-lookup"><span data-stu-id="6f169-105">Example</span></span>  
 <span data-ttu-id="6f169-106">이 예제에서는 `Name`이라는 모든 하위 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6f169-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="6f169-107">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f169-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="6f169-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6f169-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f169-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f169-109">See Also</span></span>  
 [<span data-ttu-id="6f169-110">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f169-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
