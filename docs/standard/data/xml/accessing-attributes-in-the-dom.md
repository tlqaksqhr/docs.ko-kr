---
title: "DOM에서 특성 액세스"
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
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="2cb32-102">DOM에서 특성 액세스</span><span class="sxs-lookup"><span data-stu-id="2cb32-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="2cb32-103">특성은 요소의 자식 항목이 아닌, 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="2cb32-104">이러한 구분은 XML DOM(문서 개체 모델)의 형제, 부모 및 자식 노드를 탐색하는 데 사용되는 메서드로 인하여 중요하게 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="2cb32-105">예를 들어는 **PreviousSibling** 및 **NextSibling** 특성 사이 또는 특성에 요소에서 탐색 하는 메서드가 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="2cb32-106">대신 특성은 요소의 속성 및 요소에 의해 소유, 수 있는 **OwnerElement** 속성 및 not는 **parentNode** 속성을 고유한 탐색 메서드를 있으며 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="2cb32-107">사용 하 여 현재 노드가 요소 이면는 **HasAttribute** 요소와 연관 된 특성이 있는지 확인 하기 위해 메서드.</span><span class="sxs-lookup"><span data-stu-id="2cb32-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="2cb32-108">요소에 특성이 있다고 확인되면 특성에 액세스하기 위한 여러 메서드가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="2cb32-109">요소에서 단일 특성을 검색 하려면 사용할 수 있습니다는 **GetAttribute** 및 **GetAttributeNode** 의 메서드는 **XmlElement** 하거나 모든 특성을 가져올 수 있습니다 에 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="2cb32-110">컬렉션에 대한 반복 작업이 필요한 경우 컬렉션을 가져오는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="2cb32-111">요소의 모든 특성이 사용 된 **특성** 컬렉션으로 모든 특성을 검색 하는 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="2cb32-112">모든 특성을 컬렉션으로 가져오기</span><span class="sxs-lookup"><span data-stu-id="2cb32-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="2cb32-113">모든 요소 노드 특성을 컬렉션으로, 호출 된 **XmlElement.Attributes** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="2cb32-114">이 **XmlAttributeCollection** 요소의 모든 특성이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="2cb32-115">**XmlAttributeCollection** 클래스에서 상속 된 **XmlNamedNode** 지도입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="2cb32-116">따라서 메서드 및 속성 컬렉션에서 사용할 수 있는 포함 된 명명 된 노드 맵에서 사용할 수 있는 것 뿐만 아니라 메서드와 관련 된 속성에는 **XmlAttributeCollection** 클래스 같은 **ItemOf**  속성 또는 **Append** 메서드.</span><span class="sxs-lookup"><span data-stu-id="2cb32-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="2cb32-117">특성 컬렉션에서 각 항목은 나타냅니다는 **XmlAttribute** 노드.</span><span class="sxs-lookup"><span data-stu-id="2cb32-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="2cb32-118">요소에 특성의 수를 찾으려면 가져오기는 **XmlAttributeCollection**, 사용 하 여는 **Count** 속성을 참조 하십시오 개수 **XmlAttribute** 노드 컬렉션에 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="2cb32-119">다음 코드 예제에서는 특성을 검색 하는 방법을 보여 줍니다. 컬렉션을 사용 하는 **Count** 메서드 반복 인덱스에 대 한 전체를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="2cb32-120">그런 다음 컬렉션에서 단일 특성을 검색한 후 해당 값을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.   
        Dim myElement As XmlElement = doc.DocumentElement  
  
        ' Create an attribute collection from the element.  
        Dim attrColl As XmlAttributeCollection = myElement.Attributes  
  
        ' Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...")  
        Dim i As Integer  
        For i = 0 To attrColl.Count - 1  
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)  
            Console.Write("{0}", attrColl.ItemOf(i).Value)  
            Console.WriteLine()  
        Next  
  
        ' Retrieve a single attribute from the collection; specifically, the  
        ' attribute with the name "misc".  
        Dim attr As XmlAttribute = attrColl("misc")  
  
        ' Retrieve the value from that attribute.  
        Dim miscValue As String = attr.InnerXml  
  
        Console.WriteLine("Display the attribute information.")  
        Console.WriteLine(miscValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  
    public static void Main()  
    {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +  
                      "<title>The Handmaid's Tale</title>" +  
                      "<price>14.95</price>" +  
                      "</book>");  
  
        // Move to an element.  
        XmlElement myElement = doc.DocumentElement;  
  
        // Create an attribute collection from the element.  
        XmlAttributeCollection attrColl = myElement.Attributes;  
  
        // Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...");  
        for (int i = 0; i < attrColl.Count; i++)  
        {  
            Console.Write("{0} = ", attrColl[i].Name);  
            Console.Write("{0}", attrColl[i].Value);  
            Console.WriteLine();  
        }  
  
        // Retrieve a single attribute from the collection; specifically, the  
        // attribute with the name "misc".  
        XmlAttribute attr = attrColl["misc"];  
  
        // Retrieve the value from that attribute.  
        String miscValue = attr.InnerXml;  
  
        Console.WriteLine("Display the attribute information.");  
        Console.WriteLine(miscValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="2cb32-121">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="2cb32-122">**출력**</span><span class="sxs-lookup"><span data-stu-id="2cb32-122">**Output**</span></span>  
  
 <span data-ttu-id="2cb32-123">컬렉션의 모든 특성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="2cb32-124">특성 컬렉션의 정보는 이름이나 인덱스 번호로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="2cb32-125">위의 예제는 이름으로 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="2cb32-126">다음 예제는 인덱스 번호로 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="2cb32-127">때문에 **XmlAttributeCollection** 컬렉션 이며 반복 되 이름 또는 인덱스를 하나씩 보여 주는이 예제 0 기반 인덱스를 사용 하 고 다음 파일을 사용 하 여 컬렉션에서 첫 번째 특성을 선택 하면 **baseuri.xml**입력으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="2cb32-128">입력</span><span class="sxs-lookup"><span data-stu-id="2cb32-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.Load("http://localhost/baseuri.xml")  
  
        ' Display information on the attribute node. The value  
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.  
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)  
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)  
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)  
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
    End Sub 'Main   
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    // Create the XmlDocument.  
    XmlDocument doc = new XmlDocument();  
  
    doc.Load("http://localhost/baseuri.xml");  
  
    // Display information on the attribute node. The value  
    // returned for BaseURI is 'http://localhost/baseuri.xml'.  
    XmlAttribute attr = doc.DocumentElement.Attributes[0];  
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);  
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);  
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="2cb32-129">개별 특성 노드 검색</span><span class="sxs-lookup"><span data-stu-id="2cb32-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="2cb32-130">요소에서 단일 특성 노드를 검색하려면 <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="2cb32-131">형식의 개체를 반환 **XmlAttribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="2cb32-132">있으면는 **XmlAttribute**, 모든 메서드 및 속성에서 사용할 수는 <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> 찾기 등의 해당 개체에서 사용할 수 있는 클래스는 **OwnerElement**합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.  
        Dim root As XmlElement  
        root = doc.DocumentElement  
  
        ' Get an attribute.  
        Dim attr As XmlAttribute  
        attr = root.GetAttributeNode("ISBN")  
  
        ' Display the value of the attribute.  
        Dim attrValue As String  
        attrValue = attr.InnerXml  
        Console.WriteLine(attrValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
 public class Sample  
 {  
      public static void Main()  
      {  
    XmlDocument doc = new XmlDocument();  
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +  
                   "<title>The Handmaid's Tale</title>" +  
                   "<price>14.95</price>" +  
                   "</book>");   
  
    // Move to an element.  
     XmlElement root = doc.DocumentElement;  
  
    // Get an attribute.  
     XmlAttribute attr = root.GetAttributeNode("ISBN");  
  
    // Display the value of the attribute.  
     String attrValue = attr.InnerXml;  
     Console.WriteLine(attrValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="2cb32-133">또한 단일 특성 노드가 특성 컬렉션에서 검색되는 앞의 예제와 같이 이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="2cb32-134">다음 코드 예제에서는 한 줄의 코드 수에서 기록 될 단일 특성 검색 인덱스 번호로 XML 문서의 루트 방법을 트리, 라고도 **DocumentElement** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb32-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cb32-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cb32-135">See Also</span></span>  
 [<span data-ttu-id="2cb32-136">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="2cb32-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
