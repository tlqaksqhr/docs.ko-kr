---
title: "UI 자동화 GridItem 컨트롤 패턴 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GridItem 컨트롤 패턴"
  - "UI 자동화 GridItem 컨트롤 패턴"
  - "GridItem 컨트롤 패턴"
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# UI 자동화 GridItem 컨트롤 패턴 구현
> [!NOTE]
>  이 설명서는 관리 되는 사용 하려는.NET Framework 개발자를 위한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 정의 된 클래스는 <xref:System.Windows.Automation> 네임 스페이스입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 참조 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 지침 및 규칙을 구현 하기 위한이 항목에서는 소개 <xref:System.Windows.Automation.Provider.IGridItemProvider>, 속성에 대 한 정보를 포함 합니다. 추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.GridItemPattern> 컨트롤 패턴 구현 하는 컨테이너의 개별 자식 컨트롤을 지 원하는 데 사용 됩니다 <xref:System.Windows.Automation.Provider.IGridProvider>합니다. 이 컨트롤 패턴을 구현 하는 컨트롤의 예 참조 [UI 자동화 클라이언트에 대 한 컨트롤 패턴 매핑](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)합니다.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
 구현 하는 경우 <xref:System.Windows.Automation.Provider.IGridProvider>, 다음 지침 및 규칙:  
  
-   표 좌표는 왼쪽 상단 셀 좌표가 (0, 0)인 0부터 시작되는 좌표입니다.  
  
-   병합 된 셀에서 보고 자신의 <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> 및 <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> UI 자동화 공급자에서 정의 된 속성의 내부 앵커 셀 기반 합니다. 일반적으로, 기본 앵커 셀은 맨 위쪽 및 맨 왼쪽 행이나 열입니다.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider> 셀 병합 이나 분할과 같은 모눈의 활성 조작을 제공 하지 않습니다.  
  
-   구현 하는 컨트롤 <xref:System.Windows.Automation.Provider.IGridItemProvider> 일반적으로 (즉, UI 자동화 클라이언트 이동할 수 있으며 인접 한 컨트롤에) 키보드를 사용 하 여 합니다.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>IGridItemProvider에 필요한 멤버  
 다음 속성 및 메서드는 구현에 필요한 <xref:System.Windows.Automation.Provider.IGridItemProvider>합니다.  
  
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
 [클라이언트에 대 한 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI 자동화 Grid 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)   
 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)