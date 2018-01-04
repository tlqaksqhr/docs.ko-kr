---
title: "레이아웃"
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
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9a5f33ab22779002e85d7a73b29ae74dac81c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="layout"></a>레이아웃
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 레이아웃 시스템에 대해 설명합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용자 인터페이스를 만들려면 언제, 어떻게 레이아웃을 계산해야 하는지를 이해해야 합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [요소 경계 상자](#LayoutSystem_BoundingBox)  
  
-   [레이아웃 시스템](#LayoutSystem_Overview)  
  
-   [자식 측정 및 정렬](#LayoutSystem_Measure_Arrange)  
  
-   [패널 요소 및 사용자 지정 레이아웃 동작](#LayoutSystem_PanelsCustom)  
  
-   [레이아웃 성능 고려 사항](#LayoutSystem_Performance)  
  
-   [하위 픽셀 렌더링 및 레이아웃 반올림](#LayoutSystem_LayoutRounding)  
  
-   [새로운 기능](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>요소 경계 상자  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 레이아웃을 고려할 경우에는 모든 요소를 둘러싸고 있는 경계 상자를 이해해야 합니다. 각 <xref:System.Windows.FrameworkElement> 소비 레이아웃에서 시스템은 일종의 레이아웃에 배치 하는 사각형입니다. <xref:System.Windows.Controls.Primitives.LayoutInformation> 클래스 요소의 레이아웃 할당 또는 슬롯의 경계를 반환 합니다. 모든 제약 조건, 특정 레이아웃 속성 (예: 여백 및 안쪽 여백) 및 부모 개별 동작의 크기, 사용 가능한 화면 공간을 계산 하 여 사각형의 크기 결정 <xref:System.Windows.Controls.Panel> 요소입니다. 이 데이터를 처리 레이아웃 시스템은 수 특정의 모든 자식 항목의 위치를 계산 <xref:System.Windows.Controls.Panel>합니다. 와 같은 부모 요소에는 크기 조정 특성 정의 기억을 고려해 야는 <xref:System.Windows.Controls.Border>, 해당 자식에 영향을 줍니다.  
  
 다음 그림에서는 간단한 레이아웃을 보여 줍니다.  
  
 ![경계 상자가 없이 겹쳐 놓은 일반적인 Grid](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 다음 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 이 레이아웃을 실현할 수 있습니다.  
  
 [!code-xaml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 단일 <xref:System.Windows.Controls.TextBlock> 요소 내에 호스팅되는 <xref:System.Windows.Controls.Grid>합니다. 텍스트의 왼쪽 위 모퉁이의 첫 번째 열에 할당된 된 공간을 채우는 <xref:System.Windows.Controls.TextBlock> 실제로 훨씬 큽니다. 경계 상자 <xref:System.Windows.FrameworkElement> 를 사용 하 여 검색할 수는 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드. 다음 그림에 대 한 경계 상자는 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 ![이제 TextBlock의 경계 상자가 표시됨](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 노란색 사각형에 할당된 된 공간에 의해 표시 된 것 처럼는 <xref:System.Windows.Controls.TextBlock> 요소 실제로 보다 더 큽니다 나타납니다. 추가 요소에 추가 되 고 <xref:System.Windows.Controls.Grid>,이 할당 유형 및 추가 된 요소의 크기에 따라 확장 또는 축소 수 없습니다.  
  
 레이아웃 슬롯은 <xref:System.Windows.Controls.TextBlock> 로 변환 되는 <xref:System.Windows.Shapes.Path> 를 사용 하 여는 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드. 이 기술은 요소의 경계 상자를 표시하는 데 유용합니다.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>레이아웃 시스템  
 가장 간단한 레이아웃은 재귀 시스템이며 이를 통해 요소의 크기가 조정되고 요소가 배치되고 그려집니다. 레이아웃 측정 및의 멤버를 정렬 하는 과정을 설명 하는 보다 구체적으로 <xref:System.Windows.Controls.Panel> 요소의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션입니다. 레이아웃은 집약적인 프로세스입니다. 더 큰 숫자는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션, 많을 수록 계산 해야 합니다. 에 정의 된 레이아웃 동작에 따라 복잡성 나타날 수도 있습니다는 <xref:System.Windows.Controls.Panel> 컬렉션을 소유 하는 요소입니다. 상대적으로 간단한 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Canvas>, 보다 복잡 한 보다 성능이 크게 향상 점이 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Grid>.  
  
 때마다 자식 <xref:System.Windows.UIElement> 해당 위치를 변경할 레이아웃 시스템에서 새로운 패스를 트리거할 수 있는 것입니다. 따라서 불필요한 호출로 인해 응용 프로그램 성능이 저하될 수 있으므로 레이아웃 시스템을 호출할 수 있는 이벤트를 이해해야 합니다. 다음에서 레이아웃 시스템이 호출될 때 발생하는 프로세스에 대해 설명합니다.  
  
1.  자식 <xref:System.Windows.UIElement> 먼저 핵심 속성이 측정 하 여 레이아웃 프로세스를 시작 합니다.  
  
2.  크기 조정 속성에 정의 된 <xref:System.Windows.FrameworkElement> 와 같은 평가 됩니다 <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, 및 <xref:System.Windows.FrameworkElement.Margin%2A>합니다.  
  
3.  <xref:System.Windows.Controls.Panel>-와 같은 특정 논리가 적용 되며 <xref:System.Windows.Controls.Dock> 방향 또는 탄력적인 <xref:System.Windows.Controls.StackPanel.Orientation%2A>합니다.  
  
4.  모든 자식을 측정한 후에 콘텐츠가 정렬됩니다.  
  
5.  <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션이 화면에 그려집니다.  
  
6.  추가 하는 경우 프로세스가 다시 실행 됩니다 <xref:System.Windows.Controls.Panel.Children%2A> 는 컬렉션에 추가 되는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 적용 되 또는 <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드를 호출 합니다.  
  
 이 프로세스와 해당 프로세스가 호출되는 방법은 다음 섹션에 자세히 정의되어 있습니다.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>자식 측정 및 정렬  
 이 레이아웃 시스템의 각 멤버에 대 한 두 개의 패스를 완료 합니다.는 <xref:System.Windows.Controls.Panel.Children%2A> 수집, 측정 단계 및 정렬 단계입니다. 각 자식 <xref:System.Windows.Controls.Panel> 자체 제공 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 자체 특정 레이아웃 동작을 얻기 위해 메서드.  
  
 각 멤버의 측정 단계 중는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 평가 됩니다. 에 대 한 호출으로 시작 하는 프로세스는 <xref:System.Windows.UIElement.Measure%2A> 메서드. 부모 구현 내에서이 메서드는 <xref:System.Windows.Controls.Panel> 요소인 되려면 레이아웃에 대 한 명시적으로 호출할 수 없는 합니다.  
  
 첫 번째, 네이티브 크기 속성은 <xref:System.Windows.UIElement> 와 같은 평가 됩니다 <xref:System.Windows.UIElement.Clip%2A> 및 <xref:System.Windows.UIElement.Visibility%2A>합니다. 명명 된 값이 생성 `constraintSize` 에 전달 되는 <xref:System.Windows.FrameworkElement.MeasureCore%2A>합니다.  
  
 프레임 워크 속성에 정의 된 두 번째로, <xref:System.Windows.FrameworkElement> 처리 되며, 값에 영향을 주는 `constraintSize`합니다. 이러한 속성은 일반적으로 내부 크기 조정 특성을 설명 <xref:System.Windows.UIElement>와 같은 해당 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, 및 <xref:System.Windows.FrameworkElement.Style%2A>합니다. 이러한 각 속성은 요소를 표시하는 데 필요한 공간을 변경할 수 있습니다. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>다음으로 호출 `constraintSize` 매개 변수로 합니다.  
  
> [!NOTE]
>  속성 사이의 차이가 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A>합니다. 예를 들어는 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성은 다른 높이 입력 레이아웃 시스템에 따라 계산된 된 값입니다. 값은 실제 렌더링 단계에 따라 레이아웃 시스템 자체에서 설정 되며 같은 속성의 설정 값 뒤에 약간 지연 될 수 있습니다 <xref:System.Windows.FrameworkElement.Height%2A>, 입력된 변경 기준인 합니다.  
>   
>  때문에 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 수 계산된 된 값이 있을 수 여러 또는 점증적 변경 하 여 다양 한 작업의 결과로 레이아웃 시스템에서 합니다. 레이아웃 시스템은 자식 요소에 필요한 측정 공간, 부모 요소에 의한 제약 조건 등을 계산할 수도 있습니다.  
  
 측정 단계 궁극적인 목표를 확인 하려면 자식 항목이 해당 <xref:System.Windows.UIElement.DesiredSize%2A>, 동안 발생 하는 <xref:System.Windows.FrameworkElement.MeasureCore%2A> 호출 합니다. <xref:System.Windows.UIElement.DesiredSize%2A> 여 값을 저장 <xref:System.Windows.UIElement.Measure%2A> 콘텐츠 정렬 단계 중에 사용 합니다.  
  
 정렬 단계에 대 한 호출으로 시작는 <xref:System.Windows.UIElement.Arrange%2A> 메서드. 부모 정렬 단계 동안 <xref:System.Windows.Controls.Panel> 요소는 자식 요소의 경계를 나타내는 사각형을 생성 합니다. 이 값이 전달 된 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 처리를 위해 메서드.  
  
 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드 평가 <xref:System.Windows.UIElement.DesiredSize%2A> 자식 요소의 렌더링 된 크기에 영향을 줄 수 있는 추가 여백을 평가 하 고 있습니다. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>생성 된 `arrangeSize`로 전달 되는 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 의 메서드는 <xref:System.Windows.Controls.Panel> 매개 변수로 합니다. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>생성 된 `finalSize` 자식입니다. 마지막으로 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드 등의 오프셋된 속성, 여백 및 맞춤, 마지막 평가 역할과 레이아웃 슬롯 내 자식을 넣습니다. 자식은 할당된 공간을 모두 채울 필요가 없으며 실제 모두 채우는 경우가 드뭅니다. 컨트롤의 부모에 게 반환 됩니다 <xref:System.Windows.Controls.Panel> 레이아웃 프로세스가 완료 됩니다.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>패널 요소 및 사용자 지정 레이아웃 동작  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]파생 되는 요소는 그룹이 포함 되어 <xref:System.Windows.Controls.Panel>합니다. 이러한 <xref:System.Windows.Controls.Panel> 요소 많은 복잡 한 레이아웃을 사용 하도록 설정 합니다. 예를 들어 요소를 스태킹 쉽게 액세스가 가능를 사용 하 여는 <xref:System.Windows.Controls.StackPanel> 요소를 사용 하 여 복잡 하 고 무료 이동을 레이아웃은 가능한 한 <xref:System.Windows.Controls.Canvas>합니다.  
  
 다음 표에서 사용 가능한 레이아웃 요약 <xref:System.Windows.Controls.Panel> 요소입니다.  
  
|패널 이름|설명|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|명시적으로 좌표로 기준으로 자식 요소를 배치할 수 있는 영역을 정의 하는 <xref:System.Windows.Controls.Canvas> 영역입니다.|  
|<xref:System.Windows.Controls.DockPanel>|자식 요소를 서로 맞춰 가로 또는 세로로 정렬할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.Grid>|열 및 행으로 구성되는 유연한 모눈 영역을 정의합니다.|  
|<xref:System.Windows.Controls.StackPanel>|가로 또는 세로 방향으로 한 줄로 자식 요소를 정렬합니다.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|에 대 한 프레임 워크를 제공 <xref:System.Windows.Controls.Panel> 자신의 자식 데이터 컬렉션을 가상화 하는 요소입니다. 이 클래스는 추상 클래스입니다.|  
|<xref:System.Windows.Controls.WrapPanel>|콘텐츠를 컨테이너의 가장자리에서 다음 줄로 나눠 왼쪽에서 오른쪽으로 자식 요소의 위치를 지정합니다. 위쪽에서 아래쪽 또는 오른쪽에서 왼쪽의 값에 따라 순차적으로 발생 정렬는 <xref:System.Windows.Controls.WrapPanel.Orientation%2A> 속성입니다.|  
  
 미리 정의 된를 사용 하 여 수 없으면 하는 레이아웃을 필요로 하는 응용 프로그램에 대 한 <xref:System.Windows.Controls.Panel> 에서 상속 하 여 요소를 사용자 지정 레이아웃 동작을 수행할 수 있습니다 <xref:System.Windows.Controls.Panel> 재정의 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드. 예제는 [Custom Radial Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159982)(사용자 지정 방사형 패널 샘플)을 참조하세요.  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>레이아웃 성능 고려 사항  
 레이아웃은 재귀적인 프로세스입니다. 각 자식 요소는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 레이아웃 시스템을 호출할 때마다 처리 됩니다. 따라서 필요하지 않을 때 레이아웃 시스템을 트리거하는 것을 피해야 합니다. 다음은 보다 뛰어난 성능을 얻는 데 도움이 되는 고려 사항입니다.  
  
-   레이아웃 시스템에서 재귀적으로 업데이트하도록 하는 속성 값 변경에 주의해야 합니다.  
  
     레이아웃 시스템을 초기화하는 값을 가진 종속성 속성은 공용 플래그로 표시됩니다. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>및 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> 값이 변경 되는 속성에 대 한 재귀를 강제로 유용한 단서 레이아웃 시스템에서 업데이트를 제공 합니다. 요소의 경계 상자 크기에 영향을 줄 수 있는 모든 속성 있어야 일반적으로 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> 플래그가 true로 설정 합니다. 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.  
  
-   사용 가능한 경우 한 <xref:System.Windows.UIElement.RenderTransform%2A> 대신는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>합니다.  
  
     A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 매우 유용 하 게 내용의 영향을 줄 수 있습니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. 그러나 다른 요소의 위치에 영향을 변환 효과가 없으면 것이 가장 좋습니다 사용 하는 <xref:System.Windows.UIElement.RenderTransform%2A> 대신 때문에 <xref:System.Windows.UIElement.RenderTransform%2A> 레이아웃 시스템을 호출 하지 않습니다. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>변환을 적용 하 고 영향을 받는 요소의 새 위치를 고려 하는 재귀적 레이아웃 업데이트를 수행 합니다.  
  
-   불필요 한 호출 하지 마십시오. <xref:System.Windows.UIElement.UpdateLayout%2A>합니다.  
  
     <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드는 재귀적 레이아웃 업데이트를 강제 하며 자주 필요 하지 않습니다. 전체 업데이트가 필요하다고 확신하는 경우를 제외하고는 레이아웃 시스템에서만 이 메서드를 호출합니다.  
  
-   큰 작업할 때 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션을 사용 하는 것이 좋습니다는 <xref:System.Windows.Controls.VirtualizingStackPanel> 일반 대신 <xref:System.Windows.Controls.StackPanel>합니다.  
  
     자식 컬렉션을 가상화 하 여는 <xref:System.Windows.Controls.VirtualizingStackPanel> 개체만 부모의 뷰포트 내에서 현재 사용 중인 메모리에 유지 합니다. 이를 통해 대부분의 시나리오에서 성능이 크게 향상됩니다.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>하위 픽셀 렌더링 및 레이아웃 반올림  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 시스템에서는 해상도와 장치의 영향을 받지 않기 위해 장치 독립적 단위를 사용합니다. 각 장치 독립적 픽셀은 시스템의 [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] 설정에 맞게 자동으로 크기가 조정됩니다. 이를 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 다양한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 설정에 적합하게 크기를 조정할 수 있으며 자동으로 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]를 인식할 수 있도록 합니다.  
  
 그러나 이러한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 독립성은 앤티앨리어싱으로 인해 불규칙한 가장자리 렌더링을 만들 수 있습니다. 일반적으로 흐리거나 반투명한 가장자리로 표시되는 이러한 아티팩트는 가장자리의 위치가 장치 픽셀 사이가 아닌 장치 픽셀 가운데에 있을 때 발생할 수 있습니다. 레이아웃 시스템에서는 레이아웃 반올림을 사용하여 조정할 수 있는 방법을 제공합니다. 레이아웃 반올림에서 레이아웃 단계 동안 모든 비정수 픽셀 값을 레이아웃 시스템이 반올림합니다.  
  
 레이아웃 반올림은 기본적으로 사용되지 않습니다. 레이아웃 반올림을 사용 하려면 설정는 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 속성을 `true` 에서 <xref:System.Windows.FrameworkElement>합니다. 종속성 속성이므로 값이 시각적 트리의 모든 자식에 전파됩니다. 레이아웃 반올림 전체 ui를 사용 하려면 설정 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 를 `true` 루트 컨테이너에 있습니다. 예제를 보려면 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>를 참조하십시오.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>새로운 기능  
 요소의 측정 방법과 정렬 방법을 이해하는 것이 레이아웃을 이해하기 위한 첫 단계입니다. 사용 가능한 항목에 대 한 자세한 내용은 <xref:System.Windows.Controls.Panel> 요소 참조 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)합니다. 레이아웃에 영향을 줄 수 있는 다양한 배치 속성을 더 잘 이해하려면 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)를 참조하세요. 사용자 지정에 대 한 예제 <xref:System.Windows.Controls.Panel> 요소 참조 [방사형 패널의 사용자 지정 샘플](http://go.microsoft.com/fwlink/?LinkID=159982)합니다. 간단한 응용 프로그램에 모두 함께 배치 하 라는 준비가 되 면 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.UIElement>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
