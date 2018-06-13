---
title: 복제와 연결 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 35a265d2aaef40977a9a6b89d174e9a585c525c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640308"
---
# <a name="cloning-vs-attaching-visual-basic"></a>복제와 연결 (Visual Basic)
<xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 포함) 또는 <xref:System.Xml.Linq.XAttribute> 개체를 새 트리에 추가할 때 새 내용에 부모가 없으면 개체가 XML 트리에 추가되기만 합니다. 새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 부모가 있는 요소를 트리에 추가할 때의 동작과 부모가 없는 요소를 트리에 추가할 때의 동작을 보여 줍니다.  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
