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
# <a name="ordered-node-retrieval-by-index"></a><span data-ttu-id="c84f3-102">인덱스를 사용한 정렬된 노드 검색</span><span class="sxs-lookup"><span data-stu-id="c84f3-102">Ordered Node Retrieval by Index</span></span>
<span data-ttu-id="c84f3-103">World Wide Web Consortium (W3C) XML 문서 개체 모델 (DOM) 노드에서 처리 하는 순서가 지정 되지 않은 집합과 반대 되는 순서가 지정 된 목록을 처리할 수 있는 NodeList, 대해서도 설명는 **XmlNamedNodeMap**합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f3-103">The World Wide Web Consortium (W3C) XML Document Object Model (DOM) also describes a NodeList, which has the ability to handle an ordered list of nodes, as opposed to the unordered set handled by the **XmlNamedNodeMap**.</span></span> <span data-ttu-id="c84f3-104">Microsoft.NET Framework에서는 NodeList 라고 **XmlNodeList**합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f3-104">The NodeList in the Microsoft .NET Framework is called **XmlNodeList**.</span></span> <span data-ttu-id="c84f3-105">메서드 및 속성을 반환 하는 프로그램 **XmlNodeList** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84f3-105">Methods and properties that return an **XmlNodeList** are:</span></span>  
  
-   <span data-ttu-id="c84f3-106">XmlNode.ChildNodes</span><span class="sxs-lookup"><span data-stu-id="c84f3-106">XmlNode.ChildNodes</span></span>  
  
-   <span data-ttu-id="c84f3-107">XmlDocument.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="c84f3-107">XmlDocument.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="c84f3-108">XmlElement.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="c84f3-108">XmlElement.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="c84f3-109">XmlNode.SelectNodes</span><span class="sxs-lookup"><span data-stu-id="c84f3-109">XmlNode.SelectNodes</span></span>  
  
 <span data-ttu-id="c84f3-110">**XmlNodeList** 에 **Count** 의 노드를 반복 하는 루프를 작성 하는 데 사용할 수 있는 속성은 **XmlNodeList**다음 코드 샘플에 나온 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="c84f3-110">The **XmlNodeList** has a **Count** property that can be used to write loops to iterate over the nodes in the **XmlNodeList**, as shown in the following code sample:</span></span>  
  
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
  
 <span data-ttu-id="c84f3-111">외에 **Count** 속성을는 **GetEnumerator** 메서드를 제공 하는 a, `foreach` 형식의 검색에 있는 노드의 컬렉션에 대해는 **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="c84f3-111">In addition to the **Count** property, there is a **GetEnumerator** method that provides a, `foreach` style iteration over the collection of nodes in the **XmlNodeList**.</span></span> <span data-ttu-id="c84f3-112">다음 코드 예제에서는 `foreach` 문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c84f3-112">The following code example shows the use of the `foreach` statement.</span></span>  
  
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
  
 <span data-ttu-id="c84f3-113">메서드 및 속성에 대 한 자세한 내용은 **XmlNodeList**, 참조 <xref:System.Xml.XmlNodeList>합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f3-113">For more information on the methods and properties available on the **XmlNodeList**, see <xref:System.Xml.XmlNodeList>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84f3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c84f3-114">See Also</span></span>  
 [<span data-ttu-id="c84f3-115">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="c84f3-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
