---
title: "방법: XML 파일 (Visual Basic)에서 로드 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 54755384eaf74fa008f93198f3de5e44fb095bda
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a>방법: XML 파일에서에서 로드 한 (Visual Basic)
이 항목에서는 사용 하 여 URI에서 XML을 로드 하는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>메서드.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
## <a name="example"></a>예제  
 다음 예제에서는 파일에서 XML 문서를 로드하는 방법을 보여 줍니다. 다음 예제에서는 books.xml을 로드하고 XML 트리를 콘솔에 출력합니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)합니다.  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
