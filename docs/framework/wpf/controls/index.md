---
title: "컨트롤"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66c6cc58423a2af8d0fd6de93b8884918888fb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="controls"></a>컨트롤
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]많은 등 거의 모든 Windows 응용 프로그램에서 사용 되는 일반적인 UI 구성 요소와 함께 제공 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, 및 <xref:System.Windows.Controls.ListBox>합니다. 지금까지 이러한 개체는 컨트롤이라고 불렀습니다. 동안는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK가 응용 프로그램에서 표시 되는 개체를 나타내는 모든 클래스를 대략적으로 의미를 "제어" 라는 용어를 사용 하 여 계속 클래스에서 상속 필요는 없습니다 해야는 <xref:System.Windows.Controls.Control> 클래스를 시각적 존재 합니다. 클래스에서 상속 되는 <xref:System.Windows.Controls.Control> 클래스에 포함 될는 <xref:System.Windows.Controls.ControlTemplate>, 컨트롤의 소비자를 완전히 새 하위 클래스를 만들 필요 없이 컨트롤의 모양을 변경할 수 있습니다.  이 항목에서는 방법을 컨트롤 (두는 것에서 상속 않는 <xref:System.Windows.Controls.Control> 클래스와 그러지 않은)에서 일반적으로 사용 되 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>컨트롤의 인스턴스 만들기  
 하나를 사용 하 여 응용 프로그램에 컨트롤을 추가할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다.  다음 예제에서는 사용자에게 이름과 성을 묻는 간단한 응용 프로그램을 만드는 방법을 보여 줍니다.  이 예제에서는 6 개의 컨트롤을 만듭니다: 2 개의 레이블, 두 개의 텍스트 상자 및에 두 개의 단추 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 모든 컨트롤을 유사하게 만들 수 있습니다.  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 코드로 동일한 응용 프로그램을 만듭니다. 요약 하자면, 만들기는 <xref:System.Windows.Controls.Grid>, `grid1`, 샘플에서 제외 되었습니다. `grid1`동일한 행 및 열 정의는 앞에 표시 된 것과 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제입니다.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>컨트롤의 모양 변경  
 일반적으로 응용 프로그램의 모양과 느낌에 맞게 컨트롤의 모양을 변경합니다. 수행하려는 작업에 따라 다음 중 하나를 수행하여 컨트롤의 모양을 변경할 수 있습니다.  
  
-   컨트롤의 속성 값을 변경합니다.  
  
-   만들기는 <xref:System.Windows.Style> 컨트롤에 대 한 합니다.  
  
-   새 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한 합니다.  
  
### <a name="changing-a-controls-property-value"></a>컨트롤의 속성 값 변경  
 대부분의 컨트롤 같은 컨트롤 표시 방법을 변경할 수 있는 속성이 있는 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button>합니다. 두 값 속성을 설정할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드입니다. 다음 예에서는 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, 및 <xref:System.Windows.Controls.Control.FontWeight%2A> 속성에는 <xref:System.Windows.Controls.Button> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 다음 예제에서는 코드로 동일한 속성을 설정합니다.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>컨트롤에 대한 스타일 만들기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]컨트롤의 모양을 만들어 응용 프로그램에서 각 인스턴스에서 속성을 설정 하는 대신 전체적 지정 하는 기능을 제공 된 <xref:System.Windows.Style>합니다. 다음 예제에서는 한 <xref:System.Windows.Style> 각각에 적용 되는 <xref:System.Windows.Controls.Button> 응용 프로그램에 있습니다. <xref:System.Windows.Style>정의에 일반적으로 정의 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 에 <xref:System.Windows.ResourceDictionary>와 같은 <xref:System.Windows.FrameworkElement.Resources%2A> 의 속성은 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 스타일에 키 할당에 해당 키를 지정 하 여 특정 형식의 특정 컨트롤에 스타일을 적용할 수도 있습니다는 `Style` 컨트롤의 속성입니다.  스타일에 대 한 자세한 내용은 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
### <a name="creating-a-controltemplate"></a>ControlTemplate 만들기  
 A <xref:System.Windows.Style> 하면 한 번에 여러 컨트롤에서 속성을 설정할 수 있지만 모양 사용자 지정 하려는 경우에 따라 한 <xref:System.Windows.Controls.Control> 만들어 수행할 수 있는 초과 <xref:System.Windows.Style>합니다. 클래스에서 상속 되는 <xref:System.Windows.Controls.Control> 클래스는 <xref:System.Windows.Controls.ControlTemplate>, 구조와의 모양을 정의 하는 <xref:System.Windows.Controls.Control>합니다. <xref:System.Windows.Controls.Control.Template%2A> 속성은 <xref:System.Windows.Controls.Control> 는 지정할 수 있는 공용는 <xref:System.Windows.Controls.Control> 는 <xref:System.Windows.Controls.ControlTemplate> 기본값과 다른 합니다. 종종를 지정할 수 있습니다 새 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Control> 의 모양을 사용자 지정 하는 컨트롤에서 상속 하지 않고는 <xref:System.Windows.Controls.Control>합니다.  
  
 매우 일반적인 컨트롤이 <xref:System.Windows.Controls.Button>합니다.  기본 동작은 <xref:System.Windows.Controls.Button> 사용자가 특별 한 조치를 받는 응용 프로그램을 사용 하도록 설정 합니다.  기본적으로는 <xref:System.Windows.Controls.Button> 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 나타나는 사각형으로 나타납니다.  동작을 활용 하려는 응용 프로그램을 개발 하는 동안 한 <xref:System.Windows.Controls.Button>-즉, 단추의 클릭 이벤트를 처리 하 여 하지만 단추의 속성을 변경 하 여 수행할 수 있는 다음 단추의 모양을 변경 될 수 있습니다.  이 경우 새로 만들 수 있습니다는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>합니다.  <xref:System.Windows.Controls.ControlTemplate> 만듭니다는 <xref:System.Windows.Controls.Button> 둥근된 모서리과 그라데이션 배경이 합니다.  <xref:System.Windows.Controls.ControlTemplate> 포함 한 <xref:System.Windows.Controls.Border> 인 <xref:System.Windows.Controls.Border.Background%2A> 는 <xref:System.Windows.Media.LinearGradientBrush> 두 개의 <xref:System.Windows.Media.GradientStop> 개체입니다.  첫 번째 <xref:System.Windows.Media.GradientStop> 바인딩할 데이터 바인딩을 사용 하는 <xref:System.Windows.Media.GradientStop.Color%2A> 의 속성은 <xref:System.Windows.Media.GradientStop> 단추의 배경색을 합니다.  설정 하는 경우는 <xref:System.Windows.Controls.Control.Background%2A> 속성은 <xref:System.Windows.Controls.Button>, 해당 값의 색 처음으로 사용 될 <xref:System.Windows.Media.GradientStop>합니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요. 이 예에서는 또한 만듭니다는 <xref:System.Windows.Trigger> 의 모양을 변경 하는 <xref:System.Windows.Controls.Button> 때 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 은 `true`합니다.  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control.Background%2A> 의 속성은 <xref:System.Windows.Controls.Button> 로 설정 되어야 합니다는 <xref:System.Windows.Media.SolidColorBrush> 예제가 제대로 작동 하려면에 대 한 합니다.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>이벤트 구독  
 사용 하 여 컨트롤의 이벤트를 구독할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이나 있지만 코드를 코드의에서 이벤트를 처리할만 수 있습니다.  다음 예제에서는 구독 하는 방법을 보여 줍니다.는 `Click` 의 이벤트는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 다음 예제에서는 핸들의 `Click` 의 이벤트는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>컨트롤의 풍부한 콘텐츠  
 상속 하는 대부분의 클래스는 <xref:System.Windows.Controls.Control> 클래스를 다양 한 콘텐츠를 포함할 수 있어야 합니다. 예를 들어 한 <xref:System.Windows.Controls.Label> 문자열과 같은 모든 개체를 포함할 수 있습니다는 <xref:System.Windows.Controls.Image>, 또는 <xref:System.Windows.Controls.Panel>합니다.  다음 클래스는 풍부한 콘텐츠에 대 한 지원을 제공 하며 대부분의 컨트롤에 대 한 기본 클래스 역할로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
-   <xref:System.Windows.Controls.ContentControl>-이 클래스에서 상속 된 클래스의 예는 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Controls.ToolTip>합니다.  
  
-   <xref:System.Windows.Controls.ItemsControl>-이 클래스에서 상속 된 클래스의 예는 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, 및 <xref:System.Windows.Controls.Primitives.StatusBar>합니다.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>-이 클래스에서 상속 된 클래스의 예는 <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, 및 <xref:System.Windows.Controls.Expander>합니다.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>-이 클래스에서 상속 된 클래스의 예는 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, 및 <xref:System.Windows.Controls.ToolBar>합니다.  
  
-  
  
 이러한 기본 클래스에 대 한 자세한 내용은 참조 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [범주별 컨트롤](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [컨트롤 라이브러리](../../../../docs/framework/wpf/controls/control-library.md)  
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [입력](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [명령 사용](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [연습: 사용자 지정 애니메이션 단추 만들기](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)
