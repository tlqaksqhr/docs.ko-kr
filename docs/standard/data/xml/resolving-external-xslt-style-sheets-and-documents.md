---
title: "외부 XSLT 스타일시트 및 문서 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5e84935f9fff1f993a677d408287cd775269f03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a><span data-ttu-id="341aa-102">외부 XSLT 스타일시트 및 문서 확인</span><span class="sxs-lookup"><span data-stu-id="341aa-102">Resolving External XSLT Style Sheets and Documents</span></span>
<span data-ttu-id="341aa-103">다음과 같이 변환 중에 외부 리소스를 확인해야 하는 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-103">There are several times during a transformation when you may need to resolve external resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="341aa-104"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="341aa-105"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 <span data-ttu-id="341aa-106">다음과 같이 변환 중에 외부 리소스를 확인해야 하는 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-106">There are several times during a transformation when you may need to resolve external resources:</span></span>  
  
-   <span data-ttu-id="341aa-107"><xref:System.Xml.Xsl.XslTransform.Load%2A> 중에 외부 스타일시트를 찾는 경우</span><span class="sxs-lookup"><span data-stu-id="341aa-107">During the <xref:System.Xml.Xsl.XslTransform.Load%2A> to locate an external style sheet.</span></span>  
  
-   <span data-ttu-id="341aa-108"><xref:System.Xml.Xsl.XslTransform.Load%2A> 중에 스타일시트에 있는 모든 `<xsl:include>` 또는 `<xsl:import>` 요소를 확인하는 경우</span><span class="sxs-lookup"><span data-stu-id="341aa-108">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to resolve any `<xsl:include>` or `<xsl:import>` elements found in the style sheet.</span></span>  
  
-   <span data-ttu-id="341aa-109"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 중에 `document()` 함수를 확인하는 경우</span><span class="sxs-lookup"><span data-stu-id="341aa-109">During <xref:System.Xml.Xsl.XslTransform.Transform%2A> to resolve any `document()` functions.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="341aa-110">XmlResolver 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="341aa-110">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="341aa-111">네트워크 리소스에 액세스하기 위해 인증이 필요한 경우 <xref:System.Xml.Xsl.XslTransform.Load%2A> 매개 변수를 사용하여 필요한 자격 증명 속성 집합을 갖는 <xref:System.Xml.XmlResolver> 개체를 전달할 수 있는 <xref:System.Xml.XmlResolver> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-111">If authentication is required to access a network resource, use the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that have an <xref:System.Xml.XmlResolver> parameter to pass the <xref:System.Xml.XmlResolver> object, which has the necessary credential properties set.</span></span>  
  
 <span data-ttu-id="341aa-112">다음 표에서는 사용하려는 사용자 지정 <xref:System.Xml.XmlResolver>가 있거나 다른 자격 증명을 지정해야 하는 경우 외부 리소스 확인이 필요한 시기에 따라 필요한 작업의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-112">If you have a custom <xref:System.Xml.XmlResolver> that you want to use, or if you need to specify different credentials, the following table lists the task required, depending on when the external resource needs resolution.</span></span>  
  
|<span data-ttu-id="341aa-113">확인이 필요한 프로세스</span><span class="sxs-lookup"><span data-stu-id="341aa-113">What process requires resolution</span></span>|<span data-ttu-id="341aa-114">필요한 작업</span><span class="sxs-lookup"><span data-stu-id="341aa-114">Task required</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="341aa-115"><xref:System.Xml.Xsl.XslTransform.Load%2A> 중에 스타일시트 찾기</span><span class="sxs-lookup"><span data-stu-id="341aa-115">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to locate the style sheet.</span></span>|<span data-ttu-id="341aa-116">스타일시트가 자격 증명을 요구하는 리소스에 있는 경우 <xref:System.Xml.Xsl.XslTransform.Load%2A>를 매개 변수로 사용하는 오버로드된 <xref:System.Xml.XmlResolver> 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-116">Specify the overloaded <xref:System.Xml.Xsl.XslTransform.Load%2A> method that takes, as a parameter, an <xref:System.Xml.XmlResolver> if the style sheet is on a resource that requires credentials.</span></span>|  
|<span data-ttu-id="341aa-117"><xref:System.Xml.Xsl.XslTransform.Load%2A> 중에 `<xsl:include>` 또는 `<xsl:import>` 확인</span><span class="sxs-lookup"><span data-stu-id="341aa-117">During <xref:System.Xml.Xsl.XslTransform.Load%2A> to resolve `<xsl:include>` or `<xsl:import>`.</span></span>|<span data-ttu-id="341aa-118">매개 변수로 <xref:System.Xml.Xsl.XslTransform.Load%2A>를 사용하는 오버로드된 <xref:System.Xml.XmlResolver> 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-118">Specify the overloaded <xref:System.Xml.Xsl.XslTransform.Load%2A> method that takes, as a parameter, an <xref:System.Xml.XmlResolver>.</span></span> <span data-ttu-id="341aa-119"><xref:System.Xml.XmlResolver>를 사용하여 `import` 또는 `include` 문에서 참조하는 스타일시트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-119">The <xref:System.Xml.XmlResolver> is used to load the style sheets referenced by the `import` or `include` statements.</span></span> <span data-ttu-id="341aa-120">`null`로 전달하는 경우에는 외부 리소스가 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-120">If you pass in `null`, the external resources are not resolved.</span></span>|  
|<span data-ttu-id="341aa-121">변환 중에 모든 `document()` 함수 확인</span><span class="sxs-lookup"><span data-stu-id="341aa-121">During a transformation to resolve any `document()` functions.</span></span>|<span data-ttu-id="341aa-122">지정 된 <xref:System.Xml.XmlResolver> 를 사용 하 여 변환 하는 동안는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 를 받는 메서드에 <xref:System.Xml.XmlResolver> 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-122">Specify the <xref:System.Xml.XmlResolver> during the transformation by using the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method that takes an <xref:System.Xml.XmlResolver> argument.</span></span>|  
  
 <span data-ttu-id="341aa-123">`document()` 함수 다른 XML 리소스도 검색 스타일 시트에서 또한 입력된 스트림에서 제공 하는 초기 XML 데이터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-123">The `document()` function retrieves other XML resources from a style sheet, in addition to the initial XML data provided by the input stream.</span></span> <span data-ttu-id="341aa-124">이 함수를 사용하면 어느 위치에 있는 XML 데이터도 포함시킬 수 있으므로 <xref:System.Xml.XmlResolver> 메서드에 `null` 값이 제공된 <xref:System.Xml.Xsl.XslTransform.Transform%2A>는 `document()` 함수가 실행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-124">Since this function allows the inclusion of XML data that can be located elsewhere, an <xref:System.Xml.XmlResolver> with a `null` value supplied to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method prevents the `document()` function from executing.</span></span> <span data-ttu-id="341aa-125">`document()` 함수를 사용하려면 적절한 권한을 설정하고 <xref:System.Xml.Xsl.XslTransform.Transform%2A>를 매개 변수로 사용하는 <xref:System.Xml.XmlResolver> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-125">If you want to use the `document()` function, use the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method that takes an <xref:System.Xml.XmlResolver> as a parameter, in addition to having the appropriate permission set.</span></span>  
  
 <span data-ttu-id="341aa-126"><xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드 및 이 메서드에서 <xref:System.Xml.XmlResolver>를 사용하는 방법에 대한 자세한 내용은 <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="341aa-126">For more information on the <xref:System.Xml.Xsl.XslTransform.Load%2A> method and its use of the <xref:System.Xml.XmlResolver>, see <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="341aa-127"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드가 호출되면 로드 시 제공된 증명 정보에 따라 권한이 판별되어 해당 권한 집합이 전체 변환 프로세스에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-127">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at load time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="341aa-128">`document()` 함수에서 해당 권한 집합에 없는 권한을 요구하는 작업을 시작하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="341aa-128">If the `document()` function attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341aa-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="341aa-129">See Also</span></span>  
 [<span data-ttu-id="341aa-130">XslTransform 클래스와 함께 XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="341aa-130">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="341aa-131">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="341aa-131">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="341aa-132">XslTransform 출력</span><span class="sxs-lookup"><span data-stu-id="341aa-132">Outputs from an XslTransform</span></span>](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)  
 [<span data-ttu-id="341aa-133">여러 저장소에서의 XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="341aa-133">XSLT Transformations Over Different Stores</span></span>](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)  
 [<span data-ttu-id="341aa-134">스타일 시트 매개 변수 및 확장명 개체의 XsltArgumentList</span><span class="sxs-lookup"><span data-stu-id="341aa-134">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)  
 [<span data-ttu-id="341aa-135">XSLT 스타일 시트 스크립트를 사용 하 여 \<msxsl: script ></span><span class="sxs-lookup"><span data-stu-id="341aa-135">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)  
 [<span data-ttu-id="341aa-136">Msxsl:node-set() 함수에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="341aa-136">Support for the msxsl:node-set() Function</span></span>](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)  
 [<span data-ttu-id="341aa-137">변형의 XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="341aa-137">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="341aa-138">변형의 XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="341aa-138">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="341aa-139">XslTransform에 대 한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="341aa-139">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="341aa-140">XslTransform에 대 한 XmlDataDocument 입력</span><span class="sxs-lookup"><span data-stu-id="341aa-140">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [<span data-ttu-id="341aa-141">XslTransform에 대 한 XmlDocument 입력</span><span class="sxs-lookup"><span data-stu-id="341aa-141">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
