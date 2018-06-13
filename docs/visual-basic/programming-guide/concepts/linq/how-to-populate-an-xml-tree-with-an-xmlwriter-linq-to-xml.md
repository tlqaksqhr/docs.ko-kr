---
title: '방법: XmlWriter (LINQ to XML)와 XML 트리 채우기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
ms.openlocfilehash: bc17b84b945e93443ab6d9f337e852feba5b0662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642105"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="63fb4-102">방법: XmlWriter (LINQ to XML)와 XML 트리 채우기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63fb4-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="63fb4-103">XML 트리를 채우는 한 가지 방법은 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>를 사용하여 <xref:System.Xml.XmlWriter>를 만든 다음 <xref:System.Xml.XmlWriter>에 쓰는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="63fb4-104">XML 트리는 <xref:System.Xml.XmlWriter>에 쓴 모든 노드로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="63fb4-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에 써야 하는 <xref:System.Xml.XmlWriter> 등의 다른 클래스와 함께 <xref:System.Xml.Xsl.XslCompiledTransform>을 사용할 때 이 메서드를 일반적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63fb4-106">예제</span><span class="sxs-lookup"><span data-stu-id="63fb4-106">Example</span></span>  
 <span data-ttu-id="63fb4-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A>를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="63fb4-108">이 예제에서는 XML 트리를 만들고 XML 트리에서 <xref:System.Xml.XmlReader>를 만든 다음 <xref:System.Xml.XmlWriter>를 만들어 새 문서에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="63fb4-109">그런 다음 XSLT 변환을 호출하여 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="63fb4-110">변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="63fb4-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63fb4-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63fb4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63fb4-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>  
 <xref:System.Xml.XmlWriter>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [<span data-ttu-id="63fb4-113">XML 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63fb4-113">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
