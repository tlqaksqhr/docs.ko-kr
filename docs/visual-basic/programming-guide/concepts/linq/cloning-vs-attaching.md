---
title: "복제와 (Visual Basic)를 연결 합니다. | Microsoft 문서"
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
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 81cbcb066d60851ba83bd4d783d34f8dd3bd1fac
ms.lasthandoff: 03/13/2017

---
# <a name="cloning-vs-attaching-visual-basic"></a>복제와 연결 (Visual Basic)
추가 하는 경우 <xref:System.Xml.Linq.XNode>(포함 하 여 <xref:System.Xml.Linq.XElement>) 또는 <xref:System.Xml.Linq.XAttribute>개체는 새 트리를 새 내용에 부모가 없는 경우 개체 되기만 XML 트리에.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode> 새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.  
  
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
 [XML 트리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
