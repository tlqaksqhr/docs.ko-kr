---
title: "Implementing the UI Automation Transform Control Pattern | Microsoft Docs"
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
  - "control patterns, Transform"
  - "Transform control pattern"
  - "UI Automation, Transform control pattern"
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
caps.latest.revision: 14
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 14
---
# Implementing the UI Automation Transform Control Pattern
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하기 위한 지침 및 규칙을 제공합니다. 추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.TransformPattern> 컨트롤 패턴은 2차원 공간 내에서 이동, 크기 조정 또는 회전할 수 있는 컨트롤을 지원하는 데 사용됩니다. 이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## 구현 지침 및 규칙  
 Transform 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.  
  
-   이 컨트롤 패턴에 대한 지원은 데스크톱의 개체로 제한되지 않습니다. 컨테이너 경계 내에서 자식 항목을 자유롭게 이동, 크기 조정 또는 회전할 수 있는 경우 이 컨트롤 패턴은 컨테이너 개체의 자식 항목에서도 지원되어야 합니다.  
  
-   개체를 이동하거나, 크기를 조정하거나, 회전할 수 없습니다. 이렇게 하면 결과로 표시되는 화면 위치가 컨테이너의 좌표를 완전히 벗어나므로 키보드 또는 마우스에 액세스할 수 없습니다\(예: 최상위 창이 화면을 벗어나거나 자식 개체가 컨테이너의 뷰포트 경계 밖으로 이동되는 경우\). 이러한 경우에는, 개체가 컨테이너 경계 내에 있도록 재정의되어 상단 또는 왼쪽 좌표로 가능하면 요청된 화면 좌표와 최대한 가깝게 배치됩니다.  
  
-   다중 모니터 시스템의 경우 개체가 이동, 크기 조정 또는 회전되어 조합된 데스크톱 화면 좌표를 완전히 벗어나면 이 개체는 요청된 좌표에 최대한 가깝게 기본 모니터에 배치됩니다.  
  
-   모든 매개 변수 및 속성 값은 절대 값이며 로캘과 무관합니다.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## ITransformProvider에 필요한 멤버  
 <xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.  
  
|필요한 멤버|멤버 형식|노트|  
|------------|-----------|--------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|메서드|없음|  
  
 이 컨트롤 패턴에 연결된 이벤트가 없습니다.  
  
<a name="Exceptions"></a>   
## 예외  
 공급자는 다음과 같은 예외를 throw해야 합니다.  
  
|예외 형식|조건|  
|-----------|--------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> -   <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty>가 false인 경우.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> -   <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty>가 false인 경우.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> -   <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty>가 false인 경우.|  
  
## 참고 항목  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)