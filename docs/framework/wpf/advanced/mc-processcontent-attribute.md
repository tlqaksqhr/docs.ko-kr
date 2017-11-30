---
title: "mc:ProcessContent 특성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf83fe66d5367d5e51428cb8f35aa88c12c9c39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="351fe-102">mc:ProcessContent 특성</span><span class="sxs-lookup"><span data-stu-id="351fe-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="351fe-103">지정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소 관련 부모 요소에 의해 처리 되는 콘텐츠 같아야 직계 부모 요소가 무시 되는 경우에 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지정한 이유로 프로세서 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="351fe-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="351fe-104">`mc:ProcessContent` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="351fe-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="351fe-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="351fe-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="351fe-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="351fe-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="351fe-107">*ignorablePrefix*</span></span>|<span data-ttu-id="351fe-108">XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="351fe-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="351fe-109">*ignorableUri*</span></span>|<span data-ttu-id="351fe-110">모든 유효한 URI XML 1.0 사양에 따라 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="351fe-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="351fe-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="351fe-112">무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="351fe-113">*[콘텐츠]*</span><span class="sxs-lookup"><span data-stu-id="351fe-113">*[content]*</span></span>|<span data-ttu-id="351fe-114">*ThisElementCanBeIgnored* 무시할 수 있는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="351fe-115">프로세서에서이 요소를 무시 하는 경우 *[콘텐츠]* 에서 처리 *개체*합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="351fe-116">설명</span><span class="sxs-lookup"><span data-stu-id="351fe-116">Remarks</span></span>  
 <span data-ttu-id="351fe-117">기본적으로는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 요소 내에서 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="351fe-118">특정 요소를 지정할 수 있습니다 `mc:ProcessContent`, 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 계속 무시 요소 내에서 콘텐츠 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="351fe-119">이 콘텐츠는 하나 이상와 무시할 수 있는 중 하나를 무시할 수 있는 여러 태그 안에 중첩 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="351fe-120">예를 들어 공백 구분 기호를 사용 하 여 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:ProcessContent="ignore:Element1 ignore:Element2"`합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="351fe-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와 특성의이 영역에 문서화 되지 않은 네임 스페이스를 정의 고 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="351fe-122">자세한 내용은 참조 [XML 태그 호환성 사양](http://go.microsoft.com/fwlink/?LinkId=73824)합니다.</span><span class="sxs-lookup"><span data-stu-id="351fe-122">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351fe-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="351fe-123">See Also</span></span>  
 [<span data-ttu-id="351fe-124">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="351fe-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="351fe-125">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="351fe-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
