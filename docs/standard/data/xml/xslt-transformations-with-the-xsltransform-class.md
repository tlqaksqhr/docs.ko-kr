---
title: XslTransform 클래스를 사용하여 XSLT 변형
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ece159b35cfbc83e05432b93ce7df06a5ca9fcac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576170"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="0c875-102">XslTransform 클래스를 사용하여 XSLT 변형</span><span class="sxs-lookup"><span data-stu-id="0c875-102">XSLT Transformations with the XslTransform Class</span></span>
> [!NOTE]
>  <span data-ttu-id="0c875-103"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="0c875-104"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="0c875-105">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c875-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="0c875-106">XSLT의 목표는 소스 XML 문서의 내용을 형식 또는 구조가 다른 문서로 변환하는 것입니다. 예를 들어, XML을 웹 사이트에서 사용하는 HTML로 변환하거나 응용 프로그램에서 필요한 필드만 포함하는 문서로 변형합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="0c875-107">이러한 변환 프로세스는 www.w3.org/TR/xslt에 있는 W3C(World Wide Web 컨소시엄) XSLT 버전 1.0 권장 사항으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-107">This transformation process is specified by the World Wide Web Consortium (W3C) XSLT version 1.0 recommendation located at www.w3.org/TR/xslt.</span></span> <span data-ttu-id="0c875-108">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 <xref:System.Xml.Xsl.XslTransform> 네임스페이스에 있는 <xref:System.Xml.Xsl> 클래스가 이 사양의 기능을 구현한 XSLT 프로세서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-108">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="0c875-109">여기에는 W3C XSLT 1.0 권장 사항에서 구현되지 않은 몇 가지 기능이 있습니다. 이 기능에 대해서는 [XslTransform 출력](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c875-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="0c875-110">다음 그림은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 변환 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-110">The following figure shows the transformation architecture of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="overview"></a><span data-ttu-id="0c875-111">개요</span><span class="sxs-lookup"><span data-stu-id="0c875-111">Overview</span></span>  
 <span data-ttu-id="0c875-112">![XSLT 변환 아키텍처](../../../../docs/standard/data/xml/media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span><span class="sxs-lookup"><span data-stu-id="0c875-112">![XSLT Transformation Architecture](../../../../docs/standard/data/xml/media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span></span>  
<span data-ttu-id="0c875-113">변형 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0c875-113">Transformation Architecture</span></span>  
  
 <span data-ttu-id="0c875-114">XSLT 권장 사항에서는 XML 문서의 일부를 선택하는 데 XPath(XML Path Language)를 사용합니다. 여기서 XPath는 문서 트리의 노드를 탐색하는 데 사용되는 쿼리 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-114">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="0c875-115">그림에서처럼 XPath의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 구현은 <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> 및 <xref:System.Xml.XPath.XPathDocument> 등과 같은 여러 클래스에 저장된 XML의 일부를 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-115">As shown in the diagram, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="0c875-116"><xref:System.Xml.XPath.XPathDocument>는 최적화된 XSLT 데이터 저장소로, <xref:System.Xml.Xsl.XslTransform>과 함께 사용할 경우 뛰어난 성능으로 XSLT 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-116">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>  
  
 <span data-ttu-id="0c875-117">다음 표에서는 <xref:System.Xml.Xsl.XslTransform> 및 XPath와 해당 기능을 사용할 때 자주 사용되는 클래스의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-117">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>  
  
|<span data-ttu-id="0c875-118">클래스 또는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c875-118">Class or Interface</span></span>|<span data-ttu-id="0c875-119">함수</span><span class="sxs-lookup"><span data-stu-id="0c875-119">Function</span></span>|  
|------------------------|--------------|  
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="0c875-120">XPath 쿼리 지원과 함께 저장소에 대한 커서 유형의 탐색 모델을 제공하는 API입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-120">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="0c875-121">내부 저장소에 대한 편집은 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-121">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="0c875-122">편집이 필요하면 <xref:System.Xml.XmlDocument> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-122">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|  
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="0c875-123">저장소에 대한 `CreateNavigator`에 <xref:System.Xml.XPath.XPathNavigator> 메서드를 제공하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-123">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|  
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="0c875-124">이 문서를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-124">It enables editing of this document.</span></span> <span data-ttu-id="0c875-125">XSLT 변환이 필요한 문서 편집 시나리오를 허용하여 <xref:System.Xml.XPath.IXPathNavigable>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-125">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="0c875-126">자세한 내용은 [XslTransform에 대한 XmlDocument 입력](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c875-126">For more information, see [XmlDocument Input to XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md).</span></span>|  
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="0c875-127"><xref:System.Xml.XmlDocument>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-127">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="0c875-128"><xref:System.Data.DataSet>에서 지정된 매핑에 따라 XML 문서 내의 구조화된 데이터 저장소를 최적화하는 <xref:System.Data.DataSet>을 사용하여 관계형 데이터와 XML 데이터를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-128">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0c875-129">데이터베이스에서 검색된 관계형 데이터에 대해 XSLT 변환이 수행될 수 있는 시나리오를 허용하여 <xref:System.Xml.XPath.IXPathNavigable>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-129">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="0c875-130">자세한 내용은 [XML과 관계형 데이터 및 ADO.NET의 통합](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c875-130">For more information, see [XML Integration with Relational Data and ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).</span></span>|  
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="0c875-131">이 클래스는 <xref:System.Xml.Xsl.XslTransform> 처리와 XPath 쿼리를 위해 최적화되었으며 고성능의 읽기 전용 캐시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-131">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="0c875-132"><xref:System.Xml.XPath.IXPathNavigable>을 구현하며 XSLT 변환에 사용하는 기본 설정 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-132">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="0c875-133">XPath 노드 집합을 탐색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-133">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="0c875-134"><xref:System.Xml.XPath.XPathNavigator>에서 모든 XPath 선택 메서드는 <xref:System.Xml.XPath.XPathNodeIterator>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-134">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="0c875-135">동일한 저장소에 대해 각각 선택된 노드 집합을 나타내는 여러 <xref:System.Xml.XPath.XPathNodeIterator> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-135">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|  
  
## <a name="msxml-xslt-extensions"></a><span data-ttu-id="0c875-136">MSXML XSLT 확장</span><span class="sxs-lookup"><span data-stu-id="0c875-136">MSXML XSLT Extensions</span></span>  
 <span data-ttu-id="0c875-137">`msxsl:script` 및 `msxsl:node-set` 함수는 <xref:System.Xml.Xsl.XslTransform> 클래스에서 지원하는 유일한 MSXML(Microsoft XML Core Services) XSLT 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-137">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c875-138">예</span><span class="sxs-lookup"><span data-stu-id="0c875-138">Example</span></span>  
 <span data-ttu-id="0c875-139">다음 코드 예제에서는 XSLT 스타일시트를 로드하고 <xref:System.Xml.XPath.XPathDocument>에 mydata.xml이라는 파일을 읽어들인 후, 가상 파일인 myStyleSheet.xsl에서 데이터 변환을 수행하여 서식이 지정된 출력을 콘솔로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c875-139">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
    Private filename As [String] = "mydata.xml"  
    Private stylesheet As [String] = "myStyleSheet.xsl"  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load(stylesheet)  
        Dim xpathdocument As New XPathDocument(filename)  
        Dim writer As New XmlTextWriter(Console.Out)  
        writer.Formatting = Formatting.Indented  
  
        xslt.Transform(xpathdocument, Nothing, writer, Nothing)  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample   
{  
    private const String filename = "mydata.xml";  
    private const String stylesheet = "myStyleSheet.xsl";  
  
    public static void Main()   
    {  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
    XPathDocument xpathdocument = new  
    XPathDocument(filename);  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting=Formatting.Indented;  
  
    xslt.Transform(xpathdocument, null, writer, null);      
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c875-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c875-140">See Also</span></span>  
 <xref:System.Xml.Xsl.XslTransform>  
 [<span data-ttu-id="0c875-141">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="0c875-141">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="0c875-142">XslTransform 클래스에서 임의 동작 구현</span><span class="sxs-lookup"><span data-stu-id="0c875-142">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](../../../../docs/standard/data/xml/implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)  
 [<span data-ttu-id="0c875-143">변형 과정에서 XPathNavigator의 역할</span><span class="sxs-lookup"><span data-stu-id="0c875-143">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="0c875-144">변형 과정에서 XPathNodeIterator의 역할</span><span class="sxs-lookup"><span data-stu-id="0c875-144">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="0c875-145">XslTransform에 대한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="0c875-145">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="0c875-146">XslTransform에 대한 XmlDataDocument 입력</span><span class="sxs-lookup"><span data-stu-id="0c875-146">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [<span data-ttu-id="0c875-147">XslTransform에 대한 XmlDocument 입력</span><span class="sxs-lookup"><span data-stu-id="0c875-147">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
