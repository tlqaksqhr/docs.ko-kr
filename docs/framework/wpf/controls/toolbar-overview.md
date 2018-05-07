---
title: ToolBar 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 0c66867ce4d86a11424d7a7a859817d603b4227e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="toolbar-overview"></a>ToolBar 개요
<xref:System.Windows.Controls.ToolBar> 컨트롤은 명령 또는 해당 함수에서 일반적으로 관련이 있는 컨트롤의 그룹에 대 한 컨테이너입니다. A <xref:System.Windows.Controls.ToolBar> 일반적으로 명령을 호출 하는 단추가 포함 되어 있습니다.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar 컨트롤  
 <xref:System.Windows.Controls.ToolBar> 컨트롤 단일 행 이나 열으로 단추 또는 다른 컨트롤의 막대와 비슷한 배열에서 해당 이름을 사용 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤 크기 제한 내에 맞지 않는 모든 항목을 배치 하는 오버플로 메커니즘을 제공 <xref:System.Windows.Controls.ToolBar> 특별 한 넘침 영역에 있습니다. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 사용 하는 관련 된 <xref:System.Windows.Controls.ToolBarTray> 크기 조정 및 컨트롤과 사용자가 시작한 위한 지원 뿐 아니라 특별 한 레이아웃 동작을 제공 하는 컨트롤입니다.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>ToolBarTray에서 ToolBar 위치 지정  
 사용 하 여는 <xref:System.Windows.Controls.ToolBar.Band%2A> 및 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 의 위치를 지정할 속성은 <xref:System.Windows.Controls.ToolBar> 에 <xref:System.Windows.Controls.ToolBarTray>합니다. <xref:System.Windows.Controls.ToolBar.Band%2A> 위치를 나타냅니다는 <xref:System.Windows.Controls.ToolBar> 해당 부모 노드에 배치 <xref:System.Windows.Controls.ToolBarTray>합니다. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 순서를 나타냅니다는 <xref:System.Windows.Controls.ToolBar> 해당 대역 내에 배치 됩니다. 다음 예제에서는 배치 하려면이 속성을 사용 방법 <xref:System.Windows.Controls.ToolBar> 컨트롤 내부의 <xref:System.Windows.Controls.ToolBarTray>합니다.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>오버플로 항목이 있는 ToolBar  
 종종 <xref:System.Windows.Controls.ToolBar> 컨트롤에 도구 모음의 크기에 맞출 수 있는 것 보다 많은 항목이 포함 되어 있습니다. 이런 경우는 <xref:System.Windows.Controls.ToolBar> 오버플로 단추를 표시 합니다. 오버플로 항목을 확인 하려면 사용자는 오버플로 단추를 클릭 하 고 항목 아래의 팝업 창에 표시 됩니다는 <xref:System.Windows.Controls.ToolBar>합니다. 다음 그래픽에 표시 된는 <xref:System.Windows.Controls.ToolBar> 오버플로 항목입니다.  
  
 ![오버플로 도구 모음](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
오버플로 항목이 있는 도구 모음  
  
 설정 하 여 도구 모음에 있는 항목 오버플로 패널에 배치 하면 지정할 수는 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> 연결 된 속성을 <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, 또는 <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>합니다. 다음 예제에서는 도구 모음에 있는 마지막 네 개의 단추가 오버플로 패널에 항상 표시되도록 지정합니다.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> 사용 하 여 한 <xref:System.Windows.Controls.Primitives.ToolBarPanel> 및 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 에 해당 <xref:System.Windows.Controls.ControlTemplate>합니다.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> 도구 모음에서 항목의 레이아웃을 담당 합니다.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 에 맞지 않는 항목의 레이아웃에 대 한 책임이 <xref:System.Windows.Controls.ToolBar>합니다. 에 대 한 예제는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ToolBar>, 참조  
  
 [ToolBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [ToolBar 컨트롤의 스타일 지정](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)(WPF 컨트롤 갤러리 샘플)
