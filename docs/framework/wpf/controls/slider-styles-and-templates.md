---
title: "Slider 스타일 및 템플릿 | Microsoft Docs"
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
  - "ControlTemplate[WPF], Slider"
  - "요소[WPF], Slider"
  - "Slider[WPF], 스타일 및 템플릿"
  - "상태[WPF], Slider"
  - "스타일[WPF], Slider"
  - "템플릿[WPF], Slider"
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Slider 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## Slider 요소  
 다음 표에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_Track|<xref:System.Windows.Controls.Primitives.Track>|<xref:System.Windows.Controls.Slider>의 위치를 나타내는 요소의 컨테이너입니다.|  
|PART\_SelectionRange|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.Controls.Slider>를 따라 선택 범위를 표시하는 요소입니다.  선택 범위는 <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>가 `true`인 경우에만 표시됩니다.|  
  
## Slider 상태  
 다음 표에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|--------------------|-------------------------|--------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|Disabled|CommonStates|컨트롤이 사용하지 않도록 설정되어 있습니다.|  
|Focused|FocusStates|컨트롤에 포커스가 있습니다.|  
|Unfocused|FocusStates|컨트롤에 포커스가 없습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## Slider ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면          [Styling with ControlTemplates 샘플](http://go.microsoft.com/fwlink/?LinkID=160041)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)