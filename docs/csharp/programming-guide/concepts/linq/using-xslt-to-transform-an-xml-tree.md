---
title: "XSLT를 사용하여 XML 트리 변환(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 373a2699-d4c5-471b-9bda-c1f0ab73b477
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0abd857def00bd1e96332cd635d49aa50b2b873b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-xslt-to-transform-an-xml-tree-c"></a><span data-ttu-id="45e0c-102">XSLT를 사용하여 XML 트리 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="45e0c-102">Using XSLT to Transform an XML Tree (C#)</span></span>
<span data-ttu-id="45e0c-103">XML 트리를 만들고 XML 트리에서 <xref:System.Xml.XmlReader>를 만든 다음 새 문서를 만들고 새 문서에 쓸 <xref:System.Xml.XmlWriter>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45e0c-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="45e0c-104">그런 다음 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 변환에 전달하여 XSLT 변환을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45e0c-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="45e0c-105">변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="45e0c-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45e0c-106">예제</span><span class="sxs-lookup"><span data-stu-id="45e0c-106">Example</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="45e0c-107">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="45e0c-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45e0c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45e0c-108">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="45e0c-109">고급 LINQ to XML 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="45e0c-109">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
