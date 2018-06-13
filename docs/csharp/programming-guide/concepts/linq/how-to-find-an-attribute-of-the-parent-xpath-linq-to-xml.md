---
title: '방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 6f796bfb8f8b0051af4e31f6e82a503dbfbbc334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318801"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="abf81-102">방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="abf81-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="abf81-103">이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abf81-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="abf81-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="abf81-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="abf81-105">예</span><span class="sxs-lookup"><span data-stu-id="abf81-105">Example</span></span>  
 <span data-ttu-id="abf81-106">이 예제에서는 먼저 `Author` 요소를 찾은 다음</span><span class="sxs-lookup"><span data-stu-id="abf81-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="abf81-107">부모 요소의 `id` 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abf81-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="abf81-108">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abf81-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement author =   
    books  
    .Root  
    .Element("Book")  
    .Element("Author");  
  
// LINQ to XML query  
XAttribute att1 =  
    author  
    .Parent  
    .Attribute("id");  
  
// XPath expression  
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();  
  
if (att1 == att2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(att1);  
```  
  
 <span data-ttu-id="abf81-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="abf81-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="abf81-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abf81-110">See Also</span></span>  
 [<span data-ttu-id="abf81-111">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="abf81-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
