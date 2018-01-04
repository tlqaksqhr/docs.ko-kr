---
title: "Expander 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f0623ed4c84247cc1759a203e3b95dd895cee2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="expander-overview"></a>Expander 개요
<xref:System.Windows.Controls.Expander> 컨트롤은 창을 유사한 헤더를 포함 하는 확장 가능한 영역에 콘텐츠를 제공 하는 방법을 제공 합니다.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>단순 확장기 만들기  
 다음 예제에는 간단한을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.Expander> 제어 합니다. 이 예제에서는 만듭니다는 <xref:System.Windows.Controls.Expander> 앞의 그림과 같은 형식입니다.  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> 및 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 의 <xref:System.Windows.Controls.Expander> 와 같은 복잡 한 콘텐츠를 포함할 수도 있습니다 <xref:System.Windows.Controls.RadioButton> 및 <xref:System.Windows.Controls.Image> 개체입니다.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>확장되는 콘텐츠 영역의 방향 설정  
 콘텐츠 영역을 설정할 수 있습니다는 <xref:System.Windows.Controls.Expander> 네 방향을 중 하나에서 확장 하는 컨트롤 (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, 또는 <xref:System.Windows.Controls.ExpandDirection.Right>)를 사용 하 여는 <xref:System.Windows.Controls.ExpandDirection> 속성입니다. 때 콘텐츠 영역을 축소는 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 해당 토글 단추가 나타납니다. A <xref:System.Windows.Controls.Button> 방향 화살표를 표시 하는 컨트롤을 확장 하거나 콘텐츠 영역을 축소 토글 단추도 사용 됩니다. 확장 하면는 <xref:System.Windows.Controls.Expander> 창과 같은 영역에서 모든 콘텐츠를 표시 하려고 합니다.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>패널에서 확장기의 크기 제어  
 경우는 <xref:System.Windows.Controls.Expander> 에서 상속 되는 레이아웃 컨트롤 내부 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.StackPanel>를 지정 하지 않으면는 <xref:System.Windows.FrameworkElement.Height%2A> 에 <xref:System.Windows.Controls.Expander> 때는 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성이로 설정 되어 <xref:System.Windows.Controls.ExpandDirection.Down> 또는 <xref:System.Windows.Controls.ExpandDirection.Up>합니다. 마찬가지로, 지정 하지 않으면는 <xref:System.Windows.FrameworkElement.Width%2A> 에 <xref:System.Windows.Controls.Expander> 때는 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성이 <xref:System.Windows.Controls.ExpandDirection.Left> 또는 <xref:System.Windows.Controls.ExpandDirection.Right>합니다.  
  
 크기를 설정 하면는 <xref:System.Windows.Controls.Expander> 확장 된 콘텐츠가 표시 되도록 방향에서 컨트롤의 <xref:System.Windows.Controls.Expander> 내용에 따라 사용 되 고 그 주위에 테두리를 표시 하는 영역을 제어 합니다. 콘텐츠를 축소해도 테두리가 표시됩니다. 확장 된 콘텐츠 영역의 크기를 설정 하려면의 콘텐츠에 대 한 크기를 설정 된 <xref:System.Windows.Controls.Expander>에 스크롤 기능을 원하는 경우 또는 <xref:System.Windows.Controls.ScrollViewer> 콘텐츠를 포함 하 합니다.  
  
 때는 <xref:System.Windows.Controls.Expander> 컨트롤은에서 마지막 요소는 <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 를 자동으로 설정 된 <xref:System.Windows.Controls.Expander> 를 나머지 공간을 같은 차원은 <xref:System.Windows.Controls.DockPanel>합니다. 이 기본 동작을 방지 하려면 설정는 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 속성에는 <xref:System.Windows.Controls.DockPanel> 개체를 `false`, 있는지 확인 하거나는 <xref:System.Windows.Controls.Expander> 않습니다에서 마지막 요소는 <xref:System.Windows.Controls.DockPanel>합니다.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>스크롤 가능한 콘텐츠 만들기  
 콘텐츠가 콘텐츠 영역 크기에 비해 너무 큰 경우의 콘텐츠를 래핑할 수 있습니다는 <xref:System.Windows.Controls.Expander> 에 <xref:System.Windows.Controls.ScrollViewer> 스크롤 가능한 콘텐츠가 제공 하기 위해. <xref:System.Windows.Controls.Expander> 컨트롤이 자동으로 스크롤 기능을 제공 하지 않습니다. 다음 그림에서는 <xref:System.Windows.Controls.Expander> 제어를 포함 하는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.  
  
 **ScrollViewer의 확장기**  
  
 ![ScrollBar가 있는 확장기](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 배치 하는 경우는 <xref:System.Windows.Controls.Expander> 컨트롤에 <xref:System.Windows.Controls.ScrollViewer>설정는 <xref:System.Windows.Controls.ScrollViewer> 차원 방향을에 해당 하는 속성의 <xref:System.Windows.Controls.Expander> 콘텐츠 크기에 열립니다는 <xref:System.Windows.Controls.Expander> 콘텐츠 영역의 합니다. 예를 들어, 설정 하는 경우는 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성에는 <xref:System.Windows.Controls.Expander> 를 <xref:System.Windows.Controls.ExpandDirection.Down> (콘텐츠 영역 아래로 열림), 설정는 <xref:System.Windows.FrameworkElement.Height%2A> 속성에는 <xref:System.Windows.Controls.ScrollViewer> 필요한 높이로 콘텐츠 영역에 대 한 제어 합니다. 대신 높이 차원 콘텐츠 자체에 설정 하는 경우 <xref:System.Windows.Controls.ScrollViewer> 이 설정을 인식 하지 못하고 따라서 스크롤 가능한 콘텐츠를 제공 하지 않습니다.  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Expander> 컨트롤 복잡 한 콘텐츠를 보유 하 고 포함 하는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다. 이 예제에서는 만듭니다는 <xref:System.Windows.Controls.Expander> 는이 섹션의 시작 부분에 그림과 같습니다.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>맞춤 속성 사용  
 설정 하 여 콘텐츠를 정렬할 수는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성에는 <xref:System.Windows.Controls.Expander> 제어 합니다. 이러한 속성을 설정하면 맞춤이 헤더뿐만 아니라 확장된 콘텐츠에도 적용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [방법 항목](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
