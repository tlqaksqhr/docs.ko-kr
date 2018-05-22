---
title: XslTransform에 대한 XmlDocument 입력
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3179425597173e09a8c1ef1fbdfc582f8f4538e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="1d95e-102">XslTransform에 대한 XmlDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1d95e-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="1d95e-103"><xref:System.Xml.XmlDocument> 클래스는 XML 문서에 편집 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="1d95e-104"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드로 보내기 전에 XML을 편집 또는 수정해야 하는 경우 XML을 <xref:System.Xml.XmlDocument>에 로드하고 편집한 다음 <xref:System.Xml.Xsl.XslTransform>으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d95e-105"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="1d95e-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="1d95e-107">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d95e-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="1d95e-108"><xref:System.Xml.XmlDocument>는 <xref:System.Xml.XPath.IXPathNavigable> 인터페이스를 구현하므로 편집한 후 문서를 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="1d95e-109"><xref:System.Xml.XmlDocument>의 편집 기능 때문에 <xref:System.Xml.XmlDocument> 클래스를 변환의 입력으로 사용하면 XSLT(Extensible Stylesheet Language for Transformations) 변환에 <xref:System.Xml.XPath.XPathDocument>를 사용하는 것보다 성능이 떨어집니다. 이것은 <xref:System.Xml.XPath.XPathDocument>가 내부 저장소로 인해 XPath(XML Path Language) 쿼리에 최적화되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d95e-110">예</span><span class="sxs-lookup"><span data-stu-id="1d95e-110">Example</span></span>  
 <span data-ttu-id="1d95e-111">다음 코드 예제에서는 <xref:System.Xml.XmlDocument>를 <xref:System.Xml.Xsl.XslTransform>에 보내고 출력을 <xref:System.Xml.XmlReader>로 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d95e-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d95e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d95e-112">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 [<span data-ttu-id="1d95e-113">XslTransform 클래스를 사용하여 XSLT 변형</span><span class="sxs-lookup"><span data-stu-id="1d95e-113">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="1d95e-114">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="1d95e-114">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="1d95e-115">변형 과정에서 XPathNavigator의 역할</span><span class="sxs-lookup"><span data-stu-id="1d95e-115">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="1d95e-116">변형 과정에서 XPathNodeIterator의 역할</span><span class="sxs-lookup"><span data-stu-id="1d95e-116">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="1d95e-117">XslTransform에 대한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1d95e-117">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="1d95e-118">XslTransform에 대한 XmlDataDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1d95e-118">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
