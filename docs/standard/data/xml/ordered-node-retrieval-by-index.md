---
title: "인덱스를 사용한 정렬된 노드 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 13d3077b1536d4e96cb9e4f1f09313dd793a906e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ordered-node-retrieval-by-index"></a>인덱스를 사용한 정렬된 노드 검색
World Wide Web Consortium (W3C) XML 문서 개체 모델 (DOM) 노드에서 처리 하는 순서가 지정 되지 않은 집합과 반대 되는 순서가 지정 된 목록을 처리할 수 있는 NodeList, 대해서도 설명는 **XmlNamedNodeMap**합니다. Microsoft.NET Framework에서는 NodeList 라고 **XmlNodeList**합니다. 메서드 및 속성을 반환 하는 프로그램 **XmlNodeList** 됩니다.  
  
-   XmlNode.ChildNodes  
  
-   XmlDocument.GetElementsByTagName  
  
-   XmlElement.GetElementsByTagName  
  
-   XmlNode.SelectNodes  
  
 **XmlNodeList** 에 **Count** 의 노드를 반복 하는 루프를 작성 하는 데 사용할 수 있는 속성은 **XmlNodeList**다음 코드 샘플에 나온 것 처럼:  
  
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
  
 외에 **Count** 속성을는 **GetEnumerator** 메서드를 제공 하는 a, `foreach` 형식의 검색에 있는 노드의 컬렉션에 대해는 **XmlNodeList**. 다음 코드 예제에서는 `foreach` 문을 사용하는 방법을 보여 줍니다.  
  
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
  
 메서드 및 속성에 대 한 자세한 내용은 **XmlNodeList**, 참조 <xref:System.Xml.XmlNodeList>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
