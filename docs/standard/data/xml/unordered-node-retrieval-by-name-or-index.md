---
title: "이름 또는 인덱스별로 정렬되지 않은 노드 검색"
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8bea8f373dced08fd7a2a828255a593533df9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="unordered-node-retrieval-by-name-or-index"></a>이름 또는 인덱스별로 정렬되지 않은 노드 검색
**XmlNamedNodeMap** 에서 World Wide Web Consortium (W3C) 사양에서 NamedNodeMap으로 설명 되며 이름이 나 인덱스에서 노드를 참조할 수 있는 순서가 지정 되지 않은 노드 집합을 처리 하는 데 필요 합니다. 에 액세스할 수 있는 유일한 방법은 **XmlNamedNodeMap** 는 다음 경우에 **XmlNamedNodeMap** 메서드 또는 속성을 통해 반환 됩니다. 세 가지 메서드나 속성을 반환 하는 프로그램 **XmlNamedNodeMap**:  
  
-   XmlElement.Attributes  
  
-   XmlDocumentType.Entities  
  
-   XmlDocumentType.Notations  
  
 예를 들어는 **XmlDocumentType.Entities** 속성의 컬렉션을 가져옵니다 **XmlEntity** 노드는 문서 종류 선언에 선언 합니다. 이 컬렉션으로 반환 됩니다는 **XmlNamedNodeMap**, 및를 사용 하 여 컬렉션을 반복할 수는 **Count** 엔터티 정보 속성 및 표시 합니다. 반복에 대 한 예제는 **XmlNamedNodeMap**, 참조 <xref:System.Xml.XmlDocumentType.Entities%2A>합니다.  
  
 **XmlAttributeCollection** 에서 파생 된 **XmlNamedNodeMap** 와 특성만 수정할 수 있는, 노테이션 및 엔터티는 읽기 전용입니다. 사용 하 여 **XmlNamedNodeMap** 특성의 이름을 기반으로 XML 특성에 대 한 노드를 가져올 수 있습니다. 이렇게 하면 요소 노드에서 특성 컬렉션을 손쉽게 처리할 수 있습니다. 와 직접 비교 될 수 있습니다 **XmlNodeList**, 구현에서 **IEnumerable** 인터페이스를 하지만 문자열 대신 인덱스 접근자 사용 합니다. **RemoveNamedItem** 및 **SetNamedItem** 방법에 대해만 사용 되는 **XmlAttributeCollection**합니다. 에서 추가 또는 제거는 특성 컬렉션을 사용 하는지에 관계 없이 **AttributeCollection** 또는 **XmlNamedNodeMap** 구현 요소의 특성 컬렉션을 수정 합니다. 다음 코드 예제에서는 특성을 이동하고 새 특성을 만드는 방법을 보여 줍니다.  
  
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
  
 특성을에서 제거 되는 추가 코드 예제는 **AttributeCollection**, 참조 [XmlNamedNodeMap.RemoveNamedItem 메서드](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem)합니다. 메서드 및 속성에 대 한 자세한 내용은 참조 하십시오. [XmlNamedNodeMap 멤버](AllMembers.T:System.Xml.XmlNamedNodeMap)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
