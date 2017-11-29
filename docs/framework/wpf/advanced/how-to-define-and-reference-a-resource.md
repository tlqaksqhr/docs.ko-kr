---
title: "방법: 리소스 정의 및 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 322ac3e5ebfe2d820a4711d877396b9a1a2759a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="7c215-102">방법: 리소스 정의 및 참조</span><span class="sxs-lookup"><span data-stu-id="7c215-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="7c215-103">이 예제에서는 리소스를 정의 하 고 특성을 사용 하 여 참조 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c215-104">예제</span><span class="sxs-lookup"><span data-stu-id="7c215-104">Example</span></span>  
 <span data-ttu-id="7c215-105">다음 예제에서는 두 가지 유형의 리소스를 정의:는 <xref:System.Windows.Media.SolidColorBrush> 리소스 및 여러 <xref:System.Windows.Style> 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="7c215-106"><xref:System.Windows.Media.SolidColorBrush> 리소스 `MyBrush` 각각 사용 하는 몇 가지 속성의 값을 제공 하는 데 사용 되는 <xref:System.Windows.Media.Brush> 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="7c215-107"><xref:System.Windows.Style> 리소스 `PageBackground`, `TitleText` 및 `Label` 각각 특정 컨트롤 형식의 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="7c215-108">해당 스타일 리소스 리소스 키에서 참조 하 고 설정 하는 데 사용 되는 스타일은 대상된 컨트롤에서 다양 한 속성을 설정는 <xref:System.Windows.FrameworkElement.Style%2A> 속성으로 정의 된 몇 가지 특정 컨트롤 요소의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="7c215-109">setter에 메모 속성 중 하나는 `Label` 스타일도 참조는 `MyBrush` 앞에서 정의한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="7c215-110">이 일반적인 방법 이지만 중요 리소스 구문 분석 되 고 제공 된 순서 대로 리소스 사전에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="7c215-111">리소스 사용 하는 경우 사전 내에서 발견 되는 순서로 요청도 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 다른 리소스 내에서 참조 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="7c215-112">여기서 해당 리소스가 요청 보다 리소스 컬렉션 내에서 참조 하는 모든 리소스 이전 정의 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="7c215-113">경우 필요에 따라 해결할 수 있습니다 리소스 참조의 엄격한 생성 순서를 사용 하 여 한 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 를 런타임 시 리소스를 대신 참조 알고 있어야 하지만 하는이 DynamicResource 기술 성능 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="7c215-114">자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c215-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="7c215-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c215-115">See Also</span></span>  
 [<span data-ttu-id="7c215-116">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="7c215-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="7c215-117">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7c215-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
