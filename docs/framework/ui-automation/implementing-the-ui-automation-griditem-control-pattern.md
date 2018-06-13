---
title: UI 자동화 GridItem 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: bfe7fb8ab64f148d8ca5af0e419ca60690a1acce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408290"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>UI 자동화 GridItem 컨트롤 패턴 구현
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 지침 및 규칙을 구현 하기 위한이 항목에서는 소개 <xref:System.Windows.Automation.Provider.IGridItemProvider>, 속성에 대 한 정보를 포함 합니다. 추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.GridItemPattern> 구현 하는 컨테이너의 개별 자식 컨트롤을 지 원하는 컨트롤 패턴은 사용 <xref:System.Windows.Automation.Provider.IGridProvider>합니다. 이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
 구현할 때 <xref:System.Windows.Automation.Provider.IGridProvider>, 다음 지침 및 규칙:  
  
-   표 좌표는 왼쪽 상단 셀 좌표가 (0, 0)인 0부터 시작되는 좌표입니다.  
  
-   병합된 셀은 UI 자동화 공급자가 정의한 기본 앵커 셀을 기반으로 해당 <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> 및 <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> 속성을 보고합니다. 일반적으로, 기본 앵커 셀은 맨 위쪽 및 맨 왼쪽 행이나 열입니다.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider> 셀 병합 또는 분할과 같은 표이 활성 조작 제공 하지 않습니다.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider>를 구현하는 컨트롤은 일반적으로 키보드를 사용하여 트래버스(즉, UI 자동화 클라이언트가 인접 컨트롤로 이동할 수 있음)할 수 있습니다.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>IGridItemProvider에 필요한 멤버  
 <xref:System.Windows.Automation.Provider.IGridItemProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.  
  
|필요한 멤버|멤버 형식|노트|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|속성|없음|  
  
 이 컨트롤 패턴에는 연결된 메서드 또는 이벤트가 없습니다.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>예외  
 이 컨트롤 패턴에 연결된 예외가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [UI 자동화 공급자의 컨트롤 패턴 지원](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [클라이언트용 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
