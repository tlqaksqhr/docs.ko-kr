---
title: "방법: 형제 노드 (XPath 및 LINQ to XML) 찾기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 615842d7b2fb1ae51d3380ecf928c22a59e42516
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a>방법: 형제 노드 (XPath 및 LINQ to XML) 찾기 (Visual Basic)
특정 이름을 가진 노드의 형제를 모두 찾으려고 할 수 있습니다. 컨텍스트 노드도 해당 이름을 가진 경우 생성되는 컬렉션에 컨텍스트 노드가 포함될 수 있습니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `../Book`  
  
## <a name="example"></a>예제  
 이 예제에서는 먼저 `Book` 요소를 찾은 다음 `Book`이라는 모든 형제 요소를 찾습니다. 생성되는 컬렉션에는 컨텍스트 노드가 포함됩니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)합니다.  
  
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
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
