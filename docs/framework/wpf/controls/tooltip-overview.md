---
title: "도구 설명 개요 | Microsoft Docs"
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
  - "컨트롤, 도구 설명"
  - "ToolTip 컨트롤, ToolTip 컨트롤 정보"
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 도구 설명 개요
도구 설명은 마우스 포인터를 <xref:System.Windows.Controls.Button>과 같은 요소 위에 잠시 올려 두면 나타나는 작은 팝업 창입니다.  이 항목에서는 도구 설명을 소개하고 도구 설명의 콘텐츠를 만들고 사용자 지정하는 방법을 설명합니다.  
  
   
  
<a name="what_is_a_tooltip"></a>   
## 도구 설명 정의  
 도구 설명이 있는 요소 위로 마우스 포인터를 이동하면 도구 설명 콘텐츠\(예를 들어 컨트롤의 기능을 설명하는 텍스트 콘텐츠\)가 포함된 창이 지정된 시간 동안 나타납니다.  사용자가 마우스 포인터를 컨트롤에서 다른 곳으로 옮기면 도구 설명 콘텐츠가 포커스를 받을 수 없기 때문에 창이 사라집니다.  
  
 도구 설명의 콘텐츠에는 한 줄 이상의 텍스트, 이미지, 도형 또는 기타 시각적 콘텐츠가 포함될 수 있습니다.  도구 설명 콘텐츠에 다음 속성 중 하나를 설정하여 컨트롤의 도구 설명을 정의할 수 있습니다.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>  
  
 도구 설명을 정의하는 컨트롤이 <xref:System.Windows.FrameworkContentElement> 또는 <xref:System.Windows.FrameworkElement> 중 어떤 클래스에서 상속되는지에 따라 사용하는 속성이 달라집니다.  
  
<a name="create_tooltip"></a>   
## 도구 설명 만들기  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤의 <xref:System.Windows.FrameworkElement.ToolTip%2A> 속성을 텍스트 문자열로 설정하여 간단한 도구 설명을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 도구 설명을 <xref:System.Windows.Controls.ToolTip> 개체로 정의할 수도 있습니다.  다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Controls.ToolTip> 개체를 <xref:System.Windows.Controls.TextBox> 요소의 도구 설명으로 지정합니다.  예제에서는 <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName> 속성을 설정하여 <xref:System.Windows.Controls.ToolTip>을 지정합니다.  
  
 [!code-xml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.ToolTip> 개체를 생성합니다.  예제에서는 <xref:System.Windows.Controls.ToolTip>\(`tt`\)을 만들어 <xref:System.Windows.Controls.Button>에 연결합니다.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 <xref:System.Windows.Controls.DockPanel>과 같은 레이아웃 요소 안에 도구 설명 콘텐츠를 포함하는 방법을 통해 <xref:System.Windows.Controls.ToolTip> 개체로 정의되지 않은 도구 설명 콘텐츠를 만들 수도 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.FrameworkElement.ToolTip%2A> 속성을 <xref:System.Windows.Controls.DockPanel> 컨트롤에 포함된 콘텐츠로 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## ToolTip 및 ToolTipService 클래스의 속성 사용  
 시각적 속성을 설정하고 스타일을 적용하여 도구 설명 콘텐츠를 사용자 지정할 수 있습니다.  도구 설명 콘텐츠를 <xref:System.Windows.Controls.ToolTip> 개체로 정의하는 경우에는 <xref:System.Windows.Controls.ToolTip> 개체의 시각적 속성을 설정할 수 있습니다.  그렇지 않은 경우에는 <xref:System.Windows.Controls.ToolTipService> 클래스에 동일한 [연결된 속성](GTMT)을 설정해야 합니다.  
  
 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 속성을 사용하여 도구 설명 콘텐츠의 위치를 지정하기 위해 속성을 설정하는 방법에 대한 예제는 [도구 설명 배치](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md)를 참조하십시오.  
  
<a name="StylingToolTip"></a>   
## 도구 설명에 스타일 적용  
 사용자 지정 <xref:System.Windows.Style>을 정의하여 <xref:System.Windows.Controls.ToolTip>에 스타일을 적용할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.ToolTip>의 배치를 오프셋하고, <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> 및 <xref:System.Windows.Controls.Control.FontWeight%2A>를 설정하여 모양을 변경하는 방법을 보여 주는 `Simple`이라는 <xref:System.Windows.Style>을 정의합니다.  
  
 [!code-xml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## ToolTipService의 시간 간격 속성 사용  
 <xref:System.Windows.Controls.ToolTipService> 클래스는 도구 설명 표시 시간을 설정하기 위한 속성인 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 및 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>을 제공합니다.  
  
 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 및 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> 속성을 사용하여 <xref:System.Windows.Controls.ToolTip>이 나타나기 전까지의 짧은 지연을 지정하고 <xref:System.Windows.Controls.ToolTip>이 표시되는 시간을 지정합니다.  자세한 내용은 [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/ko-kr/618e05ef-f2bf-4a53-a0f4-aacb49918bd7)을 참조하십시오.  
  
 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 속성은 마우스 포인터를 컨트롤 간에 빠르게 이동할 때 다른 컨트롤의 도구 설명을 초기 지연 없이 표시할 것인지 결정합니다.  <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 속성에 대한 자세한 내용은 [BetweenShowDelay 속성 사용](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md)을 참조하십시오.  
  
 다음 예제에서는 도구 설명에 이와 같은 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ToolTipService>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipEventArgs>   
 <xref:System.Windows.Controls.ToolTipEventHandler>   
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)