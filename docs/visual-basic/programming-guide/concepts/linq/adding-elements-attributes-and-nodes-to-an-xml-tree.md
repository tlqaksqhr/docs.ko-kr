---
title: "XML 트리 (Visual Basic)를 요소, 특성 및 노드 추가 | Microsoft 문서"
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
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b8a1644757fb4ce9f1498e79b16d1077e412346b
ms.lasthandoff: 03/13/2017


---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a>XML 트리 (Visual Basic)를 요소, 특성 및 노드 추가
내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.  
  
## <a name="methods-for-adding-content"></a>내용을 추가하는 메서드  
 다음 방법 자식 콘텐츠를 추가 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A>|<xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 끝에 콘텐츠를 추가합니다.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A>|<xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 시작 부분에 내용을 추가합니다|  
  
 다음 방법 <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 의 형제 노드로 내용을 추가합니다 <xref:System.Xml.Linq.XElement>유효한 형제 콘텐츠 노드 <xref:System.Xml.Linq.XText>또는 <xref:System.Xml.Linq.XComment>.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XText> 와 같은 다른 형식에 추가할 수는 있지만,</xref:System.Xml.Linq.XElement> 형제 내용을 추가할 가장 일반적인 노드는  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 후 콘텐츠를 추가합니다.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.  
  
### <a name="code"></a>코드  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
  
```  
  
### <a name="comments"></a>설명  
 이 코드의 결과는 다음과 같습니다.  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 수정 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
