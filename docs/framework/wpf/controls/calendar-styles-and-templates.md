---
title: "Calendar 스타일 및 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "달력[WPF], 스타일 및 템플릿"
  - "ControlTemplate[WPF], Calendar"
  - "요소[WPF], Calendar"
  - "상태[WPF], Calendar"
  - "스타일[WPF], Calendar"
  - "템플릿[WPF], Calendar"
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Calendar 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## Calendar 요소  
 다음 표에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|<xref:System.Windows.Controls.Calendar>에 현재 표시된 월 또는 연도입니다.|  
|PART\_Root|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Primitives.CalendarItem>이 들어 있는 패널입니다.|  
  
## Calendar 상태  
 다음 표에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|--------------------|-------------------------|--------|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## CalendarItem 요소  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarItem> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_Root|<xref:System.Windows.FrameworkElement>|컨트롤의 루트입니다.|  
|PART\_PreviousButton|<xref:System.Windows.Controls.Button>|클릭하면 달력의 이전 페이지를 표시하는 단추입니다.|  
|PART\_NextButton|<xref:System.Windows.Controls.Button>|클릭하면 달력의 다음 페이지를 표시하는 단추입니다.|  
|PART\_HeaderButton|<xref:System.Windows.Controls.Button>|월 모드, 년 모드, 10년 모드 간을 전환하는 데 사용할 수 있는 단추입니다.|  
|PART\_MonthView|<xref:System.Windows.Controls.Grid>|월 모드에서 콘텐츠를 호스팅합니다.|  
|PART\_YearView|<xref:System.Windows.Controls.Grid>|년 모드 또는 10년 모드에서 콘텐츠를 호스팅합니다.|  
|PART\_DisabledVisual|<xref:System.Windows.FrameworkElement>|사용하지 않도록 설정된 상태의 오버레이입니다.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|시각적 구조를 설명하는 <xref:System.Windows.DataTemplate>입니다.|  
  
## CalendarItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarItem> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|Normal 상태|CommonStates|기본 상태입니다.|  
|Disabled 상태|CommonStates|<xref:System.Windows.UIElement.IsEnabled%2A> 속성이 `false`인 경우 달력의 상태입니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## CalendarDayButton 요소  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 컨트롤에는 명명된 요소가 없습니다.  
  
## CalendarDayButton 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>을 사용할 수 없습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 위에 있습니다.|  
|Pressed|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>을 눌렀습니다.|  
|선택함|SelectionStates|단추가 선택되어 있습니다.|  
|선택하지 않음|SelectionStates|단추가 선택되어 있지 않습니다.|  
|CalendarButtonFocused|CalendarButtonFocusStates|단추에 포커스가 있습니다.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|단추에 포커스가 없습니다.|  
|Focused|FocusStates|단추에 포커스가 있습니다.|  
|Unfocused|FocusStates|단추에 포커스가 없습니다.|  
|Active|ActiveStates|단추가 활성 상태입니다.|  
|Inactive|ActiveStates|단추가 비활성 상태입니다.|  
|RegularDay|DayStates|단추가 <xref:System.DateTime.Today%2A?displayProperty=fullName>를 나타내지 않습니다.|  
|Today|DayStates|단추가 <xref:System.DateTime.Today%2A?displayProperty=fullName>를 나타냅니다.|  
|NormalDay|BlackoutDayStates|선택할 수 있는 일을 나타내는 단추입니다.|  
|BlackoutDay|BlackoutDayStates|선택할 수 없는 일을 나타내는 단추입니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## CalendarButton 요소  
 <xref:System.Windows.Controls.Primitives.CalendarButton> 컨트롤에는 명명된 요소가 없습니다.  
  
## CalendarButton 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarButton> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>을 사용할 수 없습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.CalendarButton> 위에 있습니다.|  
|Pressed|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>을 눌렀습니다.|  
|선택함|SelectionStates|단추가 선택되어 있습니다.|  
|선택하지 않음|SelectionStates|단추가 선택되어 있지 않습니다.|  
|CalendarButtonFocused|CalendarButtonFocusStates|단추에 포커스가 있습니다.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|단추에 포커스가 없습니다.|  
|Focused|FocusStates|단추에 포커스가 있습니다.|  
|Unfocused|FocusStates|단추에 포커스가 없습니다.|  
|Active|ActiveStates|단추가 활성 상태입니다.|  
|Inactive|ActiveStates|단추가 비활성 상태입니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## Calendar ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Calendar> 컨트롤과 해당 연결 형식의 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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