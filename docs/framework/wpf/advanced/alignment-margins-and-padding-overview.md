---
title: "맞춤, 여백 및 안쪽 여백 개요 | Microsoft Docs"
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
  - "맞추기"
  - "클래스, FrameworkElement"
  - "FrameworkElement 클래스"
  - "여백"
  - "안쪽 여백"
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 맞춤, 여백 및 안쪽 여백 개요
<xref:System.Windows.FrameworkElement> 클래스는 자식 요소의 위치를 정확하게 지정하는 데 사용되는 여러 속성을 노출합니다.  이 항목에서는 가장 중요한 네 가지 속성인 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>에 대해 설명합니다.  이러한 속성은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 요소의 위치를 제어하는 기본적인 방법을 제공하므로 이러한 속성이 미치는 효과를 이해해야 합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## 요소 위치 지정 소개  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 요소 위치를 지정하는 방법은 여러 가지가 있습니다.  하지만 이상적인 레이아웃을 얻으려면 올바른 <xref:System.Windows.Controls.Panel> 요소를 선택하는 것만으로는 부족합니다.  컨트롤 위치를 정밀하게 지정하려면 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 이해해야 합니다.  
  
 다음 그림에서는 몇 가지 위치 지정 속성을 사용하는 레이아웃 시나리오를 보여 줍니다.  
  
 ![WPF 위치 지정 속성 샘플](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.png "layout\_margins\_padding\_alignment\_graphic1")  
  
 얼핏 보기에는 이 그림에서 <xref:System.Windows.Controls.Button> 요소가 임의로 위치가 지정되는 것으로 보이지만,  실제로는 여백, 맞춤 및 안쪽 여백을 조합하여 사용하여 해당 위치가 정밀하게 제어된 것입니다.  
  
 다음 예제에서는 위 그림의 레이아웃을 만드는 방법에 대해 설명합니다.  <xref:System.Windows.Controls.Border> 요소는 <xref:System.Windows.Controls.Border.Padding%2A> 값을 15 [장치 독립적 픽셀](GTMT)로 하여 부모 <xref:System.Windows.Controls.StackPanel>을 캡슐화합니다.  이것은 자식 <xref:System.Windows.Controls.StackPanel>을 둘러싸는 좁은 <xref:System.Windows.Media.Brushes.LightBlue%2A> 밴드를 고려한 것입니다.  이 항목에서 자세히 설명하는 다양한 위치 지정 속성 각각을 설명하기 위해 <xref:System.Windows.Controls.StackPanel>의 자식 요소를 사용합니다.  또한 <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 모두를 설명하기 위해 <xref:System.Windows.Controls.Button> 요소 세 개를 사용합니다.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 다음 다이어그램에서는 위 샘플에 사용된 다양한 위치 지정 속성을 자세히 보여 줍니다.  이 항목의 이후 단원에서는 각 위치 지정 속성을 사용하는 방법에 대해 자세히 설명합니다.  
  
 ![화면 호출을 사용하는 위치 지정 속성](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.png "layout\_margins\_padding\_alignment\_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## 맞춤 속성 이해  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성은 부모 요소의 할당된 레이아웃 공간 내에서 자식 요소의 위치가 어떻게 지정되어야 하는지를 설명합니다.  이러한 속성을 함께 사용하면 자식 요소 위치를 정확하게 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DockPanel>의 자식 요소에서 <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment> 또는 사용 가능한 공간을 채우는 <xref:System.Windows.HorizontalAlignment>의 네 가지 가로 맞춤 속성을 지정할 수 있습니다.  세로 위치 지정에도 유사한 값을 사용할 수 있습니다.  
  
> [!NOTE]
>  요소에서 명시적으로 설정된 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성은 <xref:System.Windows.HorizontalAlignment> 속성 값보다 우선합니다.  <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값을 `Stretch`로 설정하려고 하면 `Stretch` 요청이 무시됩니다.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### HorizontalAlignment 속성  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성은 자식 요소에 적용할 가로 맞춤 특성을 선언합니다.  다음 표에서는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성에 사용할 수 있는 값을 보여 줍니다.  
  
|멤버|설명|  
|--------|--------|  
|<xref:System.Windows.HorizontalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 왼쪽에 맞춥니다.|  
|<xref:System.Windows.HorizontalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 가운데에 맞춥니다.|  
|<xref:System.Windows.HorizontalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 오른쪽에 맞춥니다.|  
|<xref:System.Windows.HorizontalAlignment>\(기본값\)|자식 요소를 늘여 부모 요소에 할당된 레이아웃 공간을 채웁니다.  명시적인 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 우선 적용됩니다.|  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 요소에 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 적용하는 방법을 보여 줍니다.  다양한 렌더링 동작을 보다 잘 설명하기 위해 각각의 특성 값이 표시되어 있습니다.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 위의 코드는 다음 이미지와 유사한 레이아웃을 만듭니다.  각 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값의 위치 지정 효과는 그림에 표시되어 있습니다.  
  
 ![HorizontalAlignment 샘플](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.png "layout\_horizontal\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### VerticalAlignment 속성  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성은 자식 요소에 적용할 세로 맞춤 특성을 설명합니다.  다음 표에서는 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성에 사용할 수 있는 값을 보여 줍니다.  
  
|멤버|설명|  
|--------|--------|  
|<xref:System.Windows.VerticalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 위쪽에 맞춥니다.|  
|<xref:System.Windows.VerticalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 가운데에 맞춥니다.|  
|<xref:System.Windows.VerticalAlignment>|자식 요소를 부모 요소에 할당된 레이아웃 공간의 아래쪽에 맞춥니다.|  
|<xref:System.Windows.VerticalAlignment>\(기본값\)|자식 요소를 늘여 부모 요소에 할당된 레이아웃 공간을 채웁니다.  명시적인 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 우선 적용됩니다.|  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 요소에 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 적용하는 방법을 보여 줍니다.  다양한 렌더링 동작을 보다 잘 설명하기 위해 각각의 특성 값이 표시되어 있습니다.  이 샘플의 목적에 맞게 각 속성 값의 레이아웃 동작을 보다 잘 설명하기 위해 모눈선이 표시된 상태로 <xref:System.Windows.Controls.Grid> 요소가 부모로 사용됩니다.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 위의 코드는 다음 이미지와 유사한 레이아웃을 만듭니다.  각 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 값의 위치 지정 효과는 그림에 표시되어 있습니다.  
  
 ![VerticalAlignment 속성 샘플](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.png "layout\_vertical\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## 여백 속성 이해  
 <xref:System.Windows.FrameworkElement.Margin%2A> 속성은 요소와 해당 자식 또는 피어 간의 거리를 설명합니다.  `Margin="20"`과 같은 구문을 사용하면 <xref:System.Windows.FrameworkElement.Margin%2A> 값을 일정하게 만들 수 있습니다.  이 구문을 사용하면 20 [장치 독립적 픽셀](GTMT)의 일정한 <xref:System.Windows.FrameworkElement.Margin%2A>을 요소에 적용할 수 있습니다.  <xref:System.Windows.FrameworkElement.Margin%2A> 값은 서로 다른 네 가지 값으로 이루어진 형태가 될 수 있으며 이 경우 각각의 값은 왼쪽, 위쪽, 오른쪽 및 아래쪽\(순서대로\)에 적용할 여백을 나타냅니다\(예: `Margin="0,10,5,25"`\).  <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 올바르게 사용하면 요소의 렌더링 위치와 인접 요소 및 자식의 렌더링 위치를 정밀하게 제어할 수 있습니다.  
  
> [!NOTE]
>  0이 아닌 여백은 요소의 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 바깥쪽에 공간을 만듭니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 요소 그룹에 균일한 여백을 적용하는 방법을 보여 줍니다.  즉, 모든 <xref:System.Windows.Controls.Button> 요소가 각 방향에 10픽셀의 여백을 두고 일정하게 배치됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 여백을 균일하게 설정하는 것이 적합하지 않은 경우가 많습니다.  이런 경우에는 균일하지 않은 여백을 적용할 수 있습니다.  다음 예제에서는 자식 요소에 균일하지 않은 여백을 적용하는 방법을 보여 줍니다.  여백은 왼쪽, 위쪽, 오른쪽, 아래쪽의 순서로 기술되어 있습니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## 안쪽 여백 속성 이해  
 안쪽 여백은 많은 점에서 <xref:System.Windows.FrameworkElement.Margin%2A>과 유사합니다.  하지만 소수의 클래스만 주로 편의성을 위해 Padding 속성을 노출합니다. <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control> 및 <xref:System.Windows.Controls.TextBlock>이 Padding 속성을 노출하는 클래스의 예입니다.  <xref:System.Windows.Controls.Border.Padding%2A> 속성은 자식 요소의 유효 크기를 지정된 <xref:System.Windows.Thickness> 값만큼 확장합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Border.Padding%2A>을 부모 <xref:System.Windows.Controls.Border> 요소에 적용하는 방법을 보여 줍니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## 응용 프로그램에서 맞춤, 여백 및 안쪽 여백 사용  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>는 복잡한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만드는 데 필요한 위치 지정 컨트롤을 제공합니다.  각 속성의 효과를 활용하여 자식 요소의 위치를 지정하면 동적 응용 프로그램 및 사용자 환경을 쉽게 만들 수 있습니다.  
  
 다음 예제에서는 이 항목에서 자세히 설명하는 각각의 개념에 대해 보여 줍니다.  이 예제에서는 이 항목의 첫 번째 샘플에 나와 있는 구조를 기반으로 하여 <xref:System.Windows.Controls.Grid> 요소를 첫 번째 샘플에 있는 <xref:System.Windows.Controls.Border>의 자식으로 추가하고  <xref:System.Windows.Controls.Border.Padding%2A>을 부모 <xref:System.Windows.Controls.Border> 요소에 적용합니다.  또한 자식 <xref:System.Windows.Controls.StackPanel> 요소 세 개 사이에 있는 공간을 분할하기 위해 <xref:System.Windows.Controls.Grid>를 사용하며  <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>의 다양한 효과를 보여 주기 위해 <xref:System.Windows.Controls.Button> 요소를 다시 사용합니다.  각 열의 <xref:System.Windows.Controls.Button> 요소에 적용할 다양한 속성을 더욱 쉽게 정의하기 위해 <xref:System.Windows.Controls.TextBlock> 요소를 각 <xref:System.Windows.Controls.ColumnDefinition>에 추가합니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 위 응용 프로그램을 컴파일하면 다음 그림과 같은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 생성됩니다.  다양한 속성 값의 효과는 요소 사이의 간격을 통해 확인할 수 있으며 각 열에서 요소의 중요한 속성 값은 <xref:System.Windows.Controls.TextBlock> 요소에 표시되어 있습니다.  
  
 ![하나의 응용 프로그램에서 여러 위치 지정 속성](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.png "layout\_margins\_padding\_aligment\_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## 새로운 기능  
 <xref:System.Windows.FrameworkElement> 클래스로 정의되는 위치 지정 속성을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에서 요소 배치를 정밀하게 제어할 수 있습니다.  이제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 더욱 쉽게 요소 위치를 지정할 수 있는 몇 가지 기술을 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃에 대해 자세히 설명하는 추가 리소스가 있습니다.  [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md) 항목에서는 다양한 <xref:System.Windows.Controls.Panel> 요소에 대해 자세히 설명하고  [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) 항목에서는 레이아웃 요소를 사용하여 구성 요소 위치를 지정하고 해당 동작을 데이터 소스에 바인딩하는 고급 기법을 소개합니다.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.Margin%2A>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF Layout Gallery 샘플](http://go.microsoft.com/fwlink/?LinkID=160054)