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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e1af87fceb9f3f7eae6af6f917037ba80908827
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="edb2a-102">XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edb2a-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="edb2a-103">사용 하는 경우는 <xref:System.Xml?displayProperty=fullName>의 상호 운용성 기능 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], <xref:System.Xml.Linq.XNode.CreateReader%2A> <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 만드는 데</xref:System.Xml.Linq.XNode.CreateReader%2A> 사용할 수</xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edb2a-103">When you use the <xref:System.Xml?displayProperty=fullName> interoperability capabilities of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="edb2a-104">읽는 모듈 <xref:System.Xml.XmlReader>XML 트리에서 노드를 읽고 하 고 적절 하 게 처리 합니다.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="edb2a-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="edb2a-105">XSLT 변환 호출</span><span class="sxs-lookup"><span data-stu-id="edb2a-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="edb2a-106">이 메서드를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="edb2a-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="edb2a-107">만들고 XML 트리를 만들 수는 <xref:System.Xml.XmlReader>에서 XML 트리를 새 문서를 만든 다음 만들고는 <xref:System.Xml.XmlWriter>새 문서에 쓸 수 있습니다.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="edb2a-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="edb2a-108">그런 다음 <xref:System.Xml.XmlReader>및 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> 에 전달 하 여 XSLT 변환을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb2a-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="edb2a-109">변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="edb2a-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="edb2a-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edb2a-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edb2a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edb2a-111">See Also</span></span>  
 [<span data-ttu-id="edb2a-112">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="edb2a-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
