---
title: 이름 또는 인덱스별로 정렬되지 않은 노드 검색
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 785a609455a35dd87a9593f00b58fd160ac708e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572943"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="1302a-102">이름 또는 인덱스별로 정렬되지 않은 노드 검색</span><span class="sxs-lookup"><span data-stu-id="1302a-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="1302a-103">**XmlNamedNodeMap**은 W3C(World Wide Web 컨소시엄) 사양에서 NamedNodeMap으로 설명되며 이름이나 인덱스를 사용하여 노드를 참조할 수 있는 정렬되지 않은 노드 집합 처리에 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="1302a-104">**XmlNamedNodeMap**에 액세스할 수 있는 유일한 방법은 메서드나 속성을 통해 **XmlNamedNodeMap**을 반환하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="1302a-105">다음과 같은 세 가지 메서드나 속성이 **XmlNamedNodeMap**을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
-   <span data-ttu-id="1302a-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="1302a-106">XmlElement.Attributes</span></span>  
  
-   <span data-ttu-id="1302a-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="1302a-107">XmlDocumentType.Entities</span></span>  
  
-   <span data-ttu-id="1302a-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="1302a-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="1302a-109">예를 들어, **XmlDocumentType.Entities** 속성은 문서 형식 선언에 선언된 **XmlEntity** 노드의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="1302a-110">이 컬렉션은 **XmlNamedNodeMap**으로 반환되고 **Count** 속성을 사용하여 컬렉션을 반복하고 엔터티 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="1302a-111">**XmlNamedNodeMap**을 반복하는 예를 보려면 <xref:System.Xml.XmlDocumentType.Entities%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1302a-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="1302a-112">**XmlAttributeCollection**은 **XmlNamedNodeMap**에서 파생되며, 표기법 및 엔터티는 읽기 전용이지만 특성의 경우에는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="1302a-113">특성에 대해 **XmlNamedNodeMap**을 사용하면 XML 이름을 기준으로 특성에 대한 노드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="1302a-114">이렇게 하면 요소 노드에서 특성 컬렉션을 손쉽게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="1302a-115">이것은 **IEnumerable** 인터페이스를 구현하지만 문자열 대신 인덱스 접근자를 사용하는 **XmlNodeList**와 반대라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="1302a-116">**RemoveNamedItem** 및 **SetNamedItem** 메서드는 **XmlAttributeCollection**에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="1302a-117">**AttributeCollection** 또는 **XmlNamedNodeMap** 구현을 통해 특성 컬렉션에서 추가하거나 제거하면 요소의 특성 컬렉션이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="1302a-118">다음 코드 예제에서는 특성을 이동하고 새 특성을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 <span data-ttu-id="1302a-119">**AttributeCollection**에서 특성을 제거하는 추가 코드 예제를 보려면 [XmlNamedNodeMap.RemoveNamedItem 메서드](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1302a-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span></span> <span data-ttu-id="1302a-120">메서드 및 속성에 대한 자세한 내용은 [XmlNamedNodeMap 멤버](AllMembers.T:System.Xml.XmlNamedNodeMap)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1302a-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1302a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1302a-121">See Also</span></span>  
 [<span data-ttu-id="1302a-122">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="1302a-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
