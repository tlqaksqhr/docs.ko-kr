---
title: UI 자동화 Table 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 955d9f005a45ab805012dd43cbef27877a9dfdb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398582"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>UI 자동화 Table 컨트롤 패턴 구현
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITableProvider>를 구현하기 위한 지침 및 규칙을 제공합니다. 추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.TablePattern> 컨트롤 패턴은 자식 요소 컬렉션에 대 한 컨테이너 역할을 하는 컨트롤을 지 원하는 데 사용 됩니다. 이 요소의 자식 항목이 구현 해야 <xref:System.Windows.Automation.Provider.ITableItemProvider> 하며 행과 열으로 트래버스할 수 있는 논리적 2 차원 좌표계로 구성 되어야 합니다. 이 컨트롤 패턴은 유사 <xref:System.Windows.Automation.Provider.IGridProvider>를 구현 하는 모든 컨트롤 차이에 <xref:System.Windows.Automation.Provider.ITableProvider> 각 자식 요소에 대 한 열 및/또는 행 헤더 관계도 노출 해야 합니다. 이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
 Table 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.  
  
-   개별 셀의 내용에 대 한 액세스가의 필수 동시 구현에서 제공 된 배열 또는 2 차원의 논리적 좌표계를 통해 <xref:System.Windows.Automation.Provider.IGridProvider>합니다.  
  
-   열 또는 행 헤더는 테이블 개체 내에 포함되거나 테이블 개체와 연결된 별도의 헤더 개체에 포함될 수 있습니다.  
  
-   열 및 행 헤더에는 모든 지원 헤더는 물론 기본 헤더가 포함될 수 있습니다.  
  
> [!NOTE]
>  이 개념에서 분명 하 게 되는 [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] 스프레드시트는 사용자 정의한 "이름" 열입니다. 이제 이 열에는 사용자가 정의한 "이름" 헤더와 응용 프로그램에서 할당한 해당 열의 영숫자 지정 두 개의 헤더가 있습니다.  
  
-   참조 [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) 관련된 표 기능에 대 한 합니다.  
  
 ![복잡 한 헤더 항목이 있는 테이블입니다. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
복잡한 열 헤더가 있는 테이블의 예  
  
 ![모호한 RowOrColumnMajor 속성이 있는 테이블입니다. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
모호한 RowOrColumnMajor 속성이 있는 테이블  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a>ITableProvider에 필요한 멤버  
 ITableProvider 인터페이스에는 다음과 같은 속성 및 메서드가 필요합니다.  
  
|필요한 멤버|멤버 형식|노트|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|메서드|없음|  
  
 이 컨트롤 패턴에 연결된 이벤트가 없습니다.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>예외  
 이 컨트롤 패턴에 연결된 예외가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [UI 자동화 공급자의 컨트롤 패턴 지원](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [클라이언트용 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [UI 자동화 TableItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
