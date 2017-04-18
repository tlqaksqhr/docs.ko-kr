---
title: "ToolBar 스타일 및 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate[WPF], ToolBar"
  - "요소[WPF], ToolBar"
  - "상태[WPF], ToolBar"
  - "스타일[WPF], ToolBar"
  - "템플릿[WPF], ToolBar"
  - "Toolbar[WPF], 스타일 및 템플릿"
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# ToolBar 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## ToolBar 요소  
 다음 표에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_ToolBarPanel|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<xref:System.Windows.Controls.ToolBar>의 컨트롤을 포함하는 개체입니다.|  
|PART\_ToolBarOverflowPanel|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<xref:System.Windows.Controls.ToolBar>의 오버플로 영역에 있는 컨트롤을 포함하는 개체입니다.|  
  
 <xref:System.Windows.Controls.ToolBar>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만들 경우 템플릿의 <xref:System.Windows.Controls.ScrollViewer> 내에 <xref:System.Windows.Controls.ItemsPresenter>가 포함될 수 있습니다.  <xref:System.Windows.Controls.ItemsPresenter>는 각 항목을 <xref:System.Windows.Controls.ToolBar>에 표시하고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>가 <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아니면 <xref:System.Windows.Controls.ItemsPresenter>에 `ItemsPresenter`라는 이름을 지정해야 합니다.  
  
## ToolBar 상태  
 다음 표에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## ToolBar ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ToolBar> 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates 샘플](http://go.microsoft.com/fwlink/?LinkID=160041)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)