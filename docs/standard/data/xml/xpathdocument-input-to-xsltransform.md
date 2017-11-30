---
title: "XslTransform에 대한 XPathDocument 입력"
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
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 80708dfa60636bbb038c3a86e336709339d2ac55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="c0ba5-102">XslTransform에 대한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="c0ba5-102">XPathDocument Input to XslTransform</span></span>
<span data-ttu-id="c0ba5-103"><xref:System.Xml.XPath.XPathDocument>는 <xref:System.Xml.Xsl.XslTransform>을 사용하여 문서를 처리하기 위한 읽기 전용 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="c0ba5-104">이 캐시는 XML DOM(문서 개체 모델)과 구조상 유사하지만 <xref:System.Xml.XPath.XPathNavigator>의 XPath 최적화 함수를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 처리와 XPath(XML Path Language) 데이터 모델에 대해 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ba5-105"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="c0ba5-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="c0ba5-107">참조 [XslCompiledTransform 클래스를 사용 하 여](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [마이그레이션 XslTransform 클래스에서](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="c0ba5-108">다음 코드 샘플에서는 변환에 대한 입력으로 <xref:System.Xml.XPath.XPathDocument>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0ba5-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0ba5-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0ba5-109">See Also</span></span>  
 [<span data-ttu-id="c0ba5-110">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="c0ba5-110">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
