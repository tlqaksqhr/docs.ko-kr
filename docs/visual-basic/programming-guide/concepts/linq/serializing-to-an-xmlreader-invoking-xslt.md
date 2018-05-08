---
title: XmlReader (XSLT 호출)에 대 한 직렬화 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: 05754593f4f30683ffabecaa8e16c35bf836a3f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a>XmlReader (XSLT 호출)에 대 한 직렬화 (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 <xref:System.Xml?displayProperty=nameWithType> 상호 운용성 기능을 사용할 때 <xref:System.Xml.Linq.XNode.CreateReader%2A>를 사용하여 <xref:System.Xml.XmlReader>를 만들 수 있습니다. 만들어진 <xref:System.Xml.XmlReader>에서 읽는 모듈은 XML 트리에서 노드를 읽고 적절하게 처리합니다.  
  
## <a name="invoking-an-xslt-transformation"></a>XSLT 변환 호출  
 이 메서드를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다. XML 트리를 만들고 XML 트리에서 <xref:System.Xml.XmlReader>를 만든 다음 새 문서를 만들고 새 문서에 쓸 <xref:System.Xml.XmlWriter>를 만들 수 있습니다. 그런 다음 XSLT 변환을 호출하여 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 전달할 수 있습니다. 변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
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
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic)를 직렬화 하는 작업](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
