---
title: "UI 자동화 TableItem 컨트롤 패턴 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5861ab24627f9b78cd20f97fcdb1b1b3d681991a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="404be-102">UI 자동화 TableItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="404be-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="404be-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="404be-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="404be-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404be-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="404be-105">지침 및 규칙을 구현 하기 위한이 항목에서는 소개 <xref:System.Windows.Automation.Provider.ITableItemProvider>, 이벤트 및 속성에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="404be-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="404be-106">추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404be-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="404be-107"><xref:System.Windows.Automation.TableItemPattern> 구현 하는 컨테이너의 자식 컨트롤을 지 원하는 컨트롤 패턴은 사용 <xref:System.Windows.Automation.Provider.ITableProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="404be-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="404be-108">필수 동시 구현에서 개별 셀 기능에 대 한 액세스 제공 <xref:System.Windows.Automation.Provider.IGridItemProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="404be-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="404be-109">이 컨트롤 패턴은 유사 <xref:System.Windows.Automation.Provider.IGridItemProvider> 구현 모든 컨트롤 차이에 <xref:System.Windows.Automation.Provider.ITableItemProvider> 개별 셀과 셀의 행 및 열 정보 간의 관계를 프로그래밍 방식으로 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="404be-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="404be-110">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404be-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="404be-111">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="404be-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="404be-112">관련된 표 항목 기능에 대 한 참조 [UI 자동화 GridItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="404be-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="404be-113">ITableItemProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="404be-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="404be-114">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="404be-114">Required member</span></span>|<span data-ttu-id="404be-115">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="404be-115">Member type</span></span>|<span data-ttu-id="404be-116">노트</span><span class="sxs-lookup"><span data-stu-id="404be-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="404be-117">메서드</span><span class="sxs-lookup"><span data-stu-id="404be-117">Method</span></span>|<span data-ttu-id="404be-118">없음</span><span class="sxs-lookup"><span data-stu-id="404be-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="404be-119">메서드</span><span class="sxs-lookup"><span data-stu-id="404be-119">Method</span></span>|<span data-ttu-id="404be-120">없음</span><span class="sxs-lookup"><span data-stu-id="404be-120">None</span></span>|  
  
 <span data-ttu-id="404be-121">이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="404be-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="404be-122">예외</span><span class="sxs-lookup"><span data-stu-id="404be-122">Exceptions</span></span>  
 <span data-ttu-id="404be-123">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="404be-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404be-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="404be-124">See Also</span></span>  
 [<span data-ttu-id="404be-125">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="404be-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="404be-126">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="404be-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="404be-127">클라이언트에 대 한 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="404be-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="404be-128">UI 자동화 Table 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="404be-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="404be-129">UI 자동화 GridItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="404be-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="404be-130">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="404be-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="404be-131">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="404be-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
