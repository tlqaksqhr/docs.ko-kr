---
title: "방법: 전체 XML 트리 (Visual Basic)에 대 한 고 Namespace 변경 | Microsoft 문서"
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
ms.assetid: 1837324b-5cb5-4fa8-95b9-3071efa0f913
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: af216e734c85806056e37d92733a3e4d49f8b73c
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-visual-basic"></a>방법: 전체 XML 트리 (Visual Basic)에 대 한는 Namespace를 변경 합니다.
요소나 특성의 네임스페이스를 프로그래밍 방식으로 변경해야 하는 경우가 있습니다. LINQ to XML을 사용하면 이 작업을 쉽게 수행할 수 있습니다. <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=fullName>속성을 설정할 수 있습니다.</xref:System.Xml.Linq.XElement.Name%2A?displayProperty=fullName> <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=fullName>속성을 설정할 수 있지만 특성을 쉽게 복사할 수는 <xref:System.Collections.Generic.List%601?displayProperty=fullName>, 기존 특성을 제거한 다음 원하는 새 네임 스페이스에 있는 새 특성을 추가 합니다.</xref:System.Collections.Generic.List%601?displayProperty=fullName> </xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=fullName>  
  
 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 네임스페이스에 없는 두 XML 트리를 만든 다음 각 트리의 네임스페이스를 변경하고 이러한 트리를 단일 트리로 결합합니다.  
  
```vb  
Dim tree1 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim tree2 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim ad As XNamespace = "http://www.adatum.com"  
' change the namespace of every element and attribute in the first tree  
For Each el As XElement In tree1.DescendantsAndSelf  
    el.Name = aw.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' change the namespace of every element and attribute in the second tree  
For Each el As XElement In tree2.DescendantsAndSelf()  
    el.Name = ad.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' add attribute namespaces so that the tree will be serialized with  
' the aw and ad namespace prefixes  
tree1.Add( _  
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _  
)  
tree2.Add( _  
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _  
)  
' create a new composite tree  
Dim root As XElement = _  
    <Root>  
        <%= tree1 %>  
        <%= tree2 %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 수정 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
