---
title: "XslCompiledTransform 클래스의 출력 옵션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61f59c1be3376fb76c91994996840b915cd662ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="output-options-on-the-xslcompiledtransform-class"></a><span data-ttu-id="6aa4e-102">XslCompiledTransform 클래스의 출력 옵션</span><span class="sxs-lookup"><span data-stu-id="6aa4e-102">Output Options on the XslCompiledTransform Class</span></span>
<span data-ttu-id="6aa4e-103">이 항목에서는 사용할 수 있는 XSLT 출력 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-103">This topic discusses the available XSLT output options.</span></span> <span data-ttu-id="6aa4e-104">스타일시트나 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에서 출력 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-104">You can specify output options in the style sheet, or on the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="xsloutput-element"></a><span data-ttu-id="6aa4e-105">xsl:output 요소</span><span class="sxs-lookup"><span data-stu-id="6aa4e-105">xsl:output Element</span></span>  
 <span data-ttu-id="6aa4e-106">`xsl:output` 요소는 출력 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-106">The `xsl:output` element specifies options for the output.</span></span> <span data-ttu-id="6aa4e-107"><xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드로 지정한 출력 형식에 의해 `xsl:output` 옵션의 동작이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-107">The output type specified by the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method determines the behavior of the `xsl:output` options.</span></span>  
  
 <span data-ttu-id="6aa4e-108">다음 표에서는 출력 형식이 스트림 또는 `xsl:output`인 경우 <xref:System.IO.TextWriter> 요소에서 사용할 수 있는 각 특성의 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-108">The following table describes the behavior for each of the attributes available on the `xsl:output` element when the output type is a stream or a <xref:System.IO.TextWriter>.</span></span>  
  
|<span data-ttu-id="6aa4e-109">특성 이름</span><span class="sxs-lookup"><span data-stu-id="6aa4e-109">Attribute name</span></span>|<span data-ttu-id="6aa4e-110">동작</span><span class="sxs-lookup"><span data-stu-id="6aa4e-110">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="6aa4e-111">메서드</span><span class="sxs-lookup"><span data-stu-id="6aa4e-111">method</span></span>|<span data-ttu-id="6aa4e-112">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-112">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-113">버전</span><span class="sxs-lookup"><span data-stu-id="6aa4e-113">version</span></span>|<span data-ttu-id="6aa4e-114">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-114">Ignored.</span></span> <span data-ttu-id="6aa4e-115">버전은 항상 XML의 경우 1.0이고 HTML의 경우 4.0입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-115">The version is always 1.0 for XML and 4.0 for HTML.</span></span>|  
|<span data-ttu-id="6aa4e-116">encoding</span><span class="sxs-lookup"><span data-stu-id="6aa4e-116">encoding</span></span>|<span data-ttu-id="6aa4e-117"><xref:System.IO.TextWriter>로 출력하는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-117">Ignored when outputting to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="6aa4e-118"><xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType> 속성이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-118">The <xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType> property is used instead.</span></span>|  
|<span data-ttu-id="6aa4e-119">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="6aa4e-119">omit-xml-declaration</span></span>|<span data-ttu-id="6aa4e-120">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-120">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-121">독립 실행형</span><span class="sxs-lookup"><span data-stu-id="6aa4e-121">standalone</span></span>|<span data-ttu-id="6aa4e-122">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-122">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-123">doctype-public</span><span class="sxs-lookup"><span data-stu-id="6aa4e-123">doctype-public</span></span>|<span data-ttu-id="6aa4e-124">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-124">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-125">doctype-system</span><span class="sxs-lookup"><span data-stu-id="6aa4e-125">doctype-system</span></span>|<span data-ttu-id="6aa4e-126">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-126">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-127">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="6aa4e-127">cdata-section-elements</span></span>|<span data-ttu-id="6aa4e-128">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-128">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-129">indent</span><span class="sxs-lookup"><span data-stu-id="6aa4e-129">indent</span></span>|<span data-ttu-id="6aa4e-130">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-130">Supported.</span></span>|  
|<span data-ttu-id="6aa4e-131">media-type</span><span class="sxs-lookup"><span data-stu-id="6aa4e-131">media-type</span></span>|<span data-ttu-id="6aa4e-132">지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-132">Supported.</span></span>|  
  
#### <a name="sending-output-to-an-xmlwriter"></a><span data-ttu-id="6aa4e-133">XmlWriter로 출력 보내기</span><span class="sxs-lookup"><span data-stu-id="6aa4e-133">Sending Output to an XmlWriter</span></span>  
 <span data-ttu-id="6aa4e-134">스타일시트에서 `xsl:output` 요소를 사용하며 출력 형식이 <xref:System.Xml.XmlWriter> 개체인 경우 <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> 개체를 만들 때 <xref:System.Xml.XmlWriter> 속성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-134">If your style sheet uses the `xsl:output` element and the output type is an <xref:System.Xml.XmlWriter> object, you should use the <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> property when you create the <xref:System.Xml.XmlWriter> object.</span></span> <span data-ttu-id="6aa4e-135"><xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> 속성은 컴파일된 스타일시트의 <xref:System.Xml.XmlWriterSettings> 요소에서 파생된 정보가 포함된 `xsl:output` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-135">The <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> property returns an <xref:System.Xml.XmlWriterSettings> object that contains information derived from the `xsl:output` element of a compiled style sheet.</span></span> <span data-ttu-id="6aa4e-136">이 <xref:System.Xml.XmlWriterSettings> 개체를 <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> 메서드에 전달하여 올바른 설정으로 <xref:System.Xml.XmlWriter> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-136">This <xref:System.Xml.XmlWriterSettings> object can be passed to the <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> method to create an <xref:System.Xml.XmlWriter> object with the correct settings.</span></span>  
  
## <a name="output-types"></a><span data-ttu-id="6aa4e-137">출력 형식</span><span class="sxs-lookup"><span data-stu-id="6aa4e-137">Output Types</span></span>  
 <span data-ttu-id="6aa4e-138">다음 목록에서는 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 명령에서 사용할 수 있는 출력 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-138">The following list describes the output types available on the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> command.</span></span>  
  
#### <a name="xmlwriter"></a><span data-ttu-id="6aa4e-139">XmlWriter</span><span class="sxs-lookup"><span data-stu-id="6aa4e-139">XmlWriter</span></span>  
 <span data-ttu-id="6aa4e-140"><xref:System.Xml.XmlWriter> 클래스는 XML 스키마 또는 파일을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-140">The <xref:System.Xml.XmlWriter> class writes out XML streams or files.</span></span> <span data-ttu-id="6aa4e-141"><xref:System.Xml.XmlWriter> 클래스를 사용하면 출력 옵션을 비롯하여 <xref:System.Xml.XmlWriterSettings> 개체에서 지원할 기능을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-141">You can specify the features to support on the <xref:System.Xml.XmlWriter> object, including output options, by using the <xref:System.Xml.XmlWriterSettings> class.</span></span> <span data-ttu-id="6aa4e-142"><xref:System.Xml.XmlWriter> 클래스는 <xref:System.Xml> 프레임워크의 필수 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-142">The <xref:System.Xml.XmlWriter> class is an integral part of the <xref:System.Xml> framework.</span></span> <span data-ttu-id="6aa4e-143">이 출력 형식을 사용하여 출력 결과를 다른 XML 프로세스에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-143">Use this output type to pipeline the output results into another XML process.</span></span>  
  
#### <a name="string"></a><span data-ttu-id="6aa4e-144">문자열</span><span class="sxs-lookup"><span data-stu-id="6aa4e-144">String</span></span>  
 <span data-ttu-id="6aa4e-145">이 출력 형식을 사용하여 출력 파일의 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-145">Use this output type to specify the URI of the output file.</span></span>  
  
#### <a name="stream"></a><span data-ttu-id="6aa4e-146">스트림</span><span class="sxs-lookup"><span data-stu-id="6aa4e-146">Stream</span></span>  
 <span data-ttu-id="6aa4e-147">스트림은 파일, 입력/출력 장치, 프로세스 간 통신 파이프 또는 TCP/IP 소켓과 같은 바이트 시퀀스를 추상적으로 나타낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-147">A stream is an abstraction of a sequence of bytes, such as a file, an input/output device, an inter-process communication pipe, or a TCP/IP socket.</span></span> <span data-ttu-id="6aa4e-148"><xref:System.IO.Stream> 클래스와 해당 파생 클래스는 이러한 여러 형식의 입력 및 출력의 일반 뷰를 제공하는데 이때 프로그래머는 운영 체제 및 기본 장치의 세부 정보에서 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-148">The <xref:System.IO.Stream> class and its derived classes provide a generic view of these different types of input and output, isolating the programmer from the specific details of the operating system and the underlying devices.</span></span>  
  
 <span data-ttu-id="6aa4e-149">이 출력 형식을 사용하여 데이터를 <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> 또는 출력 스트림(`Response.OutputStream`)으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-149">Use this output type to send data to a <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, or an output stream (`Response.OutputStream`).</span></span>  
  
#### <a name="textwriter"></a><span data-ttu-id="6aa4e-150">TextWriter</span><span class="sxs-lookup"><span data-stu-id="6aa4e-150">TextWriter</span></span>  
 <span data-ttu-id="6aa4e-151"><xref:System.IO.TextWriter>는 연속 문자를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-151">The <xref:System.IO.TextWriter> writes sequential characters.</span></span> <span data-ttu-id="6aa4e-152"><xref:System.IO.StringWriter> 및 <xref:System.IO.StreamWriter> 클래스에서 구현되며 이 클래스는 각각 문자열과 스트림에 문자를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-152">It is implemented in the <xref:System.IO.StringWriter> and <xref:System.IO.StreamWriter> classes, which write characters to strings or streams, respectively.</span></span> <span data-ttu-id="6aa4e-153">문자열로 출력하려면 이 출력 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-153">Use this output type when you want to output to a string.</span></span>  
  
## <a name="notes"></a><span data-ttu-id="6aa4e-154">참고</span><span class="sxs-lookup"><span data-stu-id="6aa4e-154">Notes</span></span>  
  
-   <span data-ttu-id="6aa4e-155">빈 태그를 쓰는 경우 `<myElement />`와 같이 요소 이름의 마지막 문자와 백슬래시 사이에 공백이 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-155">When writing out empty tags, a space is written between the last character of the element name and the backslash, `<myElement />` for example.</span></span> <span data-ttu-id="6aa4e-156">그러면 이전 브라우저에 생성된 HTML 페이지가 올바르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa4e-156">This lets older browsers display the generated HTML pages correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa4e-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6aa4e-157">See Also</span></span>  
 [<span data-ttu-id="6aa4e-158">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="6aa4e-158">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
