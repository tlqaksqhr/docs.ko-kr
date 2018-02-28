---
title: "변형 과정에서 XPathNavigator의 역할"
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
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c492d470fe29041f32039d98ecb854e18f40423c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="xpathnavigator-in-transformations"></a>변형 과정에서 XPathNavigator의 역할
<xref:System.Xml.XPath.XPathNavigator> 클래스는 데이터에 대한 임의의 읽기 전용 액세스를 제공하며 XSLT(Extensible Stylesheet Language for Transformations)의 입력으로 사용하도록 디자인되었습니다. 이 클래스는 <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument> 및 <xref:System.Xml.XmlDocument>에서 구현합니다. <xref:System.Xml.XPath.XPathNavigator>는 XPath(XML Path Language) 권장 사항의 5단원에서 설명하는 W3C(World Wide Web 컨소시엄) 데이터 모델을 기반으로 합니다.  
  
 <xref:System.Xml.XPath.XPathNavigator>는 모든 저장소에 대한 커서 모델을 정의하며 모든 데이터 저장소에 대한 빠른 속도의 읽기 전용 XPath 쿼리를 제공합니다. 또한 <xref:System.Xml.XPath.XPathNavigator>는 결과 트리 조각을 반복하는 데 사용되는 클래스이기도 합니다.  
  
 API를 사용하면 저장소의 현재 노드에서 정보를 가져오고 연결된 노드로 이동할 수 있습니다. <xref:System.Xml.XPath.XPathNavigator>는 일련의 **Move** 메서드를 사용하여 저장소를 순회하는 커서 스타일 모델입니다. <xref:System.Xml.XPath.XPathNavigator>는 항상 노드에 위치합니다. **Move** 메서드가 실패하더라도 <xref:System.Xml.XPath.XPathNavigator>는 변경되지 않습니다.  
  
 <xref:System.Xml.XPath.XPathNavigator>는 결과 트리 조각을 반복하는 데 사용되는 클래스입니다. 다음 코드 샘플에서는 XML을 포함하는 `fragment` 매개 변수로 함수를 호출하여 스타일시트 내부에서 결과 트리 조각을 만듭니다.  
  
## <a name="testxsl"></a>test.xsl  
  
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
  
## <a name="testxml"></a>test.xml  
  
```xml  
<root>Some text</root>  
```  
  
 다음 코드에서는 **test.xsl** 스타일시트와 **test.xml** 입력 데이터를 사용합니다.  
  
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
  
## <a name="output"></a>출력  
 변환 결과는 **out.xml** 파일에 표시됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a>참고 항목  
 [XslTransform 클래스의 XSLT 프로세서 구현](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
