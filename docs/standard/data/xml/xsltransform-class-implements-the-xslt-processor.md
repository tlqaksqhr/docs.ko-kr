---
title: XslTransform 클래스의 XSLT 프로세서 구현
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fd0a72ab0274fe6ccc2016d90739a5fda876826
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579199"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a><span data-ttu-id="1c4af-102">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="1c4af-102">XslTransform Class Implements the XSLT Processor</span></span>
> [!NOTE]
>  <span data-ttu-id="1c4af-103"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="1c4af-104"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="1c4af-105">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c4af-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="1c4af-106"><xref:System.Xml.Xsl.XslTransform> 클래스는 XSLT(XSL Transformations) 버전 1.0 권장 사항을 구현한 XSLT 프로세서입니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-106">The <xref:System.Xml.Xsl.XslTransform> class is an XSLT processor implementing the XSL Transformations (XSLT) Version 1.0 recommendation.</span></span> <span data-ttu-id="1c4af-107"><xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드는 스타일시트를 찾아서 읽으며 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드는 지정된 소스 문서를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-107">The <xref:System.Xml.Xsl.XslTransform.Load%2A> method locates and reads style sheets, and the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method transforms the given source document.</span></span> <span data-ttu-id="1c4af-108"><xref:System.Xml.XPath.IXPathNavigable> 인터페이스를 구현하는 저장소를 <xref:System.Xml.Xsl.XslTransform>에 대한 소스 문서로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-108">Any store that implements the <xref:System.Xml.XPath.IXPathNavigable> interface can be used as the source document for the <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="1c4af-109">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]는 현재 <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlDocument> 및 <xref:System.Xml.XmlDataDocument>에 대해 <xref:System.Xml.XPath.XPathDocument> 인터페이스를 구현하므로 이 모든 개체를 변환에 사용할 입력 소스 문서로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-109">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] currently implements the <xref:System.Xml.XPath.IXPathNavigable> interface on the <xref:System.Xml.XmlDocument>, the <xref:System.Xml.XmlDataDocument>, and the <xref:System.Xml.XPath.XPathDocument>, so all of these can be used as the input source document to a transformation.</span></span>  
  
 <span data-ttu-id="1c4af-110"><xref:System.Xml.Xsl.XslTransform>에서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체는 다음 네임스페이스로 정의된 XSLT 1.0 사양만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-110">The <xref:System.Xml.Xsl.XslTransform> object in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] only supports the XSLT 1.0 specification, defined with the following namespace:</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">    
```  
  
 <span data-ttu-id="1c4af-111"><xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드를 사용하여 다음 클래스 중 하나에서 스타일시트를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-111">The style sheet can be loaded, using the <xref:System.Xml.Xsl.XslTransform.Load%2A> method, from one of the following classes:</span></span>  
  
-   <span data-ttu-id="1c4af-112">XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="1c4af-112">XPathNavigator</span></span>  
  
-   <span data-ttu-id="1c4af-113">XmlReader</span><span class="sxs-lookup"><span data-stu-id="1c4af-113">XmlReader</span></span>  
  
-   <span data-ttu-id="1c4af-114">URL을 나타내는 문자열</span><span class="sxs-lookup"><span data-stu-id="1c4af-114">A string representing a URL</span></span>  
  
 <span data-ttu-id="1c4af-115">위의 각 입력 클래스마다 서로 다른 <xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-115">There is a different <xref:System.Xml.Xsl.XslTransform.Load%2A> method for each of the above input classes.</span></span> <span data-ttu-id="1c4af-116">일부 메서드는 이러한 클래스 중 하나와 <xref:System.Xml.XmlResolver> 클래스를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-116">Some methods take in a combination of one of these classes and the <xref:System.Xml.XmlResolver> class as arguments.</span></span> <span data-ttu-id="1c4af-117"><xref:System.Xml.XmlResolver>는 스타일시트에 있는 `<xsl:import>` 또는 `<xsl:include>`가 참조하는 리소스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-117">The <xref:System.Xml.XmlResolver> locates resources referenced by `<xsl:import>` or `<xsl:include>` found in the style sheet.</span></span> <span data-ttu-id="1c4af-118">다음 메서드는 문자열 <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XPath.XPathNavigator>를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-118">The following methods take a string, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> as input.</span></span>  
  
```vb  
Overloads Public Sub Load(String)  
```  
  
```csharp  
public void Load(string);  
```  
  
```vb  
Overloads Public Sub Load(String, XmlResolver)  
```  
  
```csharp  
public void Load(string, XmlResolver);  
```  
  
```vb  
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)  
```  
  
```csharp  
public void Load(XmlReader, XmlResolver, Evidence);  
```  
  
```vb  
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)  
```  
  
```csharp  
public void Load(XPathNavigator, XmlResolver, Evidence);  
```  
  
 <span data-ttu-id="1c4af-119">위에 표시된 대부분의 <xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드는 <xref:System.Xml.XmlResolver>를 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-119">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods shown above take an <xref:System.Xml.XmlResolver> as a parameter.</span></span> <span data-ttu-id="1c4af-120"><xref:System.Xml.XmlResolver>를 사용하여 해당 스타일시트와 xsl:import 및 xsl:include 요소에 참조되는 다른 스타일시트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-120">The <xref:System.Xml.XmlResolver> is used to load the style sheet and any style sheet(s) referenced in xsl:import and xsl:include elements.</span></span>  
  
 <span data-ttu-id="1c4af-121">대부분의 <xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드는 증명 정보도 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-121">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods also take evidence as a parameter.</span></span> <span data-ttu-id="1c4af-122">증명 매개 변수는 스타일시트와 연관된 <xref:System.Security.Policy.Evidence>입니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-122">The evidence parameter is the <xref:System.Security.Policy.Evidence> that is associated with the style sheet.</span></span> <span data-ttu-id="1c4af-123">스타일시트의 보안 수준은 스타일시트에 포함된 스크립트, 스타일시트가 사용하는 `document()` 함수 및 <xref:System.Xml.Xsl.XsltArgumentList>가 사용하는 확장 개체 등 해당 스타일시트가 참조하는 모든 후속 리소스의 보안 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-123">The security level of the style sheet affects the security level of any subsequent resources it references, such as the script it contains, any `document()` functions it uses, and any extension objects used by the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
 <span data-ttu-id="1c4af-124">URL 매개 변수를 포함하지만 증명 매개 변수는 포함하지 않는 <xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드를 사용하여 스타일시트를 로드하는 경우 지정된 URL과 해당 사이트 및 영역을 조합해서 스타일시트의 증명 정보를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-124">If the style sheet is loaded using a <xref:System.Xml.Xsl.XslTransform.Load%2A> method that contains a URL parameter and no evidence is provided, the evidence of the style sheet is calculated by combining the given URL with its site and zone.</span></span>  
  
 <span data-ttu-id="1c4af-125">URI나 증명 정보가 모두 제공되지 않으면 스타일시트의 증명 정보 집합은 완전하게 신뢰됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-125">If no URI or evidence is provided, then the evidence set for the style sheet is fully trusted.</span></span> <span data-ttu-id="1c4af-126">신뢰되지 않는 소스에서 스타일시트를 로드하거나 신뢰되지 않는 확장 개체를 <xref:System.Xml.Xsl.XsltArgumentList>에 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1c4af-126">Do not load style sheets from untrusted sources, or add untrusted extension objects into the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
 <span data-ttu-id="1c4af-127">보안 수준 및 증명 정보와 증명 정보가 스크립트에 미치는 영향에 대한 자세한 내용은 [\<msxsl:script>를 사용한 XSLT 스타일시트 스크립트](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c4af-127">For more information about security levels and evidence and how it affects scripting, see [XSLT Stylesheet Scripting Using \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span></span> <span data-ttu-id="1c4af-128">보안 수준 및 증명 정보와 증명 정보가 확장 개체에 미치는 영향에 대한 자세한 내용은 [스타일시트 매개 변수 및 확장 개체의 XsltArgumentList](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c4af-128">For information about security levels and evidence and how it affects extension objects, see [XsltArgumentList for Style Sheet Parameters and Extension Objects](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span></span>  
  
 <span data-ttu-id="1c4af-129">보안 수준 및 증명 정보와 증명 정보가 `document()` 함수에 미치는 영향에 대한 자세한 내용은 [외부 XSLT 스타일시트 및 문서 확인](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c4af-129">For information about security levels and evidence and how it affects the `document()` function, see [Resolving External XSLT Style Sheets and Documents](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span></span>  
  
 <span data-ttu-id="1c4af-130">스타일시트에 많은 입력 매개 변수가 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-130">A style sheet can be supplied with a number of input parameters.</span></span> <span data-ttu-id="1c4af-131">또한 스타일시트는 확장 개체에 대해 함수를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-131">The style sheet can also call functions on extension objects.</span></span> <span data-ttu-id="1c4af-132">이러한 매개 변수와 확장 개체는 모두 <xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 스타일시트에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-132">Both parameters and extension objects are supplied to the style sheet using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="1c4af-133"><xref:System.Xml.Xsl.XsltArgumentList>에 대한 자세한 내용은 <xref:System.Xml.Xsl.XsltArgumentList>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c4af-133">For more information about the <xref:System.Xml.Xsl.XsltArgumentList>, see <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
## <a name="recommended-secure-use-of-xsltransform-class"></a><span data-ttu-id="1c4af-134">XslTransform 클래스의 권장되는 보안 사용</span><span class="sxs-lookup"><span data-stu-id="1c4af-134">Recommended Secure Use of XslTransform Class</span></span>  
 <span data-ttu-id="1c4af-135">스타일시트의 보안 권한은 제공되는 증명 정보에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-135">The security privileges of the style sheet depend on the evidence provided.</span></span> <span data-ttu-id="1c4af-136">다음 표에서는 스타일시트의 위치를 요약해서 설명하고 제공할 증명 정보 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-136">The following table summarizes the location of the style sheet and gives an explanation of what type of evidence to give.</span></span>  
  
-   <span data-ttu-id="1c4af-137">XSLT 스타일시트에 외부 참조가 없거나 스타일시트를 사용자가 신뢰하는 코드베이스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-137">The XSLT style sheet has no external references, or the style sheet comes from a code base that you trust.</span></span>  
  
    -   <span data-ttu-id="1c4af-138">어셈블리에서 증명 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-138">Provide the evidence from your assembly:</span></span>  
  
         `Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)`  
  
         `XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);`  
  
-   <span data-ttu-id="1c4af-139">XSLT 스타일시트를 외부 소스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-139">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="1c4af-140">소스의 출처를 알고 있으며 확인 가능한 URI가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-140">The origin of the source is known and there is a verifiable URI.</span></span>  
  
    -   <span data-ttu-id="1c4af-141">URI를 사용하여 증명 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-141">Create evidence using the URI.</span></span>  
  
         `Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)`  
  
         `XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);`  
  
-   <span data-ttu-id="1c4af-142">XSLT 스타일시트를 외부 소스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-142">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="1c4af-143">소스의 원본을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-143">The origin of the source is not known.</span></span>  
  
    -   <span data-ttu-id="1c4af-144">증명 정보를 `null`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-144">Set evidence to `null`.</span></span> <span data-ttu-id="1c4af-145">스크립트 블록이 처리되지 않고, XSLT `document()` 함수가 지원되지 않으며, 권한 있는 확장 개체는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-145">Script blocks are not processed, the XSLT `document()` function is not supported, and privileged extension objects are disallowed.</span></span>  
  
         <span data-ttu-id="1c4af-146">또한 `resolver` 매개 변수를 `null`로 설정할 수 있습니다. 이렇게 하면 `xsl:import` 및 `xsl:include` 요소가 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-146">Additionally, you can also set the `resolver` parameter to `null` This ensures that `xsl:import` and `xsl:include` elements are not processed.</span></span>  
  
-   <span data-ttu-id="1c4af-147">XSLT 스타일시트를 외부 소스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-147">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="1c4af-148">소스의 원본을 알 수 없지만 스크립트 지원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-148">The origin of the source is not known, but you require script support.</span></span>  
  
    -   <span data-ttu-id="1c4af-149">호출자의 증명 정보를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-149">Request evidence from the caller.</span></span>  
  
## <a name="transformation-of-xml-data"></a><span data-ttu-id="1c4af-150">XML 데이터의 변형</span><span class="sxs-lookup"><span data-stu-id="1c4af-150">Transformation of XML Data</span></span>  
 <span data-ttu-id="1c4af-151">스타일시트가 로드된 후에는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드 중 하나를 호출하고 입력 소스 문서를 제공하여 변환을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-151">Once a style sheet is loaded, the transformation starts by calling one of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> methods and supplying an input source document.</span></span> <span data-ttu-id="1c4af-152"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드는 다양한 변환 출력을 제공하도록 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-152">The <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is overloaded to provide different transformation outputs.</span></span> <span data-ttu-id="1c4af-153">변환의 출력 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-153">The transformation can result in the following output formats:</span></span>  
  
-   <xref:System.Xml.XmlReader>  
  
-   <xref:System.Xml.XmlWriter>  
  
-   <xref:System.IO.TextWriter>  
  
-   <xref:System.IO.Stream>  
  
-   <span data-ttu-id="1c4af-154">파일의 문자열 URL</span><span class="sxs-lookup"><span data-stu-id="1c4af-154">String URL of file</span></span>  
  
 <span data-ttu-id="1c4af-155">마지막 형식인 문자열 URL은 URL에 있는 입력 문서를 변환하여 출력 URL에 문서를 쓸 경우에 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-155">This last format, the string URL, provides for a commonly used scenario in transforming an input document located in a URL and writing the document to the output URL.</span></span> <span data-ttu-id="1c4af-156">이 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드는 파일에서 XML 문서를 로드하고 XSLT 변환을 수행하여 출력을 파일에 쓸 때 편리한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-156">This <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is a convenience method to load an XML document from a file, perform the XSLT transformation, and write the output to a file.</span></span> <span data-ttu-id="1c4af-157">이 메서드를 사용하면 입력 소스 문서를 만들고 로드한 다음 파일 스트림에 쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-157">This prevents you from having to create and load the input source document, and then write to a file stream.</span></span> <span data-ttu-id="1c4af-158">다음 코드 예제에서는 문자열 URL을 입력 및 출력으로 사용하는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-158">The following code sample shows this use of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method using the string URL as input and output:</span></span>  
  
```vb  
Dim xsltransform As XslTransform = New XslTransform()  
xsltransform.Load("favorite.xsl")  
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)  
```  
  
```csharp  
XslTransform xsltransform = new XslTransform();  
xsltransform.Load("favorite.xsl");  
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);  
```  
  
## <a name="transforming-a-section-of-an-xml-document"></a><span data-ttu-id="1c4af-159">XML 문서의 섹션 변형</span><span class="sxs-lookup"><span data-stu-id="1c4af-159">Transforming a Section of an XML Document</span></span>  
 <span data-ttu-id="1c4af-160">변형은 문서 전체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-160">Transformations apply to the document as a whole.</span></span> <span data-ttu-id="1c4af-161">즉, 문서 루트 노드 이외의 노드에 전달해도 변환 프로세스에서 로드된 문서의 모든 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-161">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="1c4af-162">결과 트리 조각을 변환하려면 결과 트리 조각만 들어 있는 <xref:System.Xml.XmlDocument>를 만든 후 해당 <xref:System.Xml.XmlDocument>를 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-162">To transform a result tree fragment, you must create an <xref:System.Xml.XmlDocument> containing just the result tree fragment and pass that <xref:System.Xml.XmlDocument> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="1c4af-163">다음 예제에서는 결과 트리 조각에 대해 변형을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-163">The following example performs a transformation on a result tree fragment.</span></span>  
  
```vb  
Dim xslt As New XslTransform()  
xslt.Load("print_root.xsl")  
Dim doc As New XmlDocument()  
doc.Load("library.xml")  
' Create a new document containing just the result tree fragment.  
Dim testNode As XmlNode = doc.DocumentElement.FirstChild  
Dim tmpDoc As New XmlDocument()  
tmpDoc.LoadXml(testNode.OuterXml)  
' Pass the document containing the result tree fragment   
' to the Transform method.  
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))  
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)  
```  
  
```csharp  
XslTransform xslt = new XslTransform();       
xslt.Load("print_root.xsl");  
XmlDocument doc = new XmlDocument();  
doc.Load("library.xml");  
// Create a new document containing just the result tree fragment.  
XmlNode testNode = doc.DocumentElement.FirstChild;   
XmlDocument tmpDoc = new XmlDocument();   
tmpDoc.LoadXml(testNode.OuterXml);  
// Pass the document containing the result tree fragment   
// to the Transform method.  
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");  
xslt.Transform(tmpDoc, null, Console.Out, null);  
```  
  
 <span data-ttu-id="1c4af-164">이 예제에서는 library.xml 및 print_root.xsl 파일을 입력으로 사용하고 콘솔에 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-164">The example uses the library.xml and print_root.xsl files as input and outputs the following to the console.</span></span>  
  
```  
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl   
Root node is book.  
```  
  
 <span data-ttu-id="1c4af-165">library.xml</span><span class="sxs-lookup"><span data-stu-id="1c4af-165">library.xml</span></span>  
  
```xml  
<library>  
  <book genre='novel' ISBN='1-861001-57-5'>  
     <title>Pride And Prejudice</title>  
  </book>  
  <book genre='novel' ISBN='1-81920-21-2'>  
     <title>Hook</title>  
  </book>  
</library>  
```  
  
 <span data-ttu-id="1c4af-166">print_root.xsl</span><span class="sxs-lookup"><span data-stu-id="1c4af-166">print_root.xsl</span></span>  
  
```xml  
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >  
  <output method="text" />   
  <template match="/">  
     Root node is  <value-of select="local-name(//*[position() = 1])" />   
  </template>  
</stylesheet>  
```  
  
## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a><span data-ttu-id="1c4af-167">.NET Framework 버전 1.0에서 .NET Framework 버전 1.1로 XSLT 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1c4af-167">Migration of XSLT from .NET Framework version 1.0 to .NET Framework version 1.1</span></span>  
 <span data-ttu-id="1c4af-168">다음 표에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메서드의 사용되지 않는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0 메서드와 새로운 <xref:System.Xml.Xsl.XslTransform.Load%2A> 버전 1.1 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-168">The following table shows the obsolete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0 methods and new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.1 methods for the <xref:System.Xml.Xsl.XslTransform.Load%2A> method.</span></span> <span data-ttu-id="1c4af-169">새로운 메서드를 사용하면 증명 정보를 지정하여 스타일시트의 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-169">The new methods enable you to limit the permissions of the style sheet by specifying evidence.</span></span>  
  
|<span data-ttu-id="1c4af-170">더 이상 사용되지 않는 .NET Framework 버전 1.0 Load 메서드</span><span class="sxs-lookup"><span data-stu-id="1c4af-170">Obsolete .NET Framework version 1.0 Load Methods</span></span>|<span data-ttu-id="1c4af-171">대체 .NET Framework 버전 1.1 Load 메서드</span><span class="sxs-lookup"><span data-stu-id="1c4af-171">Replacement .NET Framework version 1.1 Load Methods</span></span>|  
|------------------------------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="1c4af-172">Load(XPathNavigator input);</span><span class="sxs-lookup"><span data-stu-id="1c4af-172">Load(XPathNavigator input);</span></span><br /><br /> <span data-ttu-id="1c4af-173">Load(XPathNavigator input, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="1c4af-173">Load(XPathNavigator input, XmlResolver resolver);</span></span>|<span data-ttu-id="1c4af-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="1c4af-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
|<span data-ttu-id="1c4af-175">Load(IXPathNavigable stylesheet);</span><span class="sxs-lookup"><span data-stu-id="1c4af-175">Load(IXPathNavigable stylesheet);</span></span><br /><br /> <span data-ttu-id="1c4af-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="1c4af-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="1c4af-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="1c4af-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
|<span data-ttu-id="1c4af-178">Load(XmlReader stylesheet);</span><span class="sxs-lookup"><span data-stu-id="1c4af-178">Load(XmlReader stylesheet);</span></span><br /><br /> <span data-ttu-id="1c4af-179">Load(XmlReader stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="1c4af-179">Load(XmlReader stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="1c4af-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="1c4af-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
  
 <span data-ttu-id="1c4af-181">다음 표에서는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드의 사용되지 않는 메서드와 새로운 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-181">The following table shows the obsolete and new methods for the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="1c4af-182">새로운 메서드는 <xref:System.Xml.XmlResolver> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-182">The new methods take an <xref:System.Xml.XmlResolver> object.</span></span>  
  
|<span data-ttu-id="1c4af-183">더 이상 사용되지 않는 .NET Framework 버전 1.0 Transform 메서드</span><span class="sxs-lookup"><span data-stu-id="1c4af-183">Obsolete .NET Framework version 1.0 Transform Methods</span></span>|<span data-ttu-id="1c4af-184">대체 .NET Framework 버전 1.1 Transform 메서드</span><span class="sxs-lookup"><span data-stu-id="1c4af-184">Replacement .NET Framework version Transform 1.1 Methods</span></span>|  
|-----------------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="1c4af-185">XmlReader 변형(XPathNavigator input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="1c4af-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span></span>|<span data-ttu-id="1c4af-186">XmlReader 변형(XPathNavigator input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="1c4af-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span></span>|<span data-ttu-id="1c4af-188">XmlReader 변형(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-189">Void 변형(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="1c4af-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="1c4af-192">Void 변형(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="1c4af-194">Void 변형(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="1c4af-196">Void 변형(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="1c4af-198">Void 변형(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-199">Void 변형(IXPathNavigable input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="1c4af-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="1c4af-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="1c4af-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="1c4af-201">Void Transform(String input, String output);</span><span class="sxs-lookup"><span data-stu-id="1c4af-201">Void Transform(String input, String output);</span></span>|<span data-ttu-id="1c4af-202">Void Transform(String input, String output, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="1c4af-202">Void Transform(String input, String output, XmlResolver resolver);</span></span>|  
  
 <span data-ttu-id="1c4af-203"><xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> 속성은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-203">The <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> property is obsolete in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.1.</span></span> <span data-ttu-id="1c4af-204">대신 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 개체를 사용하는 새로운 <xref:System.Xml.XmlResolver> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4af-204">Instead, use the new <xref:System.Xml.Xsl.XslTransform.Transform%2A> overloads which take an <xref:System.Xml.XmlResolver> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4af-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c4af-205">See Also</span></span>  
 <xref:System.Xml.Xsl.XslTransform>  
 [<span data-ttu-id="1c4af-206">XslTransform 클래스를 사용하여 XSLT 변형</span><span class="sxs-lookup"><span data-stu-id="1c4af-206">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="1c4af-207">변형 과정에서 XPathNavigator의 역할</span><span class="sxs-lookup"><span data-stu-id="1c4af-207">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="1c4af-208">변형 과정에서 XPathNodeIterator의 역할</span><span class="sxs-lookup"><span data-stu-id="1c4af-208">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="1c4af-209">XslTransform에 대한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1c4af-209">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="1c4af-210">XslTransform에 대한 XmlDataDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1c4af-210">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [<span data-ttu-id="1c4af-211">XslTransform에 대한 XmlDocument 입력</span><span class="sxs-lookup"><span data-stu-id="1c4af-211">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
