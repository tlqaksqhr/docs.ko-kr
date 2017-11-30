---
title: "XslTransform에 대한 XmlDocument 입력"
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
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 554faffb676337f8846eb6ba24152d77793b8fe0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="33f71-102">XslTransform에 대한 XmlDocument 입력</span><span class="sxs-lookup"><span data-stu-id="33f71-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="33f71-103"><xref:System.Xml.XmlDocument> 클래스는 XML 문서에 편집 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="33f71-104"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드로 보내기 전에 XML을 편집 또는 수정해야 하는 경우 XML을 <xref:System.Xml.XmlDocument>에 로드하고 편집한 다음 <xref:System.Xml.Xsl.XslTransform>으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33f71-105"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="33f71-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="33f71-107">참조 [XslCompiledTransform 클래스를 사용 하 여](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [마이그레이션 XslTransform 클래스에서](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="33f71-108"><xref:System.Xml.XmlDocument>는 <xref:System.Xml.XPath.IXPathNavigable> 인터페이스를 구현하므로 편집한 후 문서를 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="33f71-109"><xref:System.Xml.XmlDocument>의 편집 기능 때문에 <xref:System.Xml.XmlDocument> 클래스를 변환의 입력으로 사용하면 XSLT(Extensible Stylesheet Language for Transformations) 변환에 <xref:System.Xml.XPath.XPathDocument>를 사용하는 것보다 성능이 떨어집니다. 이것은 <xref:System.Xml.XPath.XPathDocument>가 내부 저장소로 인해 XPath(XML Path Language) 쿼리에 최적화되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33f71-110">예제</span><span class="sxs-lookup"><span data-stu-id="33f71-110">Example</span></span>  
 <span data-ttu-id="33f71-111">다음 코드 예제에서는 <xref:System.Xml.XmlDocument>를 <xref:System.Xml.Xsl.XslTransform>에 보내고 출력을 <xref:System.Xml.XmlReader>로 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33f71-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="33f71-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33f71-112">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 [<span data-ttu-id="33f71-113">XslTransform 클래스와 함께 XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="33f71-113">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="33f71-114">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="33f71-114">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="33f71-115">변형의 XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="33f71-115">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="33f71-116">변형의 XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="33f71-116">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="33f71-117">XslTransform에 대 한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="33f71-117">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="33f71-118">XslTransform에 대 한 XmlDataDocument 입력</span><span class="sxs-lookup"><span data-stu-id="33f71-118">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
