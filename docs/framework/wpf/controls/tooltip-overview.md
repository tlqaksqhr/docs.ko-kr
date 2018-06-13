---
title: 도구 설명 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: b70387e604b0917d154fc056b904e9ee05f6fbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557240"
---
# <a name="tooltip-overview"></a>도구 설명 개요
도구 설명 같은 요소를 위로 마우스 포인터를 놓을 때 표시 되는 작은 팝업 창인은는 <xref:System.Windows.Controls.Button>합니다. 이 항목에서는 도구 설명을 소개하고 도구 설명 콘텐츠를 만들고 사용자 지정하는 방법을 설명합니다.  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>도구 설명이란?  
 사용자가 마우스 포인터를 도구 설명이 있는 요소 위로 이동하면 도구 설명 콘텐츠(예: 컨트롤 함수를 설명하는 텍스트 콘텐츠)가 포함된 창이 지정된 시간 동안 표시됩니다. 사용자가 마우스 포인터를 컨트롤 외부로 이동하면 도구 설명 콘텐츠가 포커스를 받을 수 없기 때문에 창이 사라집니다.  
  
 도구 설명 콘텐츠에는 하나 이상의 텍스트 줄, 이미지, 도형 및 기타 시각적 콘텐츠가 포함될 수 있습니다. 컨트롤에 대한 도구 설명을 정의하려면 다음 속성 중 하나를 도구 설명 콘텐츠로 설정합니다.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 사용 되는 속성 정의 도구 설명 컨트롤에서 상속 되는 여부에 따라 달라 집니다는 <xref:System.Windows.FrameworkContentElement> 또는 <xref:System.Windows.FrameworkElement> 클래스입니다.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>ToolTip 만들기  
 다음 예제를 설정 하 여 간단한 도구 설명을 만드는 방법의 <xref:System.Windows.FrameworkElement.ToolTip%2A> 속성에 대 한는 <xref:System.Windows.Controls.Button> 컨트롤 텍스트 문자열을 합니다.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 도구 설명으로 정의할 수도 있습니다는 <xref:System.Windows.Controls.ToolTip> 개체입니다. 다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지정 하는 <xref:System.Windows.Controls.ToolTip> 의 도구 설명으로 개체는 <xref:System.Windows.Controls.TextBox> 요소입니다. 이 예제에서는 지정 된 <xref:System.Windows.Controls.ToolTip> 설정 하 여는 <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> 속성.  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 다음 예제에서는 코드를 사용 하 여 생성 하는 <xref:System.Windows.Controls.ToolTip> 개체입니다. 이 예에서는 만듭니다는 <xref:System.Windows.Controls.ToolTip> (`tt`)에 연결 된 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 로 정의 되지 않은 도구 설명 콘텐츠를 만들 수도 있습니다는 <xref:System.Windows.Controls.ToolTip> 와 같은 레이아웃 요소에 도구 설명 콘텐츠를 포함 하 여 개체는 <xref:System.Windows.Controls.DockPanel>합니다. 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.FrameworkElement.ToolTip%2A> 속성의는 <xref:System.Windows.Controls.TextBox> 에 포함 된 내용에는 <xref:System.Windows.Controls.DockPanel> 제어 합니다.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>ToolTip 및 ToolTipService 클래스의 속성 사용  
 시각적 속성을 설정하고 스타일을 적용하여 도구 설명 콘텐츠를 사용자 지정할 수 있습니다. 도구 설명으로 콘텐츠를 정의 하는 경우는 <xref:System.Windows.Controls.ToolTip> 개체의 시각적 속성을 설정할 수 있습니다는 <xref:System.Windows.Controls.ToolTip> 개체입니다. 에 해당 하는 연결 된 속성을 설정 해야 그렇지 않은 경우는 <xref:System.Windows.Controls.ToolTipService> 클래스입니다.  
  
 사용 하 여 도구 설명 콘텐츠의 위치를 지정 하기 위해 속성을 설정 하는 방법의 예는 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 속성 참조 [도구 설명 배치](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md)합니다.  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>ToolTip 스타일 지정  
 스타일을 지정할 수 있습니다는 <xref:System.Windows.Controls.ToolTip> 사용자 지정을 정의 하 여 <xref:System.Windows.Style>합니다. 다음 예제에서는 정의 <xref:System.Windows.Style> 호출 `Simple` 시간의 오프셋 하는 방법을 보여 주는 <xref:System.Windows.Controls.ToolTip> 설정 하 여 모양을 변경 하 고는 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, 및 <xref:System.Windows.Controls.Control.FontWeight%2A>합니다.  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>ToolTipService의 시간 간격 속성 사용  
 <xref:System.Windows.Controls.ToolTipService> 클래스는 시간을 표시 하는 도구 설명을 설정할 수 있습니다에 대 한 다음 속성을 제공: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, 및 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>합니다.  
  
 사용 하 여는 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 및 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> 지연 시간을 지정 하려면 속성 짧은 전에 <xref:System.Windows.Controls.ToolTip> 표시 시간을 지정 하 고는 <xref:System.Windows.Controls.ToolTip> 계속 표시 됩니다. 자세한 내용은 [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/library/618e05ef-f2bf-4a53-a0f4-aacb49918bd7)(방법: ToolTip 표시 지연)을 참조하세요.  
  
 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 속성 마우스 포인터를 빠르게 이동 하면 서로 다른 컨트롤에 대 한 도구 설명 초기 지연 없이 표시할지 여부를 결정 합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 속성 참조 [BetweenShowDelay 속성을 사용 하 여](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md)합니다.  
  
 다음 예제에서는 도구 설명에 대한 이러한 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
