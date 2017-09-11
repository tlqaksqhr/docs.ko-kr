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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a60b5cb3557016bba7bae9be6e0b9c9a448c1284
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="cae9e-102">방법: (Visual Basic) XmlReader에서 트리 조각 만들기</span><span class="sxs-lookup"><span data-stu-id="cae9e-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="cae9e-103">이 항목에서는 <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 에서 직접 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cae9e-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="cae9e-104">만들려는 <xref:System.Xml.Linq.XElement>에서 <xref:System.Xml.XmlReader>, 배치 해야는 <xref:System.Xml.XmlReader>가 요소 노드에.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="cae9e-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="cae9e-105"><xref:System.Xml.XmlReader>주석과 처리 명령을 건너뛰지만 경우 및는 <xref:System.Xml.XmlReader>커서가 텍스트 노드에 오류가 throw 됩니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="cae9e-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="cae9e-106">이러한 오류를 방지 하려면 항상는 <xref:System.Xml.XmlReader> <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 에서 XML 트리를 만들기 전에 요소에</xref:System.Xml.XmlReader> 배치</span><span class="sxs-lookup"><span data-stu-id="cae9e-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae9e-107">예제</span><span class="sxs-lookup"><span data-stu-id="cae9e-107">Example</span></span>  
 <span data-ttu-id="cae9e-108">이 예제에서는 다음 XML 문서: [샘플 XML 파일: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cae9e-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cae9e-109">다음 코드에서는 `T:System.Xml.XmlReader` 개체를 만들고 첫 번째 요소 노드를 찾을 때까지 노드를 읽은 다음</span><span class="sxs-lookup"><span data-stu-id="cae9e-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="cae9e-110">로드 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="cae9e-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="cae9e-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cae9e-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cae9e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cae9e-112">See Also</span></span>  
 [<span data-ttu-id="cae9e-113">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="cae9e-113">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
