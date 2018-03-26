---
title: XslTransform 출력
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 647f3829f4b26791c063d5646669b2fcb7ab6684
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="f19a6-102">XslTransform 출력</span><span class="sxs-lookup"><span data-stu-id="f19a6-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="f19a6-103">스타일시트는 `<xsl:output>` 특성과 `method` 문을 함께 사용하여 출력 형식을 결정할 수 있기 때문에 다음 표에서는 출력을 쓸 때 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드를 사용하고 출력 형식이 <xref:System.IO.Stream>이나 <xref:System.IO.TextWriter>로 선언된 경우의 출력 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19a6-104"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="f19a6-105"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="f19a6-106">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f19a6-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="f19a6-107">스타일시트는 `<xsl:output>` 특성과 `method` 문을 함께 사용하여 출력 형식을 결정할 수 있기 때문에 다음 표에서는 출력을 쓸 때 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드를 사용하고 출력 형식이 <xref:System.IO.Stream>이나 <xref:System.IO.TextWriter>로 선언된 경우의 출력 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="f19a6-108">다음 표에서는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드와 `<xsl:output>` 문을 함께 사용하여 출력 형식이 선언된 경우의 결과를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="f19a6-109">\<xsl:output method = > attribute</span><span class="sxs-lookup"><span data-stu-id="f19a6-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="f19a6-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="f19a6-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="f19a6-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="f19a6-111">method="xml"</span></span>|<span data-ttu-id="f19a6-112">XML</span><span class="sxs-lookup"><span data-stu-id="f19a6-112">XML</span></span>|  
|<span data-ttu-id="f19a6-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="f19a6-113">method="html"</span></span>|<span data-ttu-id="f19a6-114">HTML</span><span class="sxs-lookup"><span data-stu-id="f19a6-114">HTML</span></span>|  
|<span data-ttu-id="f19a6-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="f19a6-115">method="text"</span></span>|<span data-ttu-id="f19a6-116">Text</span><span class="sxs-lookup"><span data-stu-id="f19a6-116">Text</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f19a6-117">참고: `<xsl:output>` 메서드의 출력이 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 또는 <xref:System.Xml.XmlReader>이면 <xref:System.Xml.XmlWriter> 문은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="f19a6-118">다음 특성은 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드 출력이 <xref:System.IO.Stream> 또는 <xref:System.IO.TextWriter>인 경우에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
-   <span data-ttu-id="f19a6-119">encoding\*</span><span class="sxs-lookup"><span data-stu-id="f19a6-119">encoding\*</span></span>  
  
-   <span data-ttu-id="f19a6-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="f19a6-120">omit-xml-declaration</span></span>  
  
-   <span data-ttu-id="f19a6-121">독립 실행형</span><span class="sxs-lookup"><span data-stu-id="f19a6-121">standalone</span></span>  
  
-   <span data-ttu-id="f19a6-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="f19a6-122">doctype-public</span></span>  
  
-   <span data-ttu-id="f19a6-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="f19a6-123">doctype-system</span></span>  
  
-   <span data-ttu-id="f19a6-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="f19a6-124">cdata-section-elements</span></span>  
  
-   <span data-ttu-id="f19a6-125">indent</span><span class="sxs-lookup"><span data-stu-id="f19a6-125">indent</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f19a6-126">\*<xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에서 <xref:System.IO.TextWriter>에 해당 출력을 보내는 동안에는 인코딩 특성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-126">\*the encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="f19a6-127">대신 <xref:System.IO.TextWriter>의 인코딩 속성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span>  
  
 <span data-ttu-id="f19a6-128">다음 특성은 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드 출력이 <xref:System.IO.Stream>인 경우에 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
-   <span data-ttu-id="f19a6-129">version: 항상 1.0</span><span class="sxs-lookup"><span data-stu-id="f19a6-129">version: the version is always 1.0</span></span>  
  
-   <span data-ttu-id="f19a6-130">media-type: 미디어 형식</span><span class="sxs-lookup"><span data-stu-id="f19a6-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="f19a6-131">특수 문자 이스케이프</span><span class="sxs-lookup"><span data-stu-id="f19a6-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="f19a6-132">`<xsl:text disable-output-escaping>` 태그는 특수 문자를 XML 형식으로 이스케이프해야 하는지(예: `<&lt>` 기호 대신 `"<"` 사용), 현재 상태로 유지해야 하는지 여부를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="f19a6-133">`disable-output-escaping` 특성은 <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XmlWriter> 개체로 변환될 때 무시되며 특수 문자에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f19a6-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19a6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f19a6-134">See Also</span></span>  
 [<span data-ttu-id="f19a6-135">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="f19a6-135">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
