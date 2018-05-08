---
title: 맞춤, 여백 및 안쪽 여백 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: 70eff35db638c5bfbc9c164dc381e3f58e18957b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="alignment-margins-and-padding-overview"></a>맞춤, 여백 및 안쪽 여백 개요
<xref:System.Windows.FrameworkElement> 클래스 자식 요소의 위치를 정확 하 게 하는 데 사용 되는 몇 가지 속성을 표시 합니다. 이 항목에서는 가장 중요 한 속성의 4/설명: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서의 요소 위치를 제어하기 위한 기반을 제공하기 때문에 이 속성의 결과를 이해하는 것이 중요합니다.  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>요소 위치 지정 소개  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 요소를 배치하는 방법은 여러 가지가 있습니다. 그러나 적합 한 레이아웃을 달성 되 면 오른쪽을 단순히 선택 <xref:System.Windows.Controls.Panel> 요소입니다. 배치의 세부적으로 제어할 이해 해야는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성입니다.  
  
 다음 그림에서는 여러 위치 지정 속성을 사용하는 레이아웃 시나리오를 보여줍니다.  
  
 ![WPF 위치 지정 속성 샘플](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 얼핏 보기에 <xref:System.Windows.Controls.Button> 임의로 배치 될이 그림에서 요소가 나타날 수 있습니다. 그러나 해당 위치는 여백, 맞춤 및 안쪽 여백의 조합을 사용하여 실제로 정확하게 제어됩니다.  
  
 다음 예제에서는 앞의 그림에서 레이아웃을 만드는 방법을 설명합니다. A <xref:System.Windows.Controls.Border> 요소는 부모 캡슐화 <xref:System.Windows.Controls.StackPanel>와 <xref:System.Windows.Controls.Border.Padding%2A> 15 장치 독립적 픽셀의 값입니다. 이 기간은 좁은 <xref:System.Windows.Media.Brushes.LightBlue%2A> 밴드를 자식 둘러싸는 <xref:System.Windows.Controls.StackPanel>합니다. 자식 요소는 <xref:System.Windows.Controls.StackPanel> 각이 항목에 설명 된 다양 한 위치 지정 속성을 설명 하는 데 사용 됩니다. 세 가지 <xref:System.Windows.Controls.Button> 요소를 모두 보여 주기 위해 사용 되는 <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 다음 다이어그램은 이전 샘플에서 사용되는 다양한 위치 지정 속성의 자세히 보기를 제공합니다. 이 항목의 후속 섹션에서는 각 위치 지정 속성을 사용하는 방법을 자세히 설명합니다.  
  
 ![화면 호출을 사용하여 속성 위치 지정](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>맞춤 속성 이해  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성은 부모 요소의 레이아웃 할당 된 공간 내에서 자식 요소가 배치 되는 방식을 설명 합니다. 이러한 속성을 함께 사용하여 자식 요소를 정확하게 배치할 수 있습니다. 예를 들어, 자식 요소는 <xref:System.Windows.Controls.DockPanel> 네 가지 가로 맞춤 속성을 지정할 수 있습니다: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, 또는 <xref:System.Windows.HorizontalAlignment.Center>, 또는 <xref:System.Windows.HorizontalAlignment.Stretch> 사용 가능한 공간을 채웁니다. 비슷한 값을 세로 위치 지정에 사용할 수 있습니다.  
  
> [!NOTE]
>  명시적으로 설정 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 보다 우선 적용 하는 요소의 속성에는 <xref:System.Windows.HorizontalAlignment.Stretch> 속성 값입니다. 설정 하는 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값 `Stretch` 결과 `Stretch` 요청이 무시 됩니다.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>HorizontalAlignment 속성  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 자식 요소에 적용 해야 하는 가로 맞춤 특징을 선언 합니다. 다음 표에서 각각의 가능한 값은 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성입니다.  
  
|멤버|설명|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 왼쪽에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Center>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 중앙에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Right>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 오른쪽에 정렬됩니다.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (기본값)|자식 요소는 부모 요소의 할당된 레이아웃 공간을 채우도록 확장됩니다. 명시적 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 우선 합니다.|  
  
 적용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 <xref:System.Windows.Controls.Button> 요소입니다. 다양한 렌더링 동작의 이해를 돕기 위해 각 특성 값이 표시됩니다.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 앞의 코드는 다음 이미지와 비슷한 레이아웃을 만듭니다. 각각의 위치 지정 효과 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 값 그림에 표시 됩니다.  
  
 ![HorizontalAlignment 샘플](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>VerticalAlignment 속성  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성 자식 요소에 적용 해야 하는 세로 맞춤 특징을 설명 합니다. 다음 표에서 각에 대 한 가능한 값은 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성입니다.  
  
|멤버|설명|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 위에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Center>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 중앙에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|자식 요소는 부모 요소의 할당된 레이아웃 공간의 아래에 정렬됩니다.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (기본값)|자식 요소는 부모 요소의 할당된 레이아웃 공간을 채우도록 확장됩니다. 명시적 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 우선 합니다.|  
  
 적용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 <xref:System.Windows.Controls.Button> 요소입니다. 다양한 렌더링 동작의 이해를 돕기 위해 각 특성 값이 표시됩니다. 이 샘플의 목적을 위해 한 <xref:System.Windows.Controls.Grid> 모눈선이 표시 된 요소는 각 속성 값의 레이아웃 동작 이해를 돕기 위해의 부모로 사용 됩니다.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 앞의 코드는 다음 이미지와 비슷한 레이아웃을 만듭니다. 각각의 위치 지정 효과 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 값 그림에 표시 됩니다.  
  
 ![VerticalAlignment 속성 샘플](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>여백 속성 이해  
 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 요소와 자식 또는 피어 간의 거리를 설명 합니다. <xref:System.Windows.FrameworkElement.Margin%2A> 와 같은 구문을 사용 하 여 값은 균일 수 `Margin="20"`합니다. 이 균일 한이 구문을 사용 하 여 <xref:System.Windows.FrameworkElement.Margin%2A> 20 장치 독립적 픽셀 요소에 적용 합니다. <xref:System.Windows.FrameworkElement.Margin%2A> 값 수 형태를 취할 수의 네 가지 고유 값을 왼쪽, 위쪽, 오른쪽 및 아래쪽 (해당 순서에 따라)에 적용할 고유한 여백을 설명 하는 각 값 같은 `Margin="0,10,5,25"`합니다. 적절 한 사용는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 요소의 렌더링 위치 및 해당 인접 한 항목 요소 및 하위 항목 렌더링 위치 매우 세부적으로 제어할 수 있습니다.  
  
> [!NOTE]
>  0이 아닌 여백은 요소의 바깥쪽에 공간 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A>합니다.  
  
 다음 예제에서는 공통 여백을 그룹 주위에 적용 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Button> 요소입니다. <xref:System.Windows.Controls.Button> 각 방향에 10 픽셀 여백을 두고 요소의 간격이 균등 하 게 조정 됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 대부분의 경우 균일한 여백이 적합하지 않습니다. 이러한 경우, 균일하지 않은 여백을 적용할 수 있습니다. 다음 예제에서는 자식 요소에 균일하지 않은 여백을 적용하는 방법을 보여 줍니다. 여백은 왼쪽, 위, 오른쪽, 아래의 순서로 설명됩니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>안쪽 여백 속성 이해  
 안쪽 여백은 비슷합니다 <xref:System.Windows.FrameworkElement.Margin%2A> 대부분 비슷합니다. 편의 위해 기본적으로 몇 가지 클래스로에 대해서만에 안쪽 여백 속성이 노출 되는: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, 및 <xref:System.Windows.Controls.TextBlock> 안쪽 여백 속성을 노출 하는 클래스의 샘플입니다. <xref:System.Windows.Controls.Border.Padding%2A> 속성에서 지정 된 자식 요소의 유효 크기를 확대 <xref:System.Windows.Thickness> 값입니다.  
  
 다음 예제에서는 적용 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.Border.Padding%2A> 부모 <xref:System.Windows.Controls.Border> 요소입니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>응용 프로그램에서 맞춤, 여백 및 안쪽 여백 사용  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A><xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 복잡 한을 만드는 데 필요한 위치 지정 제어를 제공 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. 각 속성의 결과를 사용하여 자식 요소 위치를 변경하면 동적 응용 프로그램과 사용자 환경을 만드는 유연성을 사용할 수 있습니다.  
  
 다음 예제에서는 이 항목에 설명된 각 개념을 보여 줍니다. 이 항목의 첫 번째 예제에는 인프라를 바탕으로 추가 하는이 예제는 <xref:System.Windows.Controls.Grid> 의 자식으로 <xref:System.Windows.Controls.Border> 첫 번째 샘플에서. <xref:System.Windows.Controls.Border.Padding%2A> 부모에 적용 되 <xref:System.Windows.Controls.Border> 요소입니다. <xref:System.Windows.Controls.Grid> 세 명의 자식 사이 공백을 분할 하는 데 사용 <xref:System.Windows.Controls.StackPanel> 요소입니다. <xref:System.Windows.Controls.Button> 다양 한 효과 표시 하려면 요소를 다시 사용 <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>합니다. <xref:System.Windows.Controls.TextBlock> 각각에 요소가 추가 <xref:System.Windows.Controls.ColumnDefinition> 효율적에 적용 되는 다양 한 속성으로 정의 <xref:System.Windows.Controls.Button> 각 열에 있는 요소입니다.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 컴파일 시, 이전 응용 프로그램은 다음 그림과 유사한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다. 다양 한 속성 값의 효과 요소 사이의 간격에서 분명 하 게 되며 각 열에 있는 요소에 대 한 중요 한 속성 값에 표시 되어 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 ![한 응용 프로그램에서 여러 개의 위치 지정 속성](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>새로운 기능  
 위치에 정의 된 속성의 <xref:System.Windows.FrameworkElement> 클래스 내에서 요소 배치 세밀 하 게 제어할 수 있게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다. 이제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 요소 배치에 사용할 수 있는 여러 기술을 사용할 수 있습니다.  
  
 자세하게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃을 설명하는 추가 리소스를 사용할 수 있습니다. [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md) 다양 한 방법에 대 한 자세한 정보를 포함 하는 항목 <xref:System.Windows.Controls.Panel> 요소입니다. 항목 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) 레이아웃 요소를 사용 하 여 구성 요소를 배치 하 고 해당 작업을 데이터 원본에 바인딩 고급 기법을 소개 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.Margin%2A>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)  
 [WPF 레이아웃 갤러리 샘플](http://go.microsoft.com/fwlink/?LinkID=160054)
