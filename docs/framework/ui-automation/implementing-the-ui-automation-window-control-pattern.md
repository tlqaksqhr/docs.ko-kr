---
title: "UI 자동화 Window 컨트롤 패턴 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3f1b44184f1a241943d9fa9d60a62a703dbaf0d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="aecb0-102">UI 자동화 Window 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="aecb0-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="aecb0-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="aecb0-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aecb0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="aecb0-105">이 항목에서는 <xref:System.Windows.Automation.Provider.IWindowProvider>속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.WindowPattern> 를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="aecb0-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="aecb0-107"><xref:System.Windows.Automation.WindowPattern> 컨트롤 패턴은 기존의 [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]내에서 창을 기반으로 하는 기본적인 기능을 제공하는 컨트롤을 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)].</span></span> <span data-ttu-id="aecb0-108">이 컨트롤 패턴을 구현해야 하는 컨트롤의 예로는 최상위 응용 프로그램 창, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] 자식 창, 컨트롤 크기 조정 가능한 분할 창 컨트롤, 모달 대화 상자 및 풍선 도움말 창이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-108">Examples of controls that must implement this control pattern include top-level application windows, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="aecb0-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="aecb0-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="aecb0-110">Window 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="aecb0-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="aecb0-111">UI 자동화를 사용하여 창의 크기와 화면 위치를 수정하는 기능을 지원하려면 컨트롤이 <xref:System.Windows.Automation.Provider.ITransformProvider> 외에 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="aecb0-112">컨트롤을 이동, 크기 조정, 최대화, 최소화 또는 닫을 수 있도록 하는 제목 표시줄 및 제목 표시줄 요소가 포함된 컨트롤은 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="aecb0-113">도구 설명 팝업 및 콤보 상자 또는 메뉴 드롭다운 등과 같은 컨트롤을 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="aecb0-114">창과 같이 닫기 단추를 제공하는 풍선 도움말 창은 기본적인 도구 설명 팝업과는 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
-   <span data-ttu-id="aecb0-115">전체 화면 모드는 응용 프로그램에서 기능별로 다르며 일반적인 창 동작이 아니므로 IWindowProvider에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="aecb0-116">IWindowProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="aecb0-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="aecb0-117">IWindowProvider 인터페이스에는 다음과 같은 속성, 메서드 및 이벤트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="aecb0-118">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="aecb0-118">Required member</span></span>|<span data-ttu-id="aecb0-119">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="aecb0-119">Member type</span></span>|<span data-ttu-id="aecb0-120">노트</span><span class="sxs-lookup"><span data-stu-id="aecb0-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="aecb0-121">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-121">Property</span></span>|<span data-ttu-id="aecb0-122">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="aecb0-123">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-123">Property</span></span>|<span data-ttu-id="aecb0-124">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="aecb0-125">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-125">Property</span></span>|<span data-ttu-id="aecb0-126">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="aecb0-127">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-127">Property</span></span>|<span data-ttu-id="aecb0-128">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="aecb0-129">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-129">Property</span></span>|<span data-ttu-id="aecb0-130">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="aecb0-131">속성</span><span class="sxs-lookup"><span data-stu-id="aecb0-131">Property</span></span>|<span data-ttu-id="aecb0-132">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="aecb0-133">메서드</span><span class="sxs-lookup"><span data-stu-id="aecb0-133">Method</span></span>|<span data-ttu-id="aecb0-134">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="aecb0-135">메서드</span><span class="sxs-lookup"><span data-stu-id="aecb0-135">Method</span></span>|<span data-ttu-id="aecb0-136">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="aecb0-137">메서드</span><span class="sxs-lookup"><span data-stu-id="aecb0-137">Method</span></span>|<span data-ttu-id="aecb0-138">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="aecb0-139">Event</span><span class="sxs-lookup"><span data-stu-id="aecb0-139">Event</span></span>|<span data-ttu-id="aecb0-140">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="aecb0-141">Event</span><span class="sxs-lookup"><span data-stu-id="aecb0-141">Event</span></span>|<span data-ttu-id="aecb0-142">없음</span><span class="sxs-lookup"><span data-stu-id="aecb0-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="aecb0-143">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="aecb0-143">Event</span></span>|<span data-ttu-id="aecb0-144"><xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="aecb0-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="aecb0-145">예외</span><span class="sxs-lookup"><span data-stu-id="aecb0-145">Exceptions</span></span>  
 <span data-ttu-id="aecb0-146">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="aecb0-147">예외 형식</span><span class="sxs-lookup"><span data-stu-id="aecb0-147">Exception type</span></span>|<span data-ttu-id="aecb0-148">조건</span><span class="sxs-lookup"><span data-stu-id="aecb0-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="aecb0-149">-컨트롤을 지원 하지 않는 경우 요청된 된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="aecb0-150">-매개 변수가 유효한 숫자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aecb0-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aecb0-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aecb0-151">See Also</span></span>  
 [<span data-ttu-id="aecb0-152">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="aecb0-152">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="aecb0-153">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="aecb0-153">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="aecb0-154">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="aecb0-154">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="aecb0-155">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="aecb0-155">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="aecb0-156">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="aecb0-156">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
