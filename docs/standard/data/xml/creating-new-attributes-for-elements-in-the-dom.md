---
title: "DOM에서 요소의 새 특성 만들기"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="afda6-102">DOM에서 요소의 새 특성 만들기</span><span class="sxs-lookup"><span data-stu-id="afda6-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="afda6-103">새 특성을 만드는 차이가 있는 특성, 노드는 않지만 요소 노드의 속성 이며에 포함 하기 때문에 다른 노드 형식을 만드는 것 보다는 **XmlAttributeCollection** 요소와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="afda6-104">다음과 같은 여러 가지 방법으로 특성을 만들고 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="afda6-105">요소 노드 및 사용 하 여 **SetAttribute** 해당 요소의 특성 컬렉션에 특성을 추가 하려면.</span><span class="sxs-lookup"><span data-stu-id="afda6-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="afda6-106">만들기는 **XmlAttribute** 사용 하 여 노드는 **CreateAttribute** 메서드, 요소 노드를 가져오고 다음 사용 하 여 **SetAttributeNode** 있는 특성 컬렉션에 노드를 추가 하려면 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="afda6-107">특성을 사용 하 여 요소를 추가 하는 방법을 보여 주는 다음 예제는 **SetAttribute** 메서드.</span><span class="sxs-lookup"><span data-stu-id="afda6-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
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
  
 <span data-ttu-id="afda6-108">다음 예제에서는 새 특성을 만들고 사용 하 여 **CreateAttribute** 메서드.</span><span class="sxs-lookup"><span data-stu-id="afda6-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="afda6-109">다음의 특성 컬렉션에 추가 특성을 표시는 **책** 사용 하 여 요소는 **SetAttributeNode** 메서드.</span><span class="sxs-lookup"><span data-stu-id="afda6-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="afda6-110">다음과 같은 XML을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="afda6-111">새 특성을 만들어 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="afda6-112">새로 만든 특성을 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="afda6-113">**출력**</span><span class="sxs-lookup"><span data-stu-id="afda6-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="afda6-114">전체 코드 샘플에서 찾을 수 있습니다 <xref:System.Xml.XmlDocument.CreateAttribute%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="afda6-115">만들 수도 있습니다는 **XmlAttribute** 노드는 **InsertBefore** 또는 **InsertAfter** 컬렉션의 적절 한 위치에 배치 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="afda6-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="afda6-116">동일한 이름의 특성이 기존 특성 컬렉션에 이미 있으면 **XmlAttribute** 컬렉션에서 새 노드가 제거 **XmlAttribute** 노드가 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="afda6-117">이 동일한 방식으로 수행 된 **SetAttribute** 메서드.</span><span class="sxs-lookup"><span data-stu-id="afda6-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="afda6-118">이러한 메서드를 매개 변수로, 작업을 수행 하는 참조 지점으로 기존 노드는 **InsertBefore** 및 **InsertAfter**합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="afda6-119">에 대 한 기본 새 노드의 삽입 위치를 나타내는 참조 노드를 제공 하지 않으면는 **InsertAfter** 메서드는 컬렉션의 시작 부분에 새 노드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="afda6-120">에 대 한 기본 위치는 **InsertBefore**없는 참조 노드가 제공 하는 경우는 컬렉션의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="afda6-121">만든 경우는 **XmlNamedNodeMap** 특성의 이름을 사용 하 여 특성을 추가할 수는 <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="afda6-122">자세한 내용은 참조 [NamedNodeMaps 및 NodeLists의 노드 컬렉션](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="afda6-123">기본 특성</span><span class="sxs-lookup"><span data-stu-id="afda6-123">Default Attributes</span></span>  
 <span data-ttu-id="afda6-124">기본 특성을 포함하도록 선언된 요소를 만들면 새 기본 특성이 XML DOM(문서 개체 모델)에서 해당 기본값과 함께 만들어지고 해당 요소에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="afda6-125">이때 기본 특성의 자식 노드도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="afda6-126">특성 자식 노드</span><span class="sxs-lookup"><span data-stu-id="afda6-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="afda6-127">특성 노드 값은 자신의 자식 노드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="afda6-128">유효한 자식 노드에 두 가지: **XmlText** 노드 및 **XmlEntityReference** 노드.</span><span class="sxs-lookup"><span data-stu-id="afda6-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="afda6-129">자식 노드의 의미에서와 같은 해당 메서드를 이들은 **FirstChild** 및 **LastChild** 자식 노드로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="afda6-130">자식 노드가 있는 특성의 이와 같은 차이점은 특성이나 특성 자식 노드를 제거하려는 경우에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="afda6-131">자세한 내용은 참조 [DOM의 요소 노드에서 특성 제거](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afda6-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afda6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afda6-132">See Also</span></span>  
 [<span data-ttu-id="afda6-133">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="afda6-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
