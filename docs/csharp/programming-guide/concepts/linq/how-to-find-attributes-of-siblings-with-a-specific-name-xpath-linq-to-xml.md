---
title: "방법: 특정 이름으로 형제의 특성 찾기(XPath-LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5a67d502289b10dca95bbc91b16cbc2beae90cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="8bacf-102">방법: 특정 이름으로 형제의 특성 찾기(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="8bacf-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="8bacf-103">이 항목에서는 컨텍스트 노드에 대한 형제의 특성을 모두 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="8bacf-104">특정 이름을 가진 특성만 컬렉션에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="8bacf-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="8bacf-106">예제</span><span class="sxs-lookup"><span data-stu-id="8bacf-106">Example</span></span>  
 <span data-ttu-id="8bacf-107">이 예제에서는 먼저 `Book` 요소를 찾은 다음 `Book`이라는 모든 형제 요소를 찾고 `id`라는 모든 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="8bacf-108">결과는 특성의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="8bacf-109">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="8bacf-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8bacf-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bacf-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bacf-111">See Also</span></span>  
 [<span data-ttu-id="8bacf-112">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="8bacf-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
