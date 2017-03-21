---
title: "방법: XmlWriter (LINQ to XML)와 XML 트리 채우기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dfd10ec04e7293d90929d6f629201868028819ad
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a>방법: XmlWriter (LINQ to XML)와 XML 트리 채우기 (Visual Basic)
사용 하는 XML 트리를 채우는 한 가지 방법은 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>만들려는 <xref:System.Xml.XmlWriter>, 한 다음 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 쓸</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> XML 트리 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 에 기록 된 모든 노드에으로 채워집니다.  
  
 일반적으로이 메서드를 사용이 사용 하는 경우 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 써야 하는 다른 클래스와는 <xref:System.Xml.XmlWriter>, <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> 같은</xref:System.Xml.XmlWriter>  
  
## <a name="example"></a>예제  
 사용할 수 있는 하나의 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>경우는 XSLT 변환을 호출할 때입니다.</xref:System.Xml.Linq.XContainer.CreateWriter%2A> 이 예제에서는 XML 트리를 만들고는 <xref:System.Xml.XmlReader>새 문서를 만들고 다음 만듭니다 XML 트리에서 <xref:System.Xml.XmlWriter>새 문서에 쓸 수 있습니다.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> 그런 다음 <xref:System.Xml.XmlReader>및 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> 에 전달 하 여 XSLT 변환을 호출합니다 변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.  
  
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
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A></xref:System.Xml.Linq.XContainer.CreateWriter%2A>   
 <xref:System.Xml.XmlWriter></xref:System.Xml.XmlWriter>   
 <xref:System.Xml.Xsl.XslCompiledTransform></xref:System.Xml.Xsl.XslCompiledTransform>   
 [XML 트리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
