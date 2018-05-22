---
title: XslTransform 출력
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd22d59375a46c267c6df70727d9ca52e6843214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="d18aa-102">XslTransform 출력</span><span class="sxs-lookup"><span data-stu-id="d18aa-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="d18aa-103">스타일시트는 `<xsl:output>` 특성과 `method` 문을 함께 사용하여 출력 형식을 결정할 수 있기 때문에 다음 표에서는 출력을 쓸 때 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드를 사용하고 출력 형식이 <xref:System.IO.Stream>이나 <xref:System.IO.TextWriter>로 선언된 경우의 출력 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d18aa-104"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="d18aa-105"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="d18aa-106">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d18aa-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="d18aa-107">스타일시트는 `<xsl:output>` 특성과 `method` 문을 함께 사용하여 출력 형식을 결정할 수 있기 때문에 다음 표에서는 출력을 쓸 때 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드를 사용하고 출력 형식이 <xref:System.IO.Stream>이나 <xref:System.IO.TextWriter>로 선언된 경우의 출력 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="d18aa-108">다음 표에서는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드와 `<xsl:output>` 문을 함께 사용하여 출력 형식이 선언된 경우의 결과를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="d18aa-109">\<xsl:output method = > attribute</span><span class="sxs-lookup"><span data-stu-id="d18aa-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="d18aa-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="d18aa-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="d18aa-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="d18aa-111">method="xml"</span></span>|<span data-ttu-id="d18aa-112">XML</span><span class="sxs-lookup"><span data-stu-id="d18aa-112">XML</span></span>|  
|<span data-ttu-id="d18aa-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="d18aa-113">method="html"</span></span>|<span data-ttu-id="d18aa-114">HTML</span><span class="sxs-lookup"><span data-stu-id="d18aa-114">HTML</span></span>|  
|<span data-ttu-id="d18aa-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="d18aa-115">method="text"</span></span>|<span data-ttu-id="d18aa-116">텍스트</span><span class="sxs-lookup"><span data-stu-id="d18aa-116">Text</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d18aa-117">참고: `<xsl:output>` 메서드의 출력이 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 또는 <xref:System.Xml.XmlReader>이면 <xref:System.Xml.XmlWriter> 문은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="d18aa-118">다음 특성은 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드 출력이 <xref:System.IO.Stream> 또는 <xref:System.IO.TextWriter>인 경우에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
-   <span data-ttu-id="d18aa-119">encoding\*</span><span class="sxs-lookup"><span data-stu-id="d18aa-119">encoding\*</span></span>  
  
-   <span data-ttu-id="d18aa-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="d18aa-120">omit-xml-declaration</span></span>  
  
-   <span data-ttu-id="d18aa-121">독립 실행형</span><span class="sxs-lookup"><span data-stu-id="d18aa-121">standalone</span></span>  
  
-   <span data-ttu-id="d18aa-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="d18aa-122">doctype-public</span></span>  
  
-   <span data-ttu-id="d18aa-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="d18aa-123">doctype-system</span></span>  
  
-   <span data-ttu-id="d18aa-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="d18aa-124">cdata-section-elements</span></span>  
  
-   <span data-ttu-id="d18aa-125">indent</span><span class="sxs-lookup"><span data-stu-id="d18aa-125">indent</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d18aa-126">\*<xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에서 <xref:System.IO.TextWriter>에 해당 출력을 보내는 동안에는 인코딩 특성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-126">\*the encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="d18aa-127">대신 <xref:System.IO.TextWriter>의 인코딩 속성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span>  
  
 <span data-ttu-id="d18aa-128">다음 특성은 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드 출력이 <xref:System.IO.Stream>인 경우에 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
-   <span data-ttu-id="d18aa-129">version: 항상 1.0</span><span class="sxs-lookup"><span data-stu-id="d18aa-129">version: the version is always 1.0</span></span>  
  
-   <span data-ttu-id="d18aa-130">media-type: 미디어 형식</span><span class="sxs-lookup"><span data-stu-id="d18aa-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="d18aa-131">특수 문자 이스케이프</span><span class="sxs-lookup"><span data-stu-id="d18aa-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="d18aa-132">`<xsl:text disable-output-escaping>` 태그는 특수 문자를 XML 형식으로 이스케이프해야 하는지(예: `<&lt>` 기호 대신 `"<"` 사용), 현재 상태로 유지해야 하는지 여부를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="d18aa-133">`disable-output-escaping` 특성은 <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XmlWriter> 개체로 변환될 때 무시되며 특수 문자에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d18aa-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18aa-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d18aa-134">See Also</span></span>  
 [<span data-ttu-id="d18aa-135">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="d18aa-135">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
