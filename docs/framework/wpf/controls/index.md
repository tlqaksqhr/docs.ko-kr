---
title: "컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7652a2e64cdc107546ac3ea51178a3542606bd43
ms.contentlocale: ko-kr
ms.lasthandoff: 06/08/2017

---
# <a name="controls"></a>컨트롤
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에는              <xref:System.Windows.Controls.Button>,              <xref:System.Windows.Controls.Label>,              <xref:System.Windows.Controls.TextBox>,              <xref:System.Windows.Controls.Menu>,              <xref:System.Windows.Controls.ListBox> 등 거의 모든 Windows 응용 프로그램에서 사용되는 대부분의 공통 UI 구성 요소가 포함되어 있습니다. 지금까지 이러한 개체는 컨트롤이라고 불렀습니다.              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK에서는 계속해서 "컨트롤"이라는 용어를 사용하여 응용 프로그램에 표시되는 개체를 나타내는 모든 클래스를 대략적으로 지칭합니다. 그러나 클래스가 반드시               <xref:System.Windows.Controls.Control> 클래스에서 상속을 받아야 표시되는 것은 아닙니다.              <xref:System.Windows.Controls.Control> 클래스에서 상속을 받는 클래스에는               <xref:System.Windows.Controls.ControlTemplate>이 포함되어 있습니다. 따라서 컨트롤 소비자는 새 하위 클래스를 만들지 않아도 컨트롤의 모양을 대폭 변경할 수 있습니다.  이 항목에서는 컨트롤(              <xref:System.Windows.Controls.Control> 클래스에서 상속받는 컨트롤과 상속받지 않는 컨트롤)이              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 일반적으로 사용되는 방법에 대해 설명합니다.  
  
 
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>컨트롤의 인스턴스 만들기  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드를 사용하여 응용 프로그램에 컨트롤을 추가할 수 있습니다.  다음 예제에서는 사용자에게 이름과 성을 묻는 간단한 응용 프로그램을 만드는 방법을 보여 줍니다.  이 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 6개의 컨트롤, 즉 2개의 레이블, 2개의 텍스트 상자 및 2개의 단추를 만듭니다. 모든 컨트롤을 유사하게 만들 수 있습니다.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 코드로 동일한 응용 프로그램을 만듭니다. 간략한 설명을 위해 <xref:System.Windows.Controls.Grid>(`grid1`)를                  만드는 과정은 샘플에서 제외되었습니다.                   `grid1`은 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일한 열과 행의 정의를 사용합니다.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)] [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>컨트롤의 모양 변경  
 일반적으로 응용 프로그램의 모양과 느낌에 맞게 컨트롤의 모양을 변경합니다. 수행하려는 작업에 따라 다음 중 하나를 수행하여 컨트롤의 모양을 변경할 수 있습니다.  
  
-   컨트롤의 속성 값을 변경합니다.  
  
-   컨트롤의                          <xref:System.Windows.Style>을 만듭니다.  
  
-   컨트롤의 새                          <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.  
  
### <a name="changing-a-controls-property-value"></a>컨트롤의 속성 값 변경  
 대부분의 컨트롤에는                          <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>와 같이 컨트롤이 표시되는 방식을 변경할 수 있는 속성이 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드 둘 다에서 값 속성을 설정할 수 있습니다. 다음 예제의 경우                           [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서                          <xref:System.Windows.Controls.Button>의                          <xref:System.Windows.Controls.Control.Background%2A>,                          <xref:System.Windows.Controls.Control.FontSize%2A> 및                          <xref:System.Windows.Controls.Control.FontWeight%2A> 속성을 설정합니다.  
  
 [!code-xml[ControlsOverview # 3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 다음 예제에서는 코드로 동일한 속성을 설정합니다.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)] [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>컨트롤에 대한 스타일 만들기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 응용 프로그램의 각 인스턴스에 대한 속성을 설정하는 대신                          <xref:System.Windows.Style>을 만들어 여러 컨트롤의 모양을 대량으로 지정할 수 있습니다.                           다음 예제에서는                          응용 프로그램의 각                          <xref:System.Windows.Controls.Button>에 적용되는                          <xref:System.Windows.Style>을 만듭니다.                          <xref:System.Windows.Style> 정의는 대개                          [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서                          <xref:System.Windows.FrameworkElement>의                           <xref:System.Windows.FrameworkElement.Resources%2A> 속성과 같은 <xref:System.Windows.ResourceDictionary>에 정의합니다.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 스타일에 키를 할당하고 컨트롤의 `Style` 속성에서 해당 키를 지정하여 특정 형식의 특정 컨트롤에만 스타일을 적용할 수도 있습니다.  스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하세요.  
  
### <a name="creating-a-controltemplate"></a>ControlTemplate 만들기  
                          <xref:System.Windows.Style>을 사용하면 한 번에 여러 컨트롤의 속성을 설정할 수 있지만 때로는                          <xref:System.Windows.Style>을 만들어서 수행할 수 있는 것 이상으로                          <xref:System.Windows.Controls.Control>의 모양을 사용자 지정하고 싶을 수도 있습니다.                          <xref:System.Windows.Controls.Control> 클래스에서 상속을 받는 클래스에는                          <xref:System.Windows.Controls.Control>의 모양과 구조를 정의하는                           <xref:System.Windows.Controls.ControlTemplate>이 있습니다.                          <xref:System.Windows.Controls.Control>의                          <xref:System.Windows.Controls.Control.Template%2A> 속성은 public이므로                          <xref:System.Windows.Controls.Control>에 기본값과 다른                          <xref:System.Windows.Controls.ControlTemplate>을 지정할 수 있습니다.                          <xref:System.Windows.Controls.Control>의 모양을 사용자 지정하기 위해 특정 컨트롤에서 상속을 받는 대신                          <xref:System.Windows.Controls.Control>에 새                          <xref:System.Windows.Controls.ControlTemplate>을 지정할 수 있는 경우가 많습니다.  
  
 매우 흔히 사용되는 컨트롤인                          <xref:System.Windows.Controls.Button>의 경우를 예로 들어 보겠습니다.                           <xref:System.Windows.Controls.Button>의 기본 동작은 사용자가 클릭할 때 응용 프로그램이 특정 작업을 수행할 수 있게 하는 것입니다.  기본적으로                           [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서                          <xref:System.Windows.Controls.Button>은 볼록한 사각형으로 표시됩니다.  응용 프로그램을 개발하면서 단추의 클릭 이벤트를 처리하여                          <xref:System.Windows.Controls.Button>의 동작을 활용할 수도 있지만, 단추 속성을 변경하여 수행할 수 있는 것 이상으로 단추의 모양을 변경하는 경우도 있습니다.  이러한 경우 새                          <xref:System.Windows.Controls.ControlTemplate>을 만들 수 있습니다.  
  
 다음 예제에서는                          <xref:System.Windows.Controls.Button>에 대해                          <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.                           <xref:System.Windows.Controls.ControlTemplate>은 모서리가 둥글고 배경이 그라데이션 처리된                          <xref:System.Windows.Controls.Button>를 만듭니다.                           <xref:System.Windows.Controls.ControlTemplate>에 포함되어 있는                          <xref:System.Windows.Controls.Border>의                          <xref:System.Windows.Controls.Border.Background%2A>는                          <xref:System.Windows.Media.GradientStop> 개체 두 개가 들어 있는                          <xref:System.Windows.Media.LinearGradientBrush>입니다.  첫 번째                          <xref:System.Windows.Media.GradientStop>은 데이터 바인딩을 사용하여                          <xref:System.Windows.Media.GradientStop>의                          <xref:System.Windows.Media.GradientStop.Color%2A> 속성을 단추 배경의 색에 바인딩합니다.                           <xref:System.Windows.Controls.Button>의                          <xref:System.Windows.Controls.Control.Background%2A> 속성을 설정할 때는 해당 값의 색이 첫 번째                          <xref:System.Windows.Media.GradientStop>으로 사용됩니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요. 이 예제에서는                          <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>가                          `true`일 때                          <xref:System.Windows.Controls.Button>의 모양을 변경하는                           <xref:System.Windows.Trigger>도 만듭니다.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>                               <xref:System.Windows.Controls.Button>의                              <xref:System.Windows.Controls.Control.Background%2A> 속성을                               <xref:System.Windows.Media.SolidColorBrush>로 설정해야 예제가 정상적으로 작동합니다.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>이벤트 구독  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드를 사용하여 컨트롤의 이벤트를 구독할 수 있지만 코드로만 이벤트를 처리할 수 있습니다.  다음 예제에서는                  <xref:System.Windows.Controls.Button>의                   `Click` 이벤트를 구독하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)] [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 다음 예제에서는                  <xref:System.Windows.Controls.Button>의                   `Click` 이벤트를 처리합니다.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)] [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>컨트롤의 풍부한 콘텐츠  
                  <xref:System.Windows.Controls.Control> 클래스에서 상속받는 대부분의 클래스는 서식 있는 콘텐츠를 포함할 수 있습니다. 예를 들어                  <xref:System.Windows.Controls.Label>은 문자열,                  <xref:System.Windows.Controls.Image> 또는                  <xref:System.Windows.Controls.Panel>과 같은 개체를 포함할 수 있습니다.  다음 클래스는 풍부한 콘텐츠를 지원하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 대부분의 컨트롤에 대한 기본 클래스로 작동합니다.  
  
-   <xref:System.Windows.Controls.ContentControl> - 이 클래스에서 상속받는 클래스의 예로는                          <xref:System.Windows.Controls.Label>,                          <xref:System.Windows.Controls.Button>,                           <xref:System.Windows.Controls.ToolTip> 등이 있습니다.  
  
-   <xref:System.Windows.Controls.ItemsControl> - 이 클래스에서 상속받는 클래스의 예로는                          <xref:System.Windows.Controls.ListBox>,                          <xref:System.Windows.Controls.Menu>,                           <xref:System.Windows.Controls.Primitives.StatusBar> 등이 있습니다.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl> - 이 클래스에서 상속받는 클래스의 예로는                          <xref:System.Windows.Controls.TabItem>,                          <xref:System.Windows.Controls.GroupBox>,                           <xref:System.Windows.Controls.Expander> 등이 있습니다.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl> - 이 클래스에서 상속받는 클래스의 예로는                          <xref:System.Windows.Controls.MenuItem>,                          <xref:System.Windows.Controls.TreeViewItem>,                           <xref:System.Windows.Controls.ToolBar> 등이 있습니다.  
  
-  
  
 이러한 기본 클래스에 대한 자세한 내용은 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [컨트롤 범주](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [컨트롤 라이브러리](../../../../docs/framework/wpf/controls/control-library.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [입력](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [명령 사용](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [연습: 사용자 지정 애니메이션 단추 만들기](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)
