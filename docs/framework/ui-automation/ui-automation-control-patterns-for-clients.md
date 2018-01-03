---
title: "클라이언트용 UI 자동화 컨트롤 패턴"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
caps.latest.revision: "24"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 45eca9205e56d1245720425c36c6adfacae720a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-control-patterns-for-clients"></a><span data-ttu-id="6f627-102">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="6f627-102">UI Automation Control Patterns for Clients</span></span>
> [!NOTE]
>  <span data-ttu-id="6f627-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6f627-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f627-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6f627-105">이 개요에서는 UI 자동화 클라이언트에 대한 컨트롤 패턴을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-105">This overview introduces control patterns for UI Automation clients.</span></span> <span data-ttu-id="6f627-106">UI 자동화 클라이언트에서 컨트롤 패턴을 사용하여 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]에 대한 정보에 액세스하는 방법도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-106">It includes information on how a UI Automation client can use control patterns to access information about the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="6f627-107">컨트롤 패턴은 컨트롤 형식 및 컨트롤의 모양에 관계없이 컨트롤의 기능을 분류하고 노출하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-107">Control patterns provide a way to categorize and expose a control's functionality independent of the control type or the appearance of the control.</span></span> <span data-ttu-id="6f627-108">UI 자동화 클라이언트는 <xref:System.Windows.Automation.AutomationElement> 를 검사하여 지원되는 컨트롤 패턴을 확인하고 컨트롤의 동작을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-108">UI Automation clients can examine an <xref:System.Windows.Automation.AutomationElement> to determine which control patterns are supported and be assured of the behavior of the control.</span></span>  
  
 <span data-ttu-id="6f627-109">컨트롤 패턴의 전체 목록은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f627-109">For a complete list of control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a><span data-ttu-id="6f627-110">컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="6f627-110">Getting Control Patterns</span></span>  
 <span data-ttu-id="6f627-111">클라이언트는 <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>을 호출하여 <xref:System.Windows.Automation.AutomationElement>에서 컨트롤 패턴을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-111">Clients retrieve a control pattern from an <xref:System.Windows.Automation.AutomationElement> by calling either <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> or <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="6f627-112">클라이언트는 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> 메서드 또는 개별 `IsPatternAvailable` 속성(예: <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>)을 사용하여 패턴이나 패턴 그룹이 <xref:System.Windows.Automation.AutomationElement>에서 지원되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-112">Clients can use the <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> method or an individual `IsPatternAvailable` property (for example, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) to determine if a pattern or group of patterns is supported on the <xref:System.Windows.Automation.AutomationElement>.</span></span> <span data-ttu-id="6f627-113">그러나 컨트롤 패턴을 가져오고 `null` 참조를 테스트하면 프로세스 간 호출을 줄일 수 있으므로 지원되는 속성을 확인하고 컨트롤 패턴을 검색하는 것보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-113">However, it is more efficient to attempt to get the control pattern and test for a `null` reference than to check the supported properties and retrieve the control pattern since it results in fewer cross-process calls.</span></span>  
  
 <span data-ttu-id="6f627-114">다음 예제에서는 <xref:System.Windows.Automation.TextPattern> 에서 <xref:System.Windows.Automation.AutomationElement>컨트롤 패턴을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-114">The following example demonstrates how to get a <xref:System.Windows.Automation.TextPattern> control pattern from an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a><span data-ttu-id="6f627-115">컨트롤 패턴에 대한 속성 검색</span><span class="sxs-lookup"><span data-stu-id="6f627-115">Retrieving Properties on Control Patterns</span></span>  
 <span data-ttu-id="6f627-116">클라이언트는 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType>를 호출하고 적절한 형식으로 반환되는 개체를 캐스팅하여 컨트롤 패턴에 대한 속성 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-116">Clients can retrieve the property values on control patterns by calling either <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> or <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> and casting the object returned to an appropriate type.</span></span> <span data-ttu-id="6f627-117">대 한 자세한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 참조 [클라이언트에 대 한 UI 자동화 속성](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-117">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
 <span data-ttu-id="6f627-118">`GetPropertyValue` 접근자를 통해 [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] 메서드 외에 속성 값을 검색하여 패턴에 대한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-118">In addition to the `GetPropertyValue` methods, property values can be retrieved through the [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] accessors to access the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties on a pattern.</span></span>  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a><span data-ttu-id="6f627-119">가변 패턴을 사용하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6f627-119">Controls with Variable Patterns</span></span>  
 <span data-ttu-id="6f627-120">일부 컨트롤 형식은 컨트롤의 상태 또는 컨트롤이 사용되는 방식에 따라 다양한 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-120">Some control types support different patterns depending on their state or the manner in which the control is being used.</span></span> <span data-ttu-id="6f627-121">가변 패턴을 사용할 수 있는 컨트롤의 예로는 목록 보기(미리 보기, 타일, 아이콘, 목록, 자세히), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] 차트(원형, 꺾은선형, 막대형, 수식이 있는 셀 값), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]의 문서 영역(기본, 웹 모양, 개요, 인쇄 모양, 인쇄 미리 보기) 및 [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] 스킨이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-121">Examples of controls that can have variable patterns are list views (thumbnails, tiles, icons, list, details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] Charts (Pie, Line, Bar, Cell Value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]'s document area (Normal, Web Layout, Outline, Print Layout, Print Preview), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span>  
  
 <span data-ttu-id="6f627-122">사용자 지정 컨트롤 형식을 구현하는 컨트롤에는 해당 기능을 나타내는 데 필요한 컨트롤 패턴 집합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f627-122">Controls implementing custom control types can have any set of control patterns that are needed to represent their functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f627-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f627-123">See Also</span></span>  
 [<span data-ttu-id="6f627-124">UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="6f627-124">UI Automation Control Patterns</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)  
 [<span data-ttu-id="6f627-125">UI 자동화 텍스트 패턴</span><span class="sxs-lookup"><span data-stu-id="6f627-125">UI Automation Text Pattern</span></span>](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)  
 [<span data-ttu-id="6f627-126">UI 자동화를 사용하여 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="6f627-126">Invoke a Control Using UI Automation</span></span>](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [<span data-ttu-id="6f627-127">UI 자동화를 사용하여 확인란의 전환 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="6f627-127">Get the Toggle State of a Check Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [<span data-ttu-id="6f627-128">UI 자동화 클라이언트에 대한 컨트롤 패턴 매핑</span><span class="sxs-lookup"><span data-stu-id="6f627-128">Control Pattern Mapping for UI Automation Clients</span></span>](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [<span data-ttu-id="6f627-129">TextPattern 삽입 텍스트 샘플</span><span class="sxs-lookup"><span data-stu-id="6f627-129">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [<span data-ttu-id="6f627-130">TextPattern 검색 및 선택 샘플</span><span class="sxs-lookup"><span data-stu-id="6f627-130">TextPattern Search and Selection Sample</span></span>](http://msdn.microsoft.com/en-us/0a3bca57-8b72-489d-a57c-da85b7a22c7f)  
 [<span data-ttu-id="6f627-131">InvokePattern 및 ExpandCollapsePattern 메뉴 항목 샘플</span><span class="sxs-lookup"><span data-stu-id="6f627-131">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
