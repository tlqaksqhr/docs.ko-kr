---
title: UI 자동화 RangeValue 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 219f460906d2892ae6cd76d13a2b17378e02b9b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399331"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="73f09-102">UI 자동화 RangeValue 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="73f09-102">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="73f09-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="73f09-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73f09-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="73f09-105">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IRangeValueProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="73f09-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="73f09-107"><xref:System.Windows.Automation.RangeValuePattern> 컨트롤 패턴은 범위 내의 값으로 설정할 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-107">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="73f09-108">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73f09-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="73f09-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="73f09-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="73f09-110">Range Value 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="73f09-110">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="73f09-111">컨트롤을 통해 로캘 또는 사용자 기본 설정에 따라 지원되는 속성을 보정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-111">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="73f09-112">이러한 예로 온도가 화씨 또는 섭씨로 표시되도록 설정할 수 있는 온도계 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-112">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
-   <span data-ttu-id="73f09-113">진행률 표시줄 또는 슬라이더와 같은 모호한 범위 값이 있는 컨트롤에서는 해당 값을 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-113">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="73f09-114">![진행률 표시줄입니다. ] (../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="73f09-114">![Progress bar.](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="73f09-115">이 예로는 값이 정수 유형인 진행률 표시줄이며 최소 및 최대 속성 값이 각각 0과 100으로 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-115">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>   
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="73f09-116">IRangeValueProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="73f09-116">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="73f09-117">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="73f09-117">Required member</span></span>|<span data-ttu-id="73f09-118">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="73f09-118">Member type</span></span>|<span data-ttu-id="73f09-119">노트</span><span class="sxs-lookup"><span data-stu-id="73f09-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="73f09-120">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-120">Property</span></span>|<span data-ttu-id="73f09-121">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-121">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="73f09-122">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-122">Property</span></span>|<span data-ttu-id="73f09-123">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="73f09-124">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-124">Property</span></span>|<span data-ttu-id="73f09-125">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="73f09-126">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-126">Property</span></span>|<span data-ttu-id="73f09-127">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="73f09-128">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-128">Property</span></span>|<span data-ttu-id="73f09-129">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="73f09-130">속성</span><span class="sxs-lookup"><span data-stu-id="73f09-130">Property</span></span>|<span data-ttu-id="73f09-131">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="73f09-132">메서드</span><span class="sxs-lookup"><span data-stu-id="73f09-132">Methods</span></span>|<span data-ttu-id="73f09-133">없음</span><span class="sxs-lookup"><span data-stu-id="73f09-133">None</span></span>|  
  
 <span data-ttu-id="73f09-134">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="73f09-135">예외</span><span class="sxs-lookup"><span data-stu-id="73f09-135">Exceptions</span></span>  
 <span data-ttu-id="73f09-136">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="73f09-137">예외 형식</span><span class="sxs-lookup"><span data-stu-id="73f09-137">Exception type</span></span>|<span data-ttu-id="73f09-138">조건</span><span class="sxs-lookup"><span data-stu-id="73f09-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="73f09-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> 은 <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> 보다 크거나 <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>보다 작은 값으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f09-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73f09-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73f09-140">See Also</span></span>  
 [<span data-ttu-id="73f09-141">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="73f09-141">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="73f09-142">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="73f09-142">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="73f09-143">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="73f09-143">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="73f09-144">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="73f09-144">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="73f09-145">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="73f09-145">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
