---
title: "방법: (Visual Basic) XmlReader에서 트리 조각 만들기 | Microsoft 문서"
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
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
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
ms.openlocfilehash: a8dff4e518d8850b4050389e5677ac81ecd1e074
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>방법: (Visual Basic) XmlReader에서 트리 조각 만들기
이 항목에서는 <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 에서 직접 XML 트리를 만드는 방법을 보여 줍니다. 만들려는 <xref:System.Xml.Linq.XElement>에서 <xref:System.Xml.XmlReader>, 배치 해야는 <xref:System.Xml.XmlReader>가 요소 노드에.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement> <xref:System.Xml.XmlReader>주석과 처리 명령을 건너뛰지만 경우 및는 <xref:System.Xml.XmlReader>커서가 텍스트 노드에 오류가 throw 됩니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> 이러한 오류를 방지 하려면 항상는 <xref:System.Xml.XmlReader> <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 에서 XML 트리를 만들기 전에 요소에</xref:System.Xml.XmlReader> 배치  
  
## <a name="example"></a>예제  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)합니다.  
  
 다음 코드에서는 `T:System.Xml.XmlReader` 개체를 만들고 첫 번째 요소 노드를 찾을 때까지 노드를 읽은 다음 로드 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
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
