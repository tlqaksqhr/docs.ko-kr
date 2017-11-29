---
title: "방법: 특정 이름 (XPath 및 LINQ to XML)으로 형제의 특성 찾기 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 751d9559ae3b0bfe62fc866baf52fbef7babb7e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="d0eef-102">방법: 특정 이름 (XPath 및 LINQ to XML)으로 형제의 특성 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0eef-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d0eef-103">이 항목에서는 컨텍스트 노드에 대한 형제의 특성을 모두 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="d0eef-104">특정 이름을 가진 특성만 컬렉션에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="d0eef-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="d0eef-106">예제</span><span class="sxs-lookup"><span data-stu-id="d0eef-106">Example</span></span>  
 <span data-ttu-id="d0eef-107">이 예제에서는 먼저 `Book` 요소를 찾은 다음 `Book`이라는 모든 형제 요소를 찾고 `id`라는 모든 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="d0eef-108">결과는 특성의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="d0eef-109">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="d0eef-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0eef-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0eef-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0eef-111">See Also</span></span>  
 [<span data-ttu-id="d0eef-112">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0eef-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
