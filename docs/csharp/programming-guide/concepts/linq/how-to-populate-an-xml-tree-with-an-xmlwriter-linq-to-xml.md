---
title: "방법: XmlWriter를 사용하여 XML 트리 채우기(LINQ to XML)(C#)"
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
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9d74e6bd3d8454f5ed37fa8d190beb0c44399fa7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="7e9a3-102">방법: XmlWriter를 사용하여 XML 트리 채우기(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="7e9a3-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7e9a3-103">XML 트리를 채우는 한 가지 방법은 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>를 사용하여 <xref:System.Xml.XmlWriter>를 만든 다음 <xref:System.Xml.XmlWriter>에 쓰는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7e9a3-104">XML 트리는 <xref:System.Xml.XmlWriter>에 쓴 모든 노드로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="7e9a3-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에 써야 하는 <xref:System.Xml.XmlWriter> 등의 다른 클래스와 함께 <xref:System.Xml.Xsl.XslCompiledTransform>을 사용할 때 이 메서드를 일반적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e9a3-106">예제</span><span class="sxs-lookup"><span data-stu-id="7e9a3-106">Example</span></span>  
 <span data-ttu-id="7e9a3-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A>를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="7e9a3-108">이 예제에서는 XML 트리를 만들고 XML 트리에서 <xref:System.Xml.XmlReader>를 만든 다음 <xref:System.Xml.XmlWriter>를 만들어 새 문서에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="7e9a3-109">그런 다음 XSLT 변환을 호출하여 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7e9a3-110">변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="7e9a3-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9a3-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e9a3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e9a3-112">See Also</span></span>  
 <span data-ttu-id="7e9a3-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="7e9a3-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span></span>   
 <span data-ttu-id="7e9a3-114"><xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="7e9a3-114"><xref:System.Xml.XmlWriter></span></span>   
 <span data-ttu-id="7e9a3-115"><xref:System.Xml.Xsl.XslCompiledTransform></span><span class="sxs-lookup"><span data-stu-id="7e9a3-115"><xref:System.Xml.Xsl.XslCompiledTransform></span></span>   
 [<span data-ttu-id="7e9a3-116">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="7e9a3-116">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

