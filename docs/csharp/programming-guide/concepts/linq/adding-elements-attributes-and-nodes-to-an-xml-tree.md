---
title: "요소, 특성 및 노드를 XML 트리에 추가(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6894e0685d413297c01118df16d01f7d956ee333
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a>요소, 특성 및 노드를 XML 트리에 추가(C#)
내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.  
  
## <a name="methods-for-adding-content"></a>내용을 추가하는 메서드  
 다음 메서드는 자식 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>에 추가합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<xref:System.Xml.Linq.XContainer>의 자식 내용 끝 부분에 내용을 추가합니다.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<xref:System.Xml.Linq.XContainer>의 자식 내용 시작 부분에 내용을 추가합니다.|  
  
 다음 메서드는 <xref:System.Xml.Linq.XNode>의 형제 노드로 내용을 추가합니다. 유효한 형제 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XText>와 같은 다른 형식의 노드에 추가할 수 있지만, 형제 내용을 추가할 가장 일반적인 노드는 <xref:System.Xml.Linq.XComment>입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<xref:System.Xml.Linq.XNode> 뒤에 내용을 추가합니다.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다.|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.  
  
### <a name="code"></a>코드  
  
```csharp  
XElement srcTree = new XElement("Root",   
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
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
 [XML 트리 수정(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

