---
title: '방법: 선행 형제 찾기 (XPath LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 59055718-d0a7-4db3-8901-18dd33587703
ms.openlocfilehash: 1b8c73f266cc618660b59e76e46420c08b5299d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641949"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="7f510-102">방법: 선행 형제 찾기 (XPath LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f510-102">How to: Find Preceding Siblings (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="7f510-103">이 항목에서는 XPath `preceding-sibling` 축과 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 자식 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> 축을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-103">This topic compares the XPath `preceding-sibling` axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] child <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> axis.</span></span>  
  
 <span data-ttu-id="7f510-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-104">The XPath expression is:</span></span>  
  
 `preceding-sibling::*`  
  
 <span data-ttu-id="7f510-105"><xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> 및 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>의 결과는 문서 순서로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-105">Note that the results of both <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> and <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> are in document order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f510-106">예제</span><span class="sxs-lookup"><span data-stu-id="7f510-106">Example</span></span>  
 <span data-ttu-id="7f510-107">다음 예제에서는 `FullAddress` 요소를 찾은 다음 `preceding-sibling` 축을 사용하여 이전 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-107">The following example finds the `FullAddress` element, and then retrieves the previous elements using the `preceding-sibling` axis.</span></span>  
  
 <span data-ttu-id="7f510-108">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-108">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim add As XElement = co.<Customers>.<Customer>. _  
        <FullAddress>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = add.ElementsBeforeSelf()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = add.XPathSelectElements("preceding-sibling::*")  
  
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
  
 <span data-ttu-id="7f510-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f510-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f510-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f510-110">See Also</span></span>  
 [<span data-ttu-id="7f510-111">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f510-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
