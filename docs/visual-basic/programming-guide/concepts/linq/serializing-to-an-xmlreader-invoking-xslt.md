---
title: "XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
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
ms.openlocfilehash: bca1e63bbe5b3ccd13f183c3cc6081917624ad94
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a>XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic)
사용 하는 경우는 <xref:System.Xml?displayProperty=fullName>의 상호 운용성 기능 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], <xref:System.Xml.Linq.XNode.CreateReader%2A> <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 만드는 데</xref:System.Xml.Linq.XNode.CreateReader%2A> 사용할 수</xref:System.Xml?displayProperty=fullName> 읽는 모듈 <xref:System.Xml.XmlReader>XML 트리에서 노드를 읽고 하 고 적절 하 게 처리 합니다.</xref:System.Xml.XmlReader>  
  
## <a name="invoking-an-xslt-transformation"></a>XSLT 변환 호출  
 이 메서드를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다. 만들고 XML 트리를 만들 수는 <xref:System.Xml.XmlReader>에서 XML 트리를 새 문서를 만든 다음 만들고는 <xref:System.Xml.XmlWriter>새 문서에 쓸 수 있습니다.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> 그런 다음 <xref:System.Xml.XmlReader>및 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> 에 전달 하 여 XSLT 변환을 호출할 수 있습니다. 변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.  
  
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
