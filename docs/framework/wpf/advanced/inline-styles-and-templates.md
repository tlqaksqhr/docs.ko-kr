---
title: "인라인 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2acb455db8f8bdc5a95bfd2462b651cebbb692c3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="e4fec-102">인라인 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e4fec-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="e4fec-103">제공 <xref:System.Windows.Style> 개체 및 템플릿 개체 (<xref:System.Windows.FrameworkTemplate> 하위 클래스) 리소스에서 요소의 시각적 모양을 정의 하는 방법,으로 사용할 수 있도록 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="e4fec-104">이러한 이유로 특성 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 형식을 사용 하 <xref:System.Windows.Style> 및 <xref:System.Windows.FrameworkTemplate> 거의 항상 기존 스타일 및 서식 파일에 리소스를 참조 하지 않고 인라인 새 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="e4fec-105">인라인 스타일 및 서식 파일의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e4fec-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="e4fec-106">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 스타일 및 템플릿 속성 두 가지 방법 중 하나에 기술적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="e4fec-107">특성 구문을 사용 하 여 리소스에 내에서 정의 된 스타일을 참조할 `<` *개체*`Style="{StaticResource`*myResourceKey*`}" .../>`합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="e4fec-108">또는 예를 들어 인라인 스타일을 정의 하 속성 요소 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="e4fec-109">`<`*개체*`>`</span><span class="sxs-lookup"><span data-stu-id="e4fec-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="e4fec-110">`<`*개체*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="e4fec-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="e4fec-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="e4fec-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="e4fec-112">`</`*개체*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="e4fec-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="e4fec-113">`</`*개체*`>`</span><span class="sxs-lookup"><span data-stu-id="e4fec-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="e4fec-114">특성 사용이 훨씬 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-114">The attribute usage is much more common.</span></span> <span data-ttu-id="e4fec-115">인라인으로 정의 및에서는 정의 되지 않은 리소스는 스타일을 포함 하는 요소 에서만, 범위가 지정 이며 사용할 수 없습니다 다시 쉽게 키가 없거나 리소스 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="e4fec-116">일반적 리소스 정의 된 스타일을 유용 하 게 이며 더 일반적인 부합 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 모델 디자인 태그에서 코드의 프로그램 논리를 분리 하는 원칙을 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="e4fec-117">일반적으로 해당 위치에 해당 스타일이 나 템플릿을 사용 하려는 경우에 스타일이 나 템플릿을 인라인으로 설정할 필요가 없습니다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="e4fec-118">스타일이 나 템플릿을 사용할 수 있는 대부분의 요소는 콘텐츠 속성 및 콘텐츠 모델에도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="e4fec-119">어떤 논리적 트리만 사용 하는 경우 스타일이 나 템플릿을 통해 한 번 만들기는 것이 훨씬 쉽고만 직접 태그에 해당 하는 자식 요소와 해당 콘텐츠 속성을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="e4fec-120">이 스타일 및 템플릿 메커니즘은 완전히 바이패스 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="e4fec-121">개체를 반환 하는 태그 확장으로 사용 하도록 설정 하는 다른 구문 스타일 및 서식 파일을 위해 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="e4fec-122">이러한 두 개의 확장 가능한 시나리오에 포함 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 및 <xref:System.Windows.Data.Binding>합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fec-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fec-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4fec-123">See Also</span></span>  
 [<span data-ttu-id="e4fec-124">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e4fec-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
