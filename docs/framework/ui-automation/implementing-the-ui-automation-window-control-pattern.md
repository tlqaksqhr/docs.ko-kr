---
title: "Implementing the UI Automation Window Control Pattern | Microsoft Docs"
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
  - "control patterns, Window"
  - "UI Automation, Window control pattern"
  - "Window control pattern"
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: 21
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 20
---
# Implementing the UI Automation Window Control Pattern
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 <xref:System.Windows.Automation.WindowPattern> 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현하기 위한 지침 및 규칙을 제공합니다. 추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.WindowPattern> 컨트롤 패턴은 기존의 [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)] 내에서 창을 기반으로 하는 기본적인 기능을 제공하는 컨트롤을 제공하는 데 사용됩니다. 이 컨트롤 패턴을 구현해야 하는 컨트롤의 예로는 최상위 응용 프로그램 창, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] 자식 창, 컨트롤 크기 조정 가능한 분할 창 컨트롤, 모달 대화 상자 및 풍선 도움말 창이 있습니다.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## 구현 지침 및 규칙  
 Window 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.  
  
-   UI 자동화를 사용하여 창의 크기와 화면 위치를 수정하는 기능을 지원하려면 컨트롤이 <xref:System.Windows.Automation.Provider.IWindowProvider> 외에 <xref:System.Windows.Automation.Provider.ITransformProvider>를 구현해야 합니다.  
  
-   컨트롤을 이동, 크기 조정, 최대화, 최소화 또는 닫을 수 있도록 하는 제목 표시줄 및 제목 표시줄 요소가 포함된 컨트롤은 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현해야 합니다.  
  
-   도구 설명 팝업 및 콤보 상자 또는 메뉴 드롭다운 등과 같은 컨트롤을 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현하지 않습니다.  
  
-   창과 같이 닫기 단추를 제공하는 풍선 도움말 창은 기본적인 도구 설명 팝업과는 구별됩니다.  
  
-   전체 화면 모드는 응용 프로그램에서 기능별로 다르며 일반적인 창 동작이 아니므로 IWindowProvider에서 지원되지 않습니다.  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## IWindowProvider에 필요한 멤버  
 IWindowProvider 인터페이스에는 다음과 같은 속성, 메서드 및 이벤트가 필요합니다.  
  
|필요한 멤버|멤버 형식|노트|  
|------------|-----------|--------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|속성|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|메서드|없음|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|메서드|없음|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Event|없음|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Event|없음|  
|<xref:System.Windows.Automation.WindowInteractionState>|이벤트|<xref:System.Windows.Automation.WindowInteractionState>은 보장되지 않습니다.|  
  
<a name="Exceptions"></a>   
## 예외  
 공급자는 다음과 같은 예외를 throw해야 합니다.  
  
|예외 형식|조건|  
|-----------|--------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> -   컨트롤이 요청된 동작을 지원하지 않는 경우.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> -   매개 변수가 유효한 값이 아닌 경우.|  
  
## 참고 항목  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)