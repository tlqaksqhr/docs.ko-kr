---
title: "XSLT 보안 고려 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fea695be-617c-4977-9567-140e820436fc
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 560a0866a526caf4c8fe129209d0077374306a9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-security-considerations"></a><span data-ttu-id="08696-102">XSLT 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="08696-102">XSLT Security Considerations</span></span>
<span data-ttu-id="08696-103">XSLT 언어에는 강력하며 유연성 있는 풍부한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-103">The XSLT language has a rich set of features that give you a great deal of power and flexibility.</span></span> <span data-ttu-id="08696-104">이러한 기능은 유용하지만 외부 소스에서 악용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-104">It includes many features that, while useful, could also be exploited by outside sources.</span></span> <span data-ttu-id="08696-105">XSLT를 안전하게 사용하려면 XSLT를 사용할 때 발생하는 보안 문제 유형을 이해하고 이러한 위험 요소를 완화하기 위한 기본적인 전략을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-105">In order to use XSLT safely, you must understand the types of security issues that arise when using XSLT, and the basic strategies that you can employ to mitigate these risks.</span></span>  
  
## <a name="xslt-extensions"></a><span data-ttu-id="08696-106">XSLT 확장</span><span class="sxs-lookup"><span data-stu-id="08696-106">XSLT Extensions</span></span>  
 <span data-ttu-id="08696-107">가장 많이 사용되는 두 가지 XSLT 확장은 스타일시트 스크립팅과 확장 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08696-107">Two popular XSLT extensions are style sheet scripting and extension objects.</span></span> <span data-ttu-id="08696-108">이러한 확장을 사용하면 XSLT 프로세서에서 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-108">These extensions allow the XSLT processor to execute code.</span></span>  
  
-   <span data-ttu-id="08696-109">확장 개체는 프로그래밍 기능을 XSLT(XSL Transformations)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-109">Extension objects add programming capabilities to XSL transformations.</span></span>  
  
-   <span data-ttu-id="08696-110">`msxsl:script` 확장 요소를 사용하여 스타일시트에 스크립트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-110">Scripts can be embedded in the style sheet using the `msxsl:script` extension element.</span></span>  
  
### <a name="extension-objects"></a><span data-ttu-id="08696-111">확장 개체</span><span class="sxs-lookup"><span data-stu-id="08696-111">Extension Objects</span></span>  
 <span data-ttu-id="08696-112"><xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 메서드를 사용하여 확장 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-112">Extension objects are added using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="08696-113">확장 개체를 지원하려면 FullTrust 권한 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-113">The FullTrust permission set is required to support extension objects.</span></span> <span data-ttu-id="08696-114">이 권한 집합은 확장 개체 코드를 실행할 때 권한 높이기가 일어나지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-114">This ensures that elevation of permissions does not happen when extension object code is executed.</span></span> <span data-ttu-id="08696-115">FullTrust 권한 없이 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 메서드를 호출하려고 시도하면 보안 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="08696-115">Attempting to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method without FullTrust permissions results in a security exception being thrown.</span></span>  
  
### <a name="style-sheet-scripts"></a><span data-ttu-id="08696-116">스타일시트 스크립트</span><span class="sxs-lookup"><span data-stu-id="08696-116">Style Sheet Scripts</span></span>  
 <span data-ttu-id="08696-117">`msxsl:script` 확장 요소를 사용하여 스타일시트에 스크립트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-117">Scripts can be embedded in a style sheet using the `msxsl:script` extension element.</span></span> <span data-ttu-id="08696-118">스크립트 지원은 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 선택적 기능으로 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-118">Script support is an optional feature on the <xref:System.Xml.Xsl.XslCompiledTransform> class that is disabled by default.</span></span> <span data-ttu-id="08696-119">스크립트를 활성화하려면 <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=nameWithType> 속성을 `true`로 설정하고 <xref:System.Xml.Xsl.XsltSettings> 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-119">Scripting can be enabled by setting the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=nameWithType> property to `true` and passing the <xref:System.Xml.Xsl.XsltSettings> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
#### <a name="guidelines"></a><span data-ttu-id="08696-120">지침</span><span class="sxs-lookup"><span data-stu-id="08696-120">Guidelines</span></span>  
 <span data-ttu-id="08696-121">신뢰할 수 있는 소스에서 스타일시트를 가져온 경우에만 스크립팅을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-121">Enable scripting only when the style sheet comes from a trusted source.</span></span> <span data-ttu-id="08696-122">스타일시트의 소스를 확인할 수 없는 경우 또는 신뢰할 수 있는 소스에서 스타일시트를 가져오지 않은 경우 XSLT 설정 인수에 대해 `null`을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-122">If you cannot verify the source of the style sheet, or if the style sheet does not come from a trusted source, pass in `null` for the XSLT settings argument.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="08696-123">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="08696-123">External Resources</span></span>  
 <span data-ttu-id="08696-124">XSLT 언어에는 프로세서가 URI 참조를 확인해야 하는 `xsl:import`, `xsl:include`, `document()` 함수 등의 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-124">The XSLT language has features such as `xsl:import`, `xsl:include`, or the `document()` function, where the processor needs to resolve URI references.</span></span> <span data-ttu-id="08696-125"><xref:System.Xml.XmlResolver> 클래스를 사용하여 외부 리소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-125">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="08696-126">다음 두 가지 경우에 외부 리소스를 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-126">External resources may need to be resolved in the following two cases:</span></span>  
  
-   <span data-ttu-id="08696-127">스타일시트를 컴파일할 때 <xref:System.Xml.XmlResolver> 및 `xsl:import` 확인에 `xsl:include`가 사용되는 경우</span><span class="sxs-lookup"><span data-stu-id="08696-127">When compiling a style sheet, the <xref:System.Xml.XmlResolver> is used for `xsl:import` and `xsl:include` resolution.</span></span>  
  
-   <span data-ttu-id="08696-128">변환을 실행할 때 <xref:System.Xml.XmlResolver>를 사용하여 `document()` 함수를 확인하는 경우</span><span class="sxs-lookup"><span data-stu-id="08696-128">When executing the transformation, the <xref:System.Xml.XmlResolver> is used to resolve the `document()` function.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08696-129">`document()` 클래스에서 <xref:System.Xml.Xsl.XslCompiledTransform> 함수는 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-129">The `document()` function is disabled by default on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="08696-130">이 기능을 활성화하려면 <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=nameWithType> 속성을 `true`로 설정하고 <xref:System.Xml.Xsl.XsltSettings> 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-130">This feature can be enabled by setting the <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=nameWithType> property to `true` and passing the <xref:System.Xml.Xsl.XsltSettings> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
 <span data-ttu-id="08696-131"><xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 및 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드는 각각 인수의 하나로 <xref:System.Xml.XmlResolver>를 사용하는 오버로드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-131">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods each include overloads that accept an <xref:System.Xml.XmlResolver> as one of its arguments.</span></span> <span data-ttu-id="08696-132"><xref:System.Xml.XmlResolver>가 지정되지 않을 경우 기본 <xref:System.Xml.XmlUrlResolver>가 자격 증명 없이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08696-132">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
#### <a name="guidelines"></a><span data-ttu-id="08696-133">지침</span><span class="sxs-lookup"><span data-stu-id="08696-133">Guidelines</span></span>  
 <span data-ttu-id="08696-134">신뢰할 수 있는 소스에서 스타일시트를 가져온 경우에만 `document()` 함수를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-134">Enable the `document()` function only when the style sheet comes from a trusted source.</span></span>  
  
 <span data-ttu-id="08696-135">다음 목록에서는 <xref:System.Xml.XmlResolver> 개체를 지정하려 할 수 있는 경우에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-135">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
-   <span data-ttu-id="08696-136">XSLT 처리에 인증을 요구하는 네트워크 리소스에 대한 액세스 권한이 필요할 경우 <xref:System.Xml.XmlResolver>를 필요한 자격 증명과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-136">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
-   <span data-ttu-id="08696-137">XSLT 처리가 액세스할 수 있는 리소스를 제한하려면 <xref:System.Xml.XmlSecureResolver>를 올바른 권한 집합으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-137">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="08696-138">사용자가 제어하지 않거나 신뢰할 수 없는 리소스를 열어야 하는 경우에는 <xref:System.Xml.XmlSecureResolver> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08696-138">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
-   <span data-ttu-id="08696-139">동작을 사용자 지정하기 위해 사용자의 고유한 <xref:System.Xml.XmlResolver> 클래스를 구현하고 사용하여 리소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-139">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
-   <span data-ttu-id="08696-140">외부 리소스에 액세스하지 않도록 하려면 `null` 인수에 대해 <xref:System.Xml.XmlResolver>을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08696-140">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08696-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08696-141">See Also</span></span>  
 [<span data-ttu-id="08696-142">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="08696-142">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="08696-143">XSLT 처리 중 외부 리소스 확인</span><span class="sxs-lookup"><span data-stu-id="08696-143">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 [<span data-ttu-id="08696-144">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="08696-144">Code Access Security</span></span>](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)
