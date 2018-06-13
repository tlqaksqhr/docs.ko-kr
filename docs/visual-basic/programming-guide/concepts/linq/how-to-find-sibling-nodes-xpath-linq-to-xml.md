---
title: '방법: 형제 노드 찾기 (XPath LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
ms.openlocfilehash: ded92d8cb7cb2d2aa6c6342c3ddec347e25ff79a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642884"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="adb1a-102">방법: 형제 노드 찾기 (XPath LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adb1a-102">How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="adb1a-103">특정 이름을 가진 노드의 형제를 모두 찾으려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-103">You might want to find all siblings of a node that have a specific name.</span></span> <span data-ttu-id="adb1a-104">컨텍스트 노드도 해당 이름을 가진 경우 생성되는 컬렉션에 컨텍스트 노드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-104">The resulting collection might include the context node if the context node also has the specific name.</span></span>  
  
 <span data-ttu-id="adb1a-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-105">The XPath expression is:</span></span>  
  
 `../Book`  
  
## <a name="example"></a><span data-ttu-id="adb1a-106">예제</span><span class="sxs-lookup"><span data-stu-id="adb1a-106">Example</span></span>  
 <span data-ttu-id="adb1a-107">이 예제에서는 먼저 `Book` 요소를 찾은 다음 `Book`이라는 모든 형제 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`.</span></span> <span data-ttu-id="adb1a-108">생성되는 컬렉션에는 컨텍스트 노드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-108">The resulting collection includes the context node.</span></span>  
  
 <span data-ttu-id="adb1a-109">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>.Skip(1).First()  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = book.Parent.<Book>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = book.XPathSelectElements("../Book")  
  
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
  
 <span data-ttu-id="adb1a-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="adb1a-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Book id="bk101">  
  <Author>Garghentini, Davide</Author>  
  <Title>XML Developer's Guide</Title>  
  <Genre>Computer</Genre>  
  <Price>44.95</Price>  
  <PublishDate>2000-10-01</PublishDate>  
  <Description>An in-depth look at creating applications   
      with XML.</Description>  
</Book>  
<Book id="bk102">  
  <Author>Garcia, Debra</Author>  
  <Title>Midnight Rain</Title>  
  <Genre>Fantasy</Genre>  
  <Price>5.95</Price>  
  <PublishDate>2000-12-16</PublishDate>  
  <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="adb1a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adb1a-111">See Also</span></span>  
 [<span data-ttu-id="adb1a-112">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adb1a-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
