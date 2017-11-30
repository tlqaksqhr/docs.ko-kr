---
title: "변형 과정에서 XPathNodeIterator의 역할"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28877f10e11f2eebdcbcc8ff75854551302e3f66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xpathnodeiterator-in-transformations"></a><span data-ttu-id="775d9-102">변형 과정에서 XPathNodeIterator의 역할</span><span class="sxs-lookup"><span data-stu-id="775d9-102">XPathNodeIterator in Transformations</span></span>
<span data-ttu-id="775d9-103"><xref:System.Xml.XPath.XPathNodeIterator>는 XPath(XML Path Language) 쿼리의 결과로 만들어진 노드 집합이나 노드 집합 메서드를 사용하여 노드 집합으로 변환된 결과 트리 조각을 반복하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-103">The <xref:System.Xml.XPath.XPathNodeIterator> provides methods to iterate over a set of nodes created as the result of an XML Path Language (XPath) query or a result tree fragment converted to a node set by use of the node-set method.</span></span> <span data-ttu-id="775d9-104"><xref:System.Xml.XPath.XPathNodeIterator>를 사용하면 해당 노드 집합 내의 노드를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-104">The <xref:System.Xml.XPath.XPathNodeIterator> enables you to iterate over the nodes within that node set.</span></span> <span data-ttu-id="775d9-105">노드 집합을 검색한 후 <xref:System.Xml.XPath.XPathNodeIterator> 클래스는 선택한 노드 집합에 대해 앞으로만 이동 가능한 읽기 전용 커서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-105">Once a node set is retrieved, the <xref:System.Xml.XPath.XPathNodeIterator> class provides a read-only, forward-only cursor to the selected set of nodes.</span></span> <span data-ttu-id="775d9-106">노드 집합은 문서 순서에 따라 만들어지므로 이 메서드를 호출하면 문서 순서에서 다음 노드로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-106">The node set is created in document order, so calling this method moves to the next node in document order.</span></span> <span data-ttu-id="775d9-107"><xref:System.Xml.XPath.XPathNodeIterator>는 집합에 속하는 모든 노드의 노드 트리를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-107"><xref:System.Xml.XPath.XPathNodeIterator> does not build a node tree of all the nodes in the set.</span></span> <span data-ttu-id="775d9-108">대신 트리에서 이동하는 것을 나타내는 원본으로 사용하는 노드를 노출하는 데이터에 대한 단일 노드 창을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-108">Instead, it provides a single node window into the data, exposing the underlying node it points to as you move around in the tree.</span></span> <span data-ttu-id="775d9-109"><xref:System.Xml.XPath.XPathNodeIterator> 클래스에서 사용할 수 있는 메서드 및 속성을 통해 현재 노드에서 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-109">The methods and properties available from the <xref:System.Xml.XPath.XPathNodeIterator> class enable you to get information from the current node.</span></span> <span data-ttu-id="775d9-110">사용할 수 있는 메서드 및 속성 목록에 대 한 참조 <xref:System.Windows.Forms.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-110">For a list of the available methods and properties, see <xref:System.Windows.Forms.ToolBar>.</span></span>  
  
 <span data-ttu-id="775d9-111"><xref:System.Xml.XPath.XPathNodeIterator>는 XPath 쿼리에서 만든 노드 집합에서 앞으로만 이동하기 때문에 이동 방법은 <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-111">Since an <xref:System.Xml.XPath.XPathNodeIterator> moves over a set of nodes created from an XPath query and moves forward only, the way to move is by using the <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> method.</span></span> <span data-ttu-id="775d9-112">이 메서드의 반환 형식은 `Boolean`이며 선택된 다음 노드로 이동할 경우 `true`를, 더 이상 선택된 노드가 없는 경우에는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-112">The return type of this method is `Boolean`, returning `true` if it moves to the next selected node, and `false` if there are no more selected nodes.</span></span> <span data-ttu-id="775d9-113">다음은 `true`가 반환되는 경우에 사용할 수 있는 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-113">If it returns `true`, the following list shows the properties available:</span></span>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 <span data-ttu-id="775d9-114">노드 집합을 처음 확인하는 경우에는 <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A>를 호출하여 <xref:System.Xml.XPath.XPathNodeIterator>를 선택된 집합의 첫 번째 노드에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-114">When you are looking at a node set for the first time, a call to <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> must be made to position the <xref:System.Xml.XPath.XPathNodeIterator> on the first node of the selected set.</span></span> <span data-ttu-id="775d9-115">그러면 while 루프를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-115">This allows a while loop to be written.</span></span>  
  
 <span data-ttu-id="775d9-116">다음 코드 예제에서는 <xref:System.Xml.XPath.XPathNodeIterator>를 <xref:System.Xml.Xsl.XslTransform>의 매개 변수로 <xref:System.Xml.Xsl.XsltArgumentList>에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-116">The following code example shows how to pass an <xref:System.Xml.XPath.XPathNodeIterator> to an <xref:System.Xml.Xsl.XslTransform> as a parameter in the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span> <span data-ttu-id="775d9-117">코드에 대 한 입력은 **books.xml**, 스타일 시트가 및 **text.xsl**합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-117">The input to the code is **books.xml**, and the style sheet is **text.xsl**.</span></span> <span data-ttu-id="775d9-118">파일 **test.xml** 는 <xref:System.Xml.XPath.XPathDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="775d9-118">The file **test.xml** is the <xref:System.Xml.XPath.XPathDocument>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
   End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## <a name="booksxml"></a><span data-ttu-id="775d9-119">books.xml</span><span class="sxs-lookup"><span data-stu-id="775d9-119">books.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## <a name="testxsl"></a><span data-ttu-id="775d9-120">test.xsl</span><span class="sxs-lookup"><span data-stu-id="775d9-120">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="775d9-121">test.xml</span><span class="sxs-lookup"><span data-stu-id="775d9-121">test.xml</span></span>  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a><span data-ttu-id="775d9-122">출력(out.xml)</span><span class="sxs-lookup"><span data-stu-id="775d9-122">Output (out.xml)</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a><span data-ttu-id="775d9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="775d9-123">See Also</span></span>  
 [<span data-ttu-id="775d9-124">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="775d9-124">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
