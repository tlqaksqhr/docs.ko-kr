---
title: "Expander 개요 | Microsoft Docs"
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
  - "컨트롤, Expander"
  - "Expander 컨트롤, Expander 컨트롤 정보"
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Expander 개요
<xref:System.Windows.Controls.Expander> 컨트롤은 창과 비슷하며 헤더를 포함하는 확장 가능한 영역에 콘텐츠를 제공하는 방법을 제공합니다.  
  
   
  
<a name="CreatinganExpanderinXAML"></a>   
## 간단한 Expander 만들기  
 다음 예제에서는 간단한 <xref:System.Windows.Controls.Expander> 컨트롤을 만드는 방법을 보여 줍니다.  이 예제에서는 앞의 그림과 비슷하게 보이는 <xref:System.Windows.Controls.Expander>를 만듭니다.  
  
 [!code-xml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.Expander>의 <xref:System.Windows.Controls.ContentControl.Content%2A> 및 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>는 <xref:System.Windows.Controls.RadioButton> 및 <xref:System.Windows.Controls.Image> 개체 같은 복합 콘텐츠를 포함할 수도 있습니다.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## 콘텐츠 영역의 확장 방향 설정  
 <xref:System.Windows.Controls.ExpandDirection> 속성을 사용하면 <xref:System.Windows.Controls.Expander> 컨트롤의 콘텐츠 영역을 네 가지 방향\(<xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection> 또는 <xref:System.Windows.Controls.ExpandDirection>\) 중 하나로 확장되도록 설정할 수 있습니다.  이러한 콘텐츠 영역을 축소하면 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 해당 토글 단추만 나타납니다.  방향 화살표를 표시하는 <xref:System.Windows.Controls.Button> 컨트롤이 콘텐츠 영역을 확장하거나 축소하는 토글 단추로 사용됩니다.  확장할 경우 <xref:System.Windows.Controls.Expander>에서 창과 유사한 영역에 모든 콘텐츠를 표시합니다.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## 패널에 있는 Expander의 크기 제어  
 <xref:System.Windows.Controls.Expander> 컨트롤이 <xref:System.Windows.Controls.Panel>에서 상속한 <xref:System.Windows.Controls.StackPanel> 같은 레이아웃 컨트롤 내부에 있는 경우 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성이 <xref:System.Windows.Controls.ExpandDirection> 또는 <xref:System.Windows.Controls.ExpandDirection>으로 설정되어 있으면 <xref:System.Windows.Controls.Expander>에 대해 <xref:System.Windows.FrameworkElement.Height%2A>를 지정하지 마십시오.  마찬가지로 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성이 <xref:System.Windows.Controls.ExpandDirection> 또는 <xref:System.Windows.Controls.ExpandDirection>로 설정되어 있으면 <xref:System.Windows.Controls.Expander>에 대해 <xref:System.Windows.FrameworkElement.Width%2A>를 지정하지 마십시오.  
  
 확장된 콘텐츠가 표시되는 방향으로 <xref:System.Windows.Controls.Expander> 컨트롤의 크기를 설정하면 <xref:System.Windows.Controls.Expander>가 콘텐츠에 사용되는 영역을 제어하고 그 주위에 테두리를 표시합니다.  이 테두리는 콘텐츠를 축소한 경우에도 표시됩니다.  확장된 콘텐츠 영역의 크기를 설정하려면 <xref:System.Windows.Controls.Expander>의 콘텐츠에 대한 크기를 설정하거나 스크롤 기능이 필요한 경우에는 콘텐츠를 둘러싸고 있는 <xref:System.Windows.Controls.ScrollViewer>에 대한 크기를 설정합니다.  
  
 <xref:System.Windows.Controls.Expander> 컨트롤이 <xref:System.Windows.Controls.DockPanel>의 마지막 요소인 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 자동으로 <xref:System.Windows.Controls.Expander> 크기를 <xref:System.Windows.Controls.DockPanel>의 남은 영역과 동일하게 설정합니다.  이 기본 동작이 수행되지 않게 하려면 <xref:System.Windows.Controls.DockPanel> 개체에 대한 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 속성을 `false`로 설정하거나 <xref:System.Windows.Controls.Expander>가 <xref:System.Windows.Controls.DockPanel>의 마지막 요소가 되지 않게 합니다.  
  
<a name="CreatingScrollableContent"></a>   
## 스크롤할 수 있는 콘텐츠 만들기  
 콘텐츠가 콘텐츠 영역 크기보다 큰 경우 <xref:System.Windows.Controls.Expander>의 콘텐츠를 <xref:System.Windows.Controls.ScrollViewer>에 래핑하여 스크롤할 수 있는 콘텐츠를 제공할 수 있습니다.  <xref:System.Windows.Controls.Expander> 컨트롤이 스크롤 기능을 자동으로 제공하는 것은 아닙니다.  다음 그림에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤을 포함하는 <xref:System.Windows.Controls.Expander> 컨트롤을 보여 줍니다.  
  
 **ScrollViewer에 포함된 Expander**  
  
 ![스크롤 막대가 있는 확장기](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 <xref:System.Windows.Controls.ScrollViewer> 내부에 <xref:System.Windows.Controls.Expander> 컨트롤을 배치하는 경우 <xref:System.Windows.Controls.Expander> 콘텐츠가 열리는 방향에 해당하는 <xref:System.Windows.Controls.ScrollViewer> 크기 속성을 <xref:System.Windows.Controls.Expander> 콘텐츠 영역의 크기로 설정합니다.  예를 들어 <xref:System.Windows.Controls.Expander>의 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성을 <xref:System.Windows.Controls.ExpandDirection>으로 설정한 경우, 즉 콘텐츠 영역이 아래쪽으로 열리는 경우 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 콘텐츠 영역에 필요한 높이로 설정합니다.  그렇지 않고 콘텐츠 자체의 높이로 설정하면 <xref:System.Windows.Controls.ScrollViewer>가 이 설정을 인식하지 못하므로 스크롤할 수 있는 콘텐츠를 제공하지 않습니다.  
  
 다음 예제에서는 복합 콘텐츠가 있으며 <xref:System.Windows.Controls.ScrollViewer> 컨트롤을 포함하는 <xref:System.Windows.Controls.Expander> 컨트롤을 만드는 방법을 보여 줍니다.  이 예제에서는 이 단원의 시작 부분에 있는 그림과 비슷한 <xref:System.Windows.Controls.Expander>를 만듭니다.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## 맞춤 속성 사용  
 <xref:System.Windows.Controls.Expander> 컨트롤에 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성을 설정하여 콘텐츠를 정렬할 수 있습니다.  이러한 속성을 설정할 경우 맞춤은 헤더와 확장된 콘텐츠 모두에 적용됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Expander>   
 <xref:System.Windows.Controls.ExpandDirection>   
 [방법 항목](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)