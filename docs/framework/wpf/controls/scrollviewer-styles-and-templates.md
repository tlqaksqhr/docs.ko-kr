---
title: "ScrollViewer 스타일 및 템플릿 | Microsoft Docs"
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
  - "ControlTemplate[WPF], ScrollViewer"
  - "요소[WPF], ScrollViewer"
  - "ScrollViewer[WPF], 스타일 및 템플릿"
  - "상태[WPF], ScrollViewer"
  - "스타일[WPF], ScrollViewer"
  - "템플릿[WPF], ScrollViewer"
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ScrollViewer 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## ScrollViewer 요소  
 다음 표에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_ScrollContentPresenter|<xref:System.Windows.Controls.ScrollContentPresenter>|<xref:System.Windows.Controls.ScrollViewer>의 콘텐츠에 대한 자리 표시자입니다.|  
|PART\_HorizontalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|내용을 가로로 스크롤하는 데 사용되는 <xref:System.Windows.Controls.Primitives.ScrollBar>입니다.|  
|PART\_VerticalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|내용을 세로로 스크롤하는 데 사용되는 <xref:System.Windows.Controls.Primitives.ScrollBar>입니다.|  
  
## ScrollViewer 상태  
 다음 표에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## ScrollViewer ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
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