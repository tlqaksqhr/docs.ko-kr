---
title: 변형 과정에서 XPathNavigator의 역할
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76cfa51c7d434a6dfdcdc1e6852779decaa601e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="9b680-102">변형 과정에서 XPathNavigator의 역할</span><span class="sxs-lookup"><span data-stu-id="9b680-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="9b680-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 데이터에 대한 임의의 읽기 전용 액세스를 제공하며 XSLT(Extensible Stylesheet Language for Transformations)의 입력으로 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="9b680-104">이 클래스는 <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument> 및 <xref:System.Xml.XmlDocument>에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="9b680-105"><xref:System.Xml.XPath.XPathNavigator>는 XPath(XML Path Language) 권장 사항의 5단원에서 설명하는 W3C(World Wide Web 컨소시엄) 데이터 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="9b680-106"><xref:System.Xml.XPath.XPathNavigator>는 모든 저장소에 대한 커서 모델을 정의하며 모든 데이터 저장소에 대한 빠른 속도의 읽기 전용 XPath 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="9b680-107">또한 <xref:System.Xml.XPath.XPathNavigator>는 결과 트리 조각을 반복하는 데 사용되는 클래스이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="9b680-108">API를 사용하면 저장소의 현재 노드에서 정보를 가져오고 연결된 노드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="9b680-109"><xref:System.Xml.XPath.XPathNavigator>는 일련의 **Move** 메서드를 사용하여 저장소를 순회하는 커서 스타일 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="9b680-110"><xref:System.Xml.XPath.XPathNavigator>는 항상 노드에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="9b680-111">**Move** 메서드가 실패하더라도 <xref:System.Xml.XPath.XPathNavigator>는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="9b680-112"><xref:System.Xml.XPath.XPathNavigator>는 결과 트리 조각을 반복하는 데 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="9b680-113">다음 코드 샘플에서는 XML을 포함하는 `fragment` 매개 변수로 함수를 호출하여 스타일시트 내부에서 결과 트리 조각을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="9b680-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="9b680-114">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="9b680-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="9b680-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="9b680-116">다음 코드에서는 **test.xsl** 스타일시트와 **test.xml** 입력 데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
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
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a><span data-ttu-id="9b680-117">출력</span><span class="sxs-lookup"><span data-stu-id="9b680-117">Output</span></span>  
 <span data-ttu-id="9b680-118">변환 결과는 **out.xml** 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b680-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b680-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b680-119">See Also</span></span>  
 [<span data-ttu-id="9b680-120">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="9b680-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
