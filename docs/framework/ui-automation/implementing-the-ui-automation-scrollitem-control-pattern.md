---
title: "UI 자동화 ScrollItem 컨트롤 패턴 구현 | Microsoft Docs"
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
  - "Scroll Item 컨트롤 패턴"
  - "UI 자동화 Scroll Item 컨트롤 패턴"
  - "Scroll Item 컨트롤 패턴"
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
caps.latest.revision: 16
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 16
---
# UI 자동화 ScrollItem 컨트롤 패턴 구현
> [!NOTE]
>  이 설명서는 관리 되는 사용 하려는.NET Framework 개발자를 위한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 정의 된 클래스는 <xref:System.Windows.Automation> 네임 스페이스입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 참조 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 지침 및 규칙을 구현 하기 위한이 항목에서는 소개는 <xref:System.Windows.Automation.Provider.IScrollItemProvider>, 속성, 메서드 및 이벤트에 대 한 정보를 포함 합니다. 추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.ScrollItemPattern> 컨트롤 패턴 구현 하는 컨테이너의 개별 자식 컨트롤을 지 원하는 데 사용 됩니다 <xref:System.Windows.Automation.Provider.IScrollProvider>합니다. 이 컨트롤 패턴은 자식 컨트롤과 해당 컨테이너 간에 통신 채널 역할을 하여 컨테이너가 자식 컨트롤이 표시되도록 뷰포트 내에 현재 표시된 콘텐츠(또는 영역)를 변경할 수 있습니다. 이 컨트롤 패턴을 구현 하는 컨트롤의 예 참조 [UI 자동화 클라이언트에 대 한 컨트롤 패턴 매핑](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)합니다.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
 Scroll Item 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.  
  
-   창 또는 캔버스 컨트롤 내에 포함된 항목은 IScrollItemProvider 인터페이스를 구현하는 데 필요하지 않습니다. 그러나 대 안으로,를 노출 해야 올바른 위치를 고 <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>합니다. 이 사용 하 여 UI 자동화 클라이언트 응용 프로그램을 통해는 <xref:System.Windows.Automation.ScrollPattern> 자식 항목을 표시 하는 컨테이너에 패턴 메서드를 제어 합니다.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a>IScrollItemProvider에 필요한 멤버  
 다음 메서드는 IScrollProvider 인터페이스를 구현하는 데 필요합니다.  
  
|필요한 멤버|멤버 형식|노트|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|메서드|없음|  
  
 이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>예외  
 공급자는 다음과 같은 예외를 throw해야 합니다.  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|항목을 스크롤하여 볼 수 없는 경우:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 컨트롤 패턴 개요](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [UI 자동화 공급자의 컨트롤 패턴 지원](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [클라이언트에 대 한 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)