---
title: "방법: 전체 XML 트리에 대한 네임스페이스 변경(C#) | Microsoft 문서"
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
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1ce710355e410e123fb9c4129e8d7bf339d5beff
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a>방법: 전체 XML 트리에 대한 네임스페이스 변경(C#)
요소나 특성의 네임스페이스를 프로그래밍 방식으로 변경해야 하는 경우가 있습니다. LINQ to XML을 사용하면 이 작업을 쉽게 수행할 수 있습니다. <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=fullName> 속성은 설정될 수 있습니다. <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=fullName> 속성은 설정될 수 없습니다. 하지만 쉽게 특성을 <xref:System.Collections.Generic.List%601?displayProperty=fullName>에 복사하고 기존 특성을 제거한 다음 원하는 새 네임스페이스에 있는 새 특성을 추가할 수 있습니다.  
  
 자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 네임스페이스에 없는 두 XML 트리를 만든 다음 각 트리의 네임스페이스를 변경하고 이러한 트리를 단일 트리로 결합합니다.  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
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
 [XML 트리 수정(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
