---
title: '방법: 파일 (Visual Basic)에서 XML을 로드 합니다.'
ms.date: 07/20/2015
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
ms.openlocfilehash: fce4ebee075f5e622de17bd5227dd6e4ae9cccd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641441"
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="46bff-102">방법: 파일 (Visual Basic)에서 XML을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-102">How to: Load XML from a File (Visual Basic)</span></span>
<span data-ttu-id="46bff-103">이 항목에서는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 메서드를 사용하여 URI에서 XML을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46bff-104">예제</span><span class="sxs-lookup"><span data-stu-id="46bff-104">Example</span></span>  
 <span data-ttu-id="46bff-105">다음 예제에서는 파일에서 XML 문서를 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="46bff-106">다음 예제에서는 books.xml을 로드하고 XML 트리를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="46bff-107">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 <span data-ttu-id="46bff-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46bff-108">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
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
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46bff-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46bff-109">See Also</span></span>  
 [<span data-ttu-id="46bff-110">XML 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46bff-110">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
