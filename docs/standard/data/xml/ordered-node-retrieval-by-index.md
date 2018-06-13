---
title: 인덱스를 사용한 정렬된 노드 검색
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3cfa371394e76aab832c3dd4b065eb811413322
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568627"
---
# <a name="ordered-node-retrieval-by-index"></a>인덱스를 사용한 정렬된 노드 검색
W3C(World Wide Web 컨소시엄) XML DOM(문서 개체 모델)에서는 **XmlNamedNodeMap**으로 처리되는 정렬되지 않은 집합과 반대되는 정렬된 노드 목록을 처리할 수 있는 NodeList에 대해서도 설명합니다. Microsoft .NET Framework에서는 NodeList를 **XmlNodeList**라고 합니다. **XmlNodeList**를 반환하는 메서드와 속성은 다음과 같습니다.  
  
-   XmlNode.ChildNodes  
  
-   XmlDocument.GetElementsByTagName  
  
-   XmlElement.GetElementsByTagName  
  
-   XmlNode.SelectNodes  
  
 **XmlNodeList**에는 다음 코드 샘플과 같이 **XmlNodeList**의 노드를 반복하는 루프를 작성하는 데 사용할 수 있는 **Count** 속성이 있습니다.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 **Count** 속성과 더불어 **XmlNodeList**의 노드 컬렉션에 대한 `foreach` 스타일 반복을 제공하는 **GetEnumerator** 메서드가 있습니다. 다음 코드 예제에서는 `foreach` 문을 사용하는 방법을 보여 줍니다.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 **XmlNodeList**에서 사용할 수 있는 메서드 및 속성에 대한 자세한 내용은 <xref:System.Xml.XmlNodeList>를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
