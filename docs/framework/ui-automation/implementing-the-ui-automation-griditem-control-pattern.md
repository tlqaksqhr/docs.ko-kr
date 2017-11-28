---
title: "UI 자동화 GridItem 컨트롤 패턴 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: "15"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: daaffd02eaaf7fcb0e64dbcda4bd2ee155163f4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="e6e9c-102">UI 자동화 GridItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="e6e9c-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="e6e9c-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e6e9c-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e6e9c-105">지침 및 규칙을 구현 하기 위한이 항목에서는 소개 <xref:System.Windows.Automation.Provider.IGridItemProvider>, 속성에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="e6e9c-106">추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="e6e9c-107"><xref:System.Windows.Automation.GridItemPattern> 구현 하는 컨테이너의 개별 자식 컨트롤을 지 원하는 컨트롤 패턴은 사용 <xref:System.Windows.Automation.Provider.IGridProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="e6e9c-108">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e6e9c-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="e6e9c-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="e6e9c-110">구현할 때 <xref:System.Windows.Automation.Provider.IGridProvider>, 다음 지침 및 규칙:</span><span class="sxs-lookup"><span data-stu-id="e6e9c-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="e6e9c-111">표 좌표는 왼쪽 상단 셀 좌표가 (0, 0)인 0부터 시작되는 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="e6e9c-112">병합된 셀은 UI 자동화 공급자가 정의한 기본 앵커 셀을 기반으로 해당 <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> 및 <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> 속성을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="e6e9c-113">일반적으로, 기본 앵커 셀은 맨 위쪽 및 맨 왼쪽 행이나 열입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="e6e9c-114"><xref:System.Windows.Automation.Provider.IGridItemProvider>셀 병합 또는 분할과 같은 표이 활성 조작 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="e6e9c-115"><xref:System.Windows.Automation.Provider.IGridItemProvider>를 구현하는 컨트롤은 일반적으로 키보드를 사용하여 트래버스(즉, UI 자동화 클라이언트가 인접 컨트롤로 이동할 수 있음)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="e6e9c-116">IGridItemProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="e6e9c-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="e6e9c-117"><xref:System.Windows.Automation.Provider.IGridItemProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="e6e9c-118">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="e6e9c-118">Required members</span></span>|<span data-ttu-id="e6e9c-119">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="e6e9c-119">Member type</span></span>|<span data-ttu-id="e6e9c-120">노트</span><span class="sxs-lookup"><span data-stu-id="e6e9c-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="e6e9c-121">속성</span><span class="sxs-lookup"><span data-stu-id="e6e9c-121">Property</span></span>|<span data-ttu-id="e6e9c-122">없음</span><span class="sxs-lookup"><span data-stu-id="e6e9c-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="e6e9c-123">속성</span><span class="sxs-lookup"><span data-stu-id="e6e9c-123">Property</span></span>|<span data-ttu-id="e6e9c-124">없음</span><span class="sxs-lookup"><span data-stu-id="e6e9c-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="e6e9c-125">속성</span><span class="sxs-lookup"><span data-stu-id="e6e9c-125">Property</span></span>|<span data-ttu-id="e6e9c-126">없음</span><span class="sxs-lookup"><span data-stu-id="e6e9c-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="e6e9c-127">속성</span><span class="sxs-lookup"><span data-stu-id="e6e9c-127">Property</span></span>|<span data-ttu-id="e6e9c-128">없음</span><span class="sxs-lookup"><span data-stu-id="e6e9c-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="e6e9c-129">속성</span><span class="sxs-lookup"><span data-stu-id="e6e9c-129">Property</span></span>|<span data-ttu-id="e6e9c-130">없음</span><span class="sxs-lookup"><span data-stu-id="e6e9c-130">None</span></span>|  
  
 <span data-ttu-id="e6e9c-131">이 컨트롤 패턴에는 연결된 메서드 또는 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="e6e9c-132">예외</span><span class="sxs-lookup"><span data-stu-id="e6e9c-132">Exceptions</span></span>  
 <span data-ttu-id="e6e9c-133">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e9c-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e9c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6e9c-134">See Also</span></span>  
 [<span data-ttu-id="e6e9c-135">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="e6e9c-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="e6e9c-136">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="e6e9c-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="e6e9c-137">클라이언트에 대 한 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="e6e9c-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="e6e9c-138">UI 자동화 Grid 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="e6e9c-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="e6e9c-139">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="e6e9c-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="e6e9c-140">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="e6e9c-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
