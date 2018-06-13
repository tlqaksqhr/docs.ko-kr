---
title: XslCompiledTransform 클래스 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b242556e6fb05cae5ff5f54d1b134e1db918e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571048"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="051ff-102">XslCompiledTransform 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="051ff-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="051ff-103"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 Microsoft .NET Framework XSLT 프로세서입니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="051ff-104">이 클래스를 사용하여 스타일시트를 컴파일하고 XSLT 변환을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="051ff-105"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 전체적인 성능이 <xref:System.Xml.Xsl.XslTransform> 클래스보다 좋지만 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslCompiledTransform> 메서드는 변환에 대해 처음 호출될 때 <xref:System.Xml.Xsl.XslTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslTransform> 메서드보다 느리게 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="051ff-106">이는 XSLT 파일이 로드되기 전에 컴파일되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="051ff-107">자세한 내용은 [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)(XslCompiledTransform이 XslTransform보다 느린가?)라는 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="051ff-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="051ff-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="051ff-108">In This Section</span></span>  
 [<span data-ttu-id="051ff-109">XslCompiledTransform 클래스에 대한 입력</span><span class="sxs-lookup"><span data-stu-id="051ff-109">Inputs to the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="051ff-110">사용할 수 있는 XSLT 입력 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="051ff-111">XslCompiledTransform 클래스의 출력 옵션</span><span class="sxs-lookup"><span data-stu-id="051ff-111">Output Options on the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="051ff-112">사용할 수 있는 XSLT 출력 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="051ff-113">XSLT 처리 중 외부 리소스 확인</span><span class="sxs-lookup"><span data-stu-id="051ff-113">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="051ff-114"><xref:System.Xml.XmlResolver> 클래스를 사용하여 외부 리소스를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="051ff-115">XSLT 스타일시트 확장</span><span class="sxs-lookup"><span data-stu-id="051ff-115">Extending XSLT Style Sheets</span></span>](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 <span data-ttu-id="051ff-116">XSLT 확장을 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="051ff-117">복구할 수 있는 XSLT 오류</span><span class="sxs-lookup"><span data-stu-id="051ff-117">Recoverable XSLT Errors</span></span>](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|<span data-ttu-id="051ff-118">W3C(World Wide Web 컨소시엄) XSLT 1.0 권장 사항에서 허용하는 임의 동작 및 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 임의 동작을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="051ff-119">방법: 노드 조각 변형</span><span class="sxs-lookup"><span data-stu-id="051ff-119">How to: Transform a Node Fragment</span></span>](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|<span data-ttu-id="051ff-120">노드 조각을 변형하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="051ff-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="051ff-121">Related Sections</span></span>  
 [<span data-ttu-id="051ff-122">XslTransform 클래스에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="051ff-122">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="051ff-123"><xref:System.Xml.Xsl.XslTransform> 클래스에서 코드를 마이그레이션하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="051ff-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051ff-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="051ff-124">See Also</span></span>  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
