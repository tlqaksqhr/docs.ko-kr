---
title: DOM에서 요소의 새 특성 만들기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb1a337c2795627b82125c8c29335c52b5fb332c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570386"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="3454f-102">DOM에서 요소의 새 특성 만들기</span><span class="sxs-lookup"><span data-stu-id="3454f-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="3454f-103">특성은 노드가 아니라 요소 노드의 속성이며 요소와 연결된 **XmlAttributeCollection**에 포함되어 있으므로 새 특성을 만드는 것은 다른 노드 형식을 만드는 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="3454f-104">다음과 같은 여러 가지 방법으로 특성을 만들고 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="3454f-105">요소 노드를 가져오고 **SetAttribute**를 사용하여 특성을 해당 요소의 특성 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="3454f-106">**CreateAttribute** 메서드를 사용하여 **XmlAttribute** 노드를 만들고, 요소 노드를 가져온 다음, **SetAttributeNode**를 사용하여 해당 요소의 특성 컬렉션에 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="3454f-107">다음 예제는 **SetAttribute** 메서드를 사용하여 요소에 특성을 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
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
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="3454f-108">다음 예제는 **CreateAttribute** 메서드를 사용하여 새 특성을 만든 후</span><span class="sxs-lookup"><span data-stu-id="3454f-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="3454f-109">**SetAttributeNode** 메서드를 사용하여 **book** 요소의 특성 컬렉션에 해당 특성을 추가하는 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="3454f-110">다음과 같은 XML을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="3454f-111">새 특성을 만들어 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="3454f-112">새로 만든 특성을 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="3454f-113">**출력**</span><span class="sxs-lookup"><span data-stu-id="3454f-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="3454f-114">전체 코드 샘플은 <xref:System.Xml.XmlDocument.CreateAttribute%2A>에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="3454f-115">또한 **XmlAttribute** 노드를 만들고 **InsertBefore** 또는 **InsertAfter** 메서드를 사용하여 해당 노드를 컬렉션의 적절한 위치에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="3454f-116">동일한 이름의 특성이 이미 특성 컬렉션에 있는 경우 기존 **XmlAttribute** 노드가 컬렉션에서 제거되고 새 **XmlAttribute** 노드가 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="3454f-117">이는 **SetAttribute** 메서드와 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="3454f-118">이러한 메서드는 **InsertBefore** 및 **InsertAfter**를 수행하는 참조 위치로 기존 노드를 사용합니다(매개 변수로).</span><span class="sxs-lookup"><span data-stu-id="3454f-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="3454f-119">새 노드의 삽입 위치를 나타내는 참조 노드를 제공하지 않으면 **InsertAfter** 메서드는 기본적으로 컬렉션의 처음에 새 노드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="3454f-120">참조 노드가 제공되지 않을 경우 **InsertBefore**의 기본 위치는 컬렉션의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="3454f-121">특성의 **XmlNamedNodeMap**을 만든 경우 <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>을 사용하여 이름에 따라 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="3454f-122">자세한 내용은 [NamedNodeMaps 및 NodeLists의 노드 컬렉션](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3454f-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="3454f-123">기본 특성</span><span class="sxs-lookup"><span data-stu-id="3454f-123">Default Attributes</span></span>  
 <span data-ttu-id="3454f-124">기본 특성을 포함하도록 선언된 요소를 만들면 새 기본 특성이 XML DOM(문서 개체 모델)에서 해당 기본값과 함께 만들어지고 해당 요소에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="3454f-125">이때 기본 특성의 자식 노드도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="3454f-126">특성 자식 노드</span><span class="sxs-lookup"><span data-stu-id="3454f-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="3454f-127">특성 노드 값은 자신의 자식 노드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="3454f-128">유효한 자식 노드에는 **XmlText** 노드와 **XmlEntityReference** 노드의 두 가지 형식만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="3454f-129">**FirstChild** 및 **LastChild**와 같은 메서드에서 이러한 형식의 노드를 자식 노드로 처리한다는 점에서 이러한 형식의 노드는 자식 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="3454f-130">자식 노드가 있는 특성의 이와 같은 차이점은 특성이나 특성 자식 노드를 제거하려는 경우에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3454f-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="3454f-131">자세한 내용은 [DOM의 요소 노드에서 특성 제거](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3454f-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3454f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3454f-132">See Also</span></span>  
 [<span data-ttu-id="3454f-133">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="3454f-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
