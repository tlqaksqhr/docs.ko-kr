---
title: "UI 자동화 Table 컨트롤 패턴 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4a1fbe175abf07eaccfd177c6e32f5515e88c4ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="f7910-102">UI 자동화 Table 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="f7910-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="f7910-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f7910-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7910-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f7910-105">이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITableProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="f7910-106">추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="f7910-107"><xref:System.Windows.Automation.TablePattern> 컨트롤 패턴은 자식 요소 컬렉션에 대 한 컨테이너 역할을 하는 컨트롤을 지 원하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="f7910-108">이 요소의 자식 항목이 구현 해야 <xref:System.Windows.Automation.Provider.ITableItemProvider> 하며 행과 열으로 트래버스할 수 있는 논리적 2 차원 좌표계로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="f7910-109">이 컨트롤 패턴은 유사 <xref:System.Windows.Automation.Provider.IGridProvider>를 구현 하는 모든 컨트롤 차이에 <xref:System.Windows.Automation.Provider.ITableProvider> 각 자식 요소에 대 한 열 및/또는 행 헤더 관계도 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="f7910-110">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7910-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f7910-111">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="f7910-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f7910-112">Table 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="f7910-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="f7910-113">개별 셀의 내용에 대 한 액세스가의 필수 동시 구현에서 제공 된 배열 또는 2 차원의 논리적 좌표계를 통해 <xref:System.Windows.Automation.Provider.IGridProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
-   <span data-ttu-id="f7910-114">열 또는 행 헤더는 테이블 개체 내에 포함되거나 테이블 개체와 연결된 별도의 헤더 개체에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
-   <span data-ttu-id="f7910-115">열 및 행 헤더에는 모든 지원 헤더는 물론 기본 헤더가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7910-116">이 개념에서 분명 하 게 되는 [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] 스프레드시트는 사용자 정의한 "이름" 열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-116">This concept becomes evident in a [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="f7910-117">이제 이 열에는 사용자가 정의한 "이름" 헤더와 응용 프로그램에서 할당한 해당 열의 영숫자 지정 두 개의 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
-   <span data-ttu-id="f7910-118">참조 [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) 관련된 표 기능에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-118">See [Implementing the UI Automation Grid Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="f7910-119">![복잡 한 헤더 항목이 있는 테이블입니다. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="f7910-119">![Table with complex header items.](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="f7910-120">복잡한 열 헤더가 있는 테이블의 예</span><span class="sxs-lookup"><span data-stu-id="f7910-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="f7910-121">![모호한 RowOrColumnMajor 속성이 있는 테이블입니다. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="f7910-121">![Table with ambiguous RowOrColumnMajor property.](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="f7910-122">모호한 RowOrColumnMajor 속성이 있는 테이블</span><span class="sxs-lookup"><span data-stu-id="f7910-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="f7910-123">ITableProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="f7910-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="f7910-124">ITableProvider 인터페이스에는 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="f7910-125">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="f7910-125">Required members</span></span>|<span data-ttu-id="f7910-126">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="f7910-126">Member type</span></span>|<span data-ttu-id="f7910-127">노트</span><span class="sxs-lookup"><span data-stu-id="f7910-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="f7910-128">속성</span><span class="sxs-lookup"><span data-stu-id="f7910-128">Property</span></span>|<span data-ttu-id="f7910-129">없음</span><span class="sxs-lookup"><span data-stu-id="f7910-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="f7910-130">메서드</span><span class="sxs-lookup"><span data-stu-id="f7910-130">Method</span></span>|<span data-ttu-id="f7910-131">없음</span><span class="sxs-lookup"><span data-stu-id="f7910-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="f7910-132">메서드</span><span class="sxs-lookup"><span data-stu-id="f7910-132">Method</span></span>|<span data-ttu-id="f7910-133">없음</span><span class="sxs-lookup"><span data-stu-id="f7910-133">None</span></span>|  
  
 <span data-ttu-id="f7910-134">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="f7910-135">예외</span><span class="sxs-lookup"><span data-stu-id="f7910-135">Exceptions</span></span>  
 <span data-ttu-id="f7910-136">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7910-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7910-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7910-137">See Also</span></span>  
 [<span data-ttu-id="f7910-138">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="f7910-138">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="f7910-139">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="f7910-139">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="f7910-140">클라이언트에 대 한 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="f7910-140">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="f7910-141">UI 자동화 TableItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="f7910-141">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [<span data-ttu-id="f7910-142">UI 자동화 Grid 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="f7910-142">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="f7910-143">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="f7910-143">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="f7910-144">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="f7910-144">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
