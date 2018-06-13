---
title: UI 자동화 Transform 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 65c90e8e9f0653181b98645bf453c9d78c14bc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408267"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="2c1ed-102">UI 자동화 Transform 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="2c1ed-102">Implementing the UI Automation Transform Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="2c1ed-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2c1ed-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="2c1ed-105">이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="2c1ed-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="2c1ed-107"><xref:System.Windows.Automation.TransformPattern> 컨트롤 패턴은 2차원 공간 내에서 이동, 크기 조정 또는 회전할 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-107">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="2c1ed-108">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2c1ed-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="2c1ed-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="2c1ed-110">Transform 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-110">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="2c1ed-111">이 컨트롤 패턴에 대한 지원은 데스크톱의 개체로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-111">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="2c1ed-112">컨테이너 경계 내에서 자식 항목을 자유롭게 이동, 크기 조정 또는 회전할 수 있는 경우 이 컨트롤 패턴은 컨테이너 개체의 자식 항목에서도 지원되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-112">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
-   <span data-ttu-id="2c1ed-113">개체를 이동하거나, 크기를 조정하거나, 회전할 수 없습니다. 이렇게 하면 결과로 표시되는 화면 위치가 컨테이너의 좌표를 완전히 벗어나므로 키보드 또는 마우스에 액세스할 수 없습니다(예: 최상위 창이 화면을 벗어나거나 자식 개체가 컨테이너의 뷰포트 경계 밖으로 이동되는 경우).</span><span class="sxs-lookup"><span data-stu-id="2c1ed-113">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="2c1ed-114">이러한 경우에는, 개체가 컨테이너 경계 내에 있도록 재정의되어 상단 또는 왼쪽 좌표로 가능하면 요청된 화면 좌표와 최대한 가깝게 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-114">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
-   <span data-ttu-id="2c1ed-115">다중 모니터 시스템의 경우 개체가 이동, 크기 조정 또는 회전되어 조합된 데스크톱 화면 좌표를 완전히 벗어나면 이 개체는 요청된 좌표에 최대한 가깝게 기본 모니터에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-115">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
-   <span data-ttu-id="2c1ed-116">모든 매개 변수 및 속성 값은 절대 값이며 로캘과 무관합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-116">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="2c1ed-117">ITransformProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="2c1ed-117">Required Members for ITransformProvider</span></span>  
 <span data-ttu-id="2c1ed-118"><xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="2c1ed-119">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="2c1ed-119">Required members</span></span>|<span data-ttu-id="2c1ed-120">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="2c1ed-120">Member type</span></span>|<span data-ttu-id="2c1ed-121">노트</span><span class="sxs-lookup"><span data-stu-id="2c1ed-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="2c1ed-122">속성</span><span class="sxs-lookup"><span data-stu-id="2c1ed-122">Property</span></span>|<span data-ttu-id="2c1ed-123">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="2c1ed-124">속성</span><span class="sxs-lookup"><span data-stu-id="2c1ed-124">Property</span></span>|<span data-ttu-id="2c1ed-125">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="2c1ed-126">속성</span><span class="sxs-lookup"><span data-stu-id="2c1ed-126">Property</span></span>|<span data-ttu-id="2c1ed-127">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="2c1ed-128">메서드</span><span class="sxs-lookup"><span data-stu-id="2c1ed-128">Method</span></span>|<span data-ttu-id="2c1ed-129">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="2c1ed-130">메서드</span><span class="sxs-lookup"><span data-stu-id="2c1ed-130">Method</span></span>|<span data-ttu-id="2c1ed-131">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="2c1ed-132">메서드</span><span class="sxs-lookup"><span data-stu-id="2c1ed-132">Method</span></span>|<span data-ttu-id="2c1ed-133">없음</span><span class="sxs-lookup"><span data-stu-id="2c1ed-133">None</span></span>|  
  
 <span data-ttu-id="2c1ed-134">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="2c1ed-135">예외</span><span class="sxs-lookup"><span data-stu-id="2c1ed-135">Exceptions</span></span>  
 <span data-ttu-id="2c1ed-136">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="2c1ed-137">예외 형식</span><span class="sxs-lookup"><span data-stu-id="2c1ed-137">Exception Type</span></span>|<span data-ttu-id="2c1ed-138">조건</span><span class="sxs-lookup"><span data-stu-id="2c1ed-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="2c1ed-139">If는 <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> 은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-139">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="2c1ed-140">If는 <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> 은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-140">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="2c1ed-141">If는 <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> 은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="2c1ed-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c1ed-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c1ed-142">See Also</span></span>  
 [<span data-ttu-id="2c1ed-143">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="2c1ed-143">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="2c1ed-144">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="2c1ed-144">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="2c1ed-145">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="2c1ed-145">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="2c1ed-146">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="2c1ed-146">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="2c1ed-147">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="2c1ed-147">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
