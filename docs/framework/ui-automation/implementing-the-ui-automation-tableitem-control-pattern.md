---
title: "UI 자동화 TableItem 컨트롤 패턴 구현 | Microsoft Docs"
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
  - "Table Item 컨트롤 패턴"
  - "UI 자동화 Table Item 컨트롤 패턴"
  - "TableItem 컨트롤 패턴"
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: 14
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 14
---
# UI 자동화 TableItem 컨트롤 패턴 구현
> [!NOTE]
>  이 설명서는 관리 되는 사용 하려는.NET Framework 개발자를 위한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 정의 된 클래스는 <xref:System.Windows.Automation> 네임 스페이스입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 참조 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 지침 및 규칙을 구현 하기 위한이 항목에서는 소개 <xref:System.Windows.Automation.Provider.ITableItemProvider>, 이벤트 및 속성에 대 한 정보를 포함 합니다. 추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.TableItemPattern> 컨트롤 패턴을 구현 하는 컨테이너의 자식 컨트롤을 지 원하는 데 사용 됩니다 <xref:System.Windows.Automation.Provider.ITableProvider>합니다. 개별 셀 기능에 대 한 액세스는 필요한 동시 구현에 의해 제공 됩니다 <xref:System.Windows.Automation.Provider.IGridItemProvider>합니다. 이 컨트롤 패턴은 유사 <xref:System.Windows.Automation.Provider.IGridItemProvider> 를 구현 하는 컨트롤 차이에 <xref:System.Windows.Automation.Provider.ITableItemProvider> 개별 셀 및 행 및 열 정보 간의 관계를 프로그래밍 방식으로 노출 해야 합니다. 이 컨트롤 패턴을 구현 하는 컨트롤의 예 참조 [UI 자동화 클라이언트에 대 한 컨트롤 패턴 매핑](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)합니다.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
  
-   관련 된 표 항목 기능에 대 한 참조 [UI 자동화 GridItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)합니다.  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>ITableItemProvider에 필요한 멤버  
  
|필요한 멤버|멤버 형식|노트|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|메서드|없음|  
  
 이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>예외  
 이 컨트롤 패턴에 연결된 예외가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [UI 자동화 공급자의 컨트롤 패턴 지원](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [클라이언트에 대 한 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI 자동화 Table 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)   
 [UI 자동화 GridItem 컨트롤 패턴 구현](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)   
 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)