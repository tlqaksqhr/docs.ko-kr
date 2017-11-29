---
title: "방법: 두 위치 경로 (XPath 및 LINQ to XML)의 공용 구조체 찾기 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c15ef409500a07d922563309301ea8f1442feee6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="b23e7-102">방법: 두 위치 경로 (XPath 및 LINQ to XML)의 공용 구조체 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23e7-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b23e7-103">XPath를 사용하여 두 XPath 위치 경로의 통합을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="b23e7-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="b23e7-105"><xref:System.Linq.Enumerable.Concat%2A> 표준 쿼리 연산자를 사용하여 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b23e7-106">예제</span><span class="sxs-lookup"><span data-stu-id="b23e7-106">Example</span></span>  
 <span data-ttu-id="b23e7-107">이 예제에서는 모든 `Category` 요소와 모든 `Price` 요소를 찾은 다음 단일 컬렉션으로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="b23e7-108">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>을 호출하여 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="b23e7-109">XPath 식 계산의 결과도 문서 순서로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="b23e7-110">이 예제에서는 XML 문서 [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="b23e7-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b23e7-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b23e7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b23e7-112">See Also</span></span>  
 [<span data-ttu-id="b23e7-113">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23e7-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
