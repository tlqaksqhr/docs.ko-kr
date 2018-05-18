---
title: '방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 6f796bfb8f8b0051af4e31f6e82a503dbfbbc334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)
이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `../@id`  
  
## <a name="example"></a>예  
 이 예제에서는 먼저 `Author` 요소를 찾은 다음 부모 요소의 `id` 특성을 찾습니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.  
  
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
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>참고 항목  
 [XPath 사용자를 위한 LINQ to XML(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
