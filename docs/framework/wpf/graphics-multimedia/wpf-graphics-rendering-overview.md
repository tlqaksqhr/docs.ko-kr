---
title: "WPF 그래픽 렌더링 개요 | Microsoft Docs"
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
  - "그래픽, 렌더링(rendering)"
  - "그래픽 렌더링"
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: 51
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 48
---
# WPF 그래픽 렌더링 개요
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표시 계층에 대해 간략하게 설명합니다.  여기서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 모델에서의 렌더링 지원을 위한 <xref:System.Windows.Media.Visual> 클래스의 역할을 중점적으로 설명합니다.  
  
   
  
<a name="role_of_visual_object"></a>   
## 표시 개체의 역할  
 <xref:System.Windows.Media.Visual> 클래스는 모든 <xref:System.Windows.FrameworkElement> 개체가 파생되는 기본 추상화입니다.  이는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 새 컨트롤을 작성하기 위한 진입점이며 여러 가지 면에서 Win32 응용 프로그램 모델의 창 핸들\(HWND\)과 같습니다.  
  
 <xref:System.Windows.Media.Visual> 개체는 핵심 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체이며 렌더링 지원을 제공하는 기본적인 역할을 수행합니다.  <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.TextBox>와 같은 사용자 인터페이스 컨트롤은 <xref:System.Windows.Media.Visual> 클래스에서 파생되며 렌더링 데이터를 유지하는 데 사용됩니다.  <xref:System.Windows.Media.Visual> 개체는 다음과 같은 지원을 제공합니다.  
  
-   출력 표시: 유지 및 serialize된 시각적 요소의 그리기 콘텐츠를 렌더링합니다.  
  
-   변환: 시각적 요소에 대한 변환을 수행합니다.  
  
-   클리핑: 시각적 요소에 대한 클리핑 영역 지원을 제공합니다.  
  
-   적중 테스트: 좌표 또는 기하 도형이 시각적 요소의 경계 내에 포함되어 있는지 여부를 확인합니다.  
  
-   경계 상자 계산: 시각적 요소의 경계 사각형을 확인합니다.  
  
 그러나 <xref:System.Windows.Media.Visual> 개체는 다음과 같은 비렌더링 기능에 대한 지원은 제공하지 않습니다.  
  
-   이벤트 처리  
  
-   Layout  
  
-   스타일  
  
-   데이터 바인딩  
  
-   전역화  
  
 <xref:System.Windows.Media.Visual>은 자식 클래스가 파생되어야 하는 공용 추상 클래스로 노출됩니다.  다음 그림에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 노출되는 표시 개체의 계층 구조를 보여 줍니다.  
  
 ![시각적 개체에서 파생된 클래스의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
표시 클래스 계층 구조  
  
### DrawingVisual 클래스  
 <xref:System.Windows.Media.DrawingVisual>은 도형, 이미지 또는 텍스트를 렌더링하는 데 사용되는 간단한 그리기 클래스입니다.  이 클래스는 런타임 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다.  이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다.  <xref:System.Windows.Media.DrawingVisual>은 사용자 지정 표시 개체를 만드는 데 사용할 수 있습니다.  자세한 내용은 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)을 참조하십시오.  
  
### Viewport3DVisual 클래스  
 <xref:System.Windows.Media.Media3D.Viewport3DVisual>은 2차원 <xref:System.Windows.Media.Visual> 개체와 <xref:System.Windows.Media.Media3D.Visual3D> 개체를 연결합니다.  <xref:System.Windows.Media.Media3D.Visual3D> 클래스는 모든 3차원 시각적 요소의 기본 클래스입니다.  <xref:System.Windows.Media.Media3D.Viewport3DVisual>을 사용하려면 <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> 값과 <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> 값을 정의해야 합니다.  카메라를 사용하면 장면을 볼 수 있습니다.  뷰포트는 프로젝션이 2차원 화면에 매핑되는 위치를 설정합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서의 3차원에 대한 자세한 내용은 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)를 참조하십시오.  
  
### ContainerVisual 클래스  
 <xref:System.Windows.Media.ContainerVisual> 클래스는 <xref:System.Windows.Media.Visual> 개체 컬렉션의 컨테이너로 사용됩니다.  <xref:System.Windows.Media.DrawingVisual> 클래스는 <xref:System.Windows.Media.ContainerVisual> 클래스에서 파생되므로 표시 개체 컬렉션을 포함할 수 있습니다.  
  
### 표시 개체의 그리기 콘텐츠  
 <xref:System.Windows.Media.Visual> 개체는 해당 렌더링 데이터를 **벡터 그래픽 지침 목록**으로 저장합니다.  지침 목록의 각 항목은 그래픽 데이터의 하위 수준 집합 및 연관된 리소스를 serialize된 형식으로 나타냅니다.  그리기 콘텐츠를 포함할 수 있는 렌더링 데이터에는 네 가지 형식이 있습니다.  
  
|그리기 콘텐츠 형식|설명|  
|----------------|--------|  
|벡터 그래픽|벡터 그래픽 데이터 및 연관된 모든 <xref:System.Windows.Media.Brush> 및 <xref:System.Windows.Media.Pen> 정보를 나타냅니다.|  
|Image|<xref:System.Windows.Rect>로 정의된 영역 내의 이미지를 나타냅니다.|  
|문자 모양|지정된 글꼴 리소스에 있는 일련의 문자 모양인 <xref:System.Windows.Media.GlyphRun>을 렌더링하는 그리기를 나타냅니다.  이는 텍스트가 표시되는 방식입니다.|  
|비디오|비디오를 렌더링하는 그리기를 나타냅니다.|  
  
 <xref:System.Windows.Media.DrawingContext>를 사용하면 <xref:System.Windows.Media.Visual>을 표시 콘텐츠로 채울 수 있습니다.  <xref:System.Windows.Media.DrawingContext> 개체의 그리기 명령을 사용할 경우 실제로는 나중에 그래픽 시스템에 사용될 렌더링 데이터 집합을 저장하는 것이며 화면에 실시간으로 그리는 것이 아닙니다.  
  
 <xref:System.Windows.Controls.Button>과 같은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 만들 때 이 컨트롤은 그리기 자체에 대한 렌더링 데이터를 암시적으로 생성합니다.  예를 들어 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 설정하면 컨트롤이 문자 모양의 렌더링 표현을 저장합니다.  
  
 <xref:System.Windows.Media.Visual>은 해당 콘텐츠를 <xref:System.Windows.Media.DrawingGroup> 내에 포함된 하나 이상의 <xref:System.Windows.Media.Drawing> 개체로 설명합니다.  또한 <xref:System.Windows.Media.DrawingGroup>은 해당 콘텐츠에 적용되는 불투명 마스크, 변환, 비트맵 효과 및 기타 작업을 설명합니다.  <xref:System.Windows.Media.DrawingGroup> 작업은 콘텐츠가 렌더링될 때 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, <xref:System.Windows.Media.DrawingGroup.Transform%2A>의 순서로 적용됩니다.  
  
 다음 그림에서는 렌더링 시퀀스 중 <xref:System.Windows.Media.DrawingGroup> 작업이 적용되는 순서를 보여 줍니다.  
  
 ![DrawingGroup 작업의 순서](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
DrawingGroup 작업의 순서  
  
 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하십시오.  
  
#### 표시 계층의 그리기 콘텐츠  
 <xref:System.Windows.Media.DrawingContext>는 직접 인스턴스화할 수 없지만 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> 및 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>과 같은 특정 메서드에서 그리기 컨텍스트를 가져올 수 있습니다.  다음 예제에서는 <xref:System.Windows.Media.DrawingVisual>에서 <xref:System.Windows.Media.DrawingContext>를 검색하고 이를 사용하여 사각형을 그립니다.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### 표시 계층의 그리기 콘텐츠 열거  
 기타 다른 용도와 더불어 <xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.Media.Visual>의 콘텐츠를 열거하기 위한 개체 모델을 제공합니다.  
  
> [!NOTE]
>  시각적 요소의 콘텐츠를 열거할 경우 <xref:System.Windows.Media.Drawing> 개체를 검색하는 것이며 렌더링 데이터의 기본 표현을 벡터 그래픽 지침 목록으로 검색하는 것이 아닙니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용하여 <xref:System.Windows.Media.Visual>의 <xref:System.Windows.Media.DrawingGroup> 값을 검색하고 이를 열거합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## 표시 개체를 사용하여 컨트롤을 빌드하는 방법  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 많은 개체는 다른 표시 개체로 구성됩니다. 즉, 이러한 개체는 하위 개체의 다양한 계층 구조를 포함할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 컨트롤과 같은 많은 사용자 인터페이스 요소는 다양한 렌더링 요소 형식을 나타내는 다중 표시 개체로 구성됩니다.  예를 들어 <xref:System.Windows.Controls.Button> 컨트롤에는 <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter> 및 <xref:System.Windows.Controls.TextBlock>을 비롯한 다른 여러 개체가 포함될 수 있습니다.  
  
 다음 코드에서는 태그로 정의된 <xref:System.Windows.Controls.Button> 컨트롤을 보여 줍니다.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 기본 <xref:System.Windows.Controls.Button> 컨트롤을 구성하는 표시 개체를 열거하면 아래와 같은 표시 개체의 계층 구조가 나타납니다.  
  
 ![시각적 트리 계층 구조의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.png "VisualLayerOverview03")  
표시 트리 계층 구조 다이어그램  
  
 <xref:System.Windows.Controls.Button> 컨트롤에는 <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 요소가 포함되고 이 요소에는 <xref:System.Windows.Controls.ContentPresenter> 요소가 포함됩니다.  <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 요소는 <xref:System.Windows.Controls.Button>의 테두리와 배경을 그립니다.  <xref:System.Windows.Controls.ContentPresenter> 요소는 <xref:System.Windows.Controls.Button>의 콘텐츠를 표시합니다.  여기서는 텍스트를 표시하므로 <xref:System.Windows.Controls.ContentPresenter> 요소에 <xref:System.Windows.Controls.TextBlock> 요소가 포함됩니다.  <xref:System.Windows.Controls.Button> 컨트롤이 <xref:System.Windows.Controls.ContentPresenter>를 사용할 경우에는 콘텐츠를 <xref:System.Windows.Controls.Image>와 같은 다른 요소나 <xref:System.Windows.Media.EllipseGeometry>와 같은 기하 도형으로 표시할 수 있습니다.  
  
### 컨트롤 템플릿  
 컨트롤 계층 구조로 컨트롤을 확장하는 작업의 핵심은 <xref:System.Windows.Controls.ControlTemplate>입니다.  컨트롤 템플릿은 컨트롤의 기본 표시 계층 구조를 지정합니다.  컨트롤을 명시적으로 참조하는 경우 해당 표시 계층 구조를 암시적으로 참조하게 됩니다.  컨트롤 템플릿의 기본값을 재정의하여 컨트롤의 시각적 모양을 사용자 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.Button> 컨트롤의 배경색 값을 수정하여 단색 값 대신 선형 그라데이션 값을 사용할 수 있습니다.  자세한 내용은 [Button 스타일 및 템플릿](../../../../docs/framework/wpf/controls/button-styles-and-templates.md)을 참조하십시오.  
  
 <xref:System.Windows.Controls.Button> 컨트롤과 같은 사용자 인터페이스 요소에는 컨트롤의 전체 렌더링 정의를 설명하는 벡터 그래픽 지침 목록이 여러 개 포함되어 있습니다.  다음 코드에서는 태그로 정의된 <xref:System.Windows.Controls.Button> 컨트롤을 보여 줍니다.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 <xref:System.Windows.Controls.Button> 컨트롤을 구성하는 표시 개체 및 벡터 그래픽 지침 목록을 열거하면 아래와 같은 개체의 계층 구조가 나타납니다.  
  
 ![시각적 트리 및 렌더링 데이터의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
표시 트리 및 렌더링 데이터 다이어그램  
  
 <xref:System.Windows.Controls.Button> 컨트롤에는 <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 요소가 포함되고 이 요소에는 <xref:System.Windows.Controls.ContentPresenter> 요소가 포함됩니다.  <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 요소는 단추의 테두리 및 배경을 구성하는 모든 개별 그래픽 요소를 그립니다.  <xref:System.Windows.Controls.ContentPresenter> 요소는 <xref:System.Windows.Controls.Button>의 콘텐츠를 표시합니다.  여기서는 이미지를 표시하므로 <xref:System.Windows.Controls.ContentPresenter> 요소에 <xref:System.Windows.Controls.Image> 요소가 포함됩니다.  
  
 벡터 그래픽 지침 목록 및 표시 개체의 계층 구조와 관련하여 다음과 같은 몇 가지 사항에 유의해야 합니다.  
  
-   계층 구조의 순서는 그리기 정보의 렌더링 순서를 나타냅니다.  루트 시각적 요소로부터 자식 요소는 왼쪽에서 오른쪽, 위에서 아래로 이동합니다.  요소에 시각적 자식 요소가 있는 경우 이러한 자식 요소는 요소의 형제 요소 전에 이동됩니다.  
  
-   <xref:System.Windows.Controls.ContentPresenter>와 같이 계층에서 리프가 아닌 노드 요소는 자식 요소를 포함하는 데 사용되며 지침 목록을 포함하지 않습니다.  
  
-   시각적 요소에 벡터 그래픽 지침 목록과 표시 자식 요소가 모두 포함되어 있는 경우에는 표시 자식 개체의 그리기 전에 부모 시각적 요소의 지침 목록이 렌더링됩니다.  
  
-   벡터 그래픽 지침 목록의 항목은 왼쪽에서 오른쪽으로 렌더링됩니다.  
  
<a name="visual_tree"></a>   
## 표시 트리  
 표시 트리에는 응용 프로그램의 사용자 인터페이스에 사용되는 모든 시각적 요소가 포함됩니다.  시각적 요소에는 유지되는 그리기 정보가 포함되므로 디스플레이 장치에 표시되는 출력을 구성하는 데 필요한 모든 렌더링 정보를 포함하는 장면 그래프로 표시 트리를 생각할 수 있습니다.  이 트리는 응용 프로그램에서 코드나 태그 중 어느 것을 사용하든 직접 만든 모든 시각적 요소가 누적된 것입니다.  표시 트리에는 컨트롤 및 데이터 개체와 같은 요소의 템플릿 확장으로 만들어진 모든 시각적 요소도 포함됩니다.  
  
 다음 코드에서는 태그로 정의된 <xref:System.Windows.Controls.StackPanel> 요소를 보여 줍니다.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 태그 예제에서 <xref:System.Windows.Controls.StackPanel> 요소를 구성하는 표시 개체를 열거하면 아래와 같은 표시 개체의 계층 구조가 나타납니다.  
  
 ![시각적 트리 계층 구조의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.png "VisualLayerOverview05")  
표시 트리 계층 구조 다이어그램  
  
### 렌더링 순서  
 표시 트리는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표시 개체 및 그리기 개체의 렌더링 순서를 결정합니다.  이동은 표시 트리의 최상위 노드인 루트 시각적 요소로부터 시작됩니다.  그 다음 루트 시각적 요소의 자식이 왼쪽에서 오른쪽으로 이동됩니다.  시각적 요소에 자식 요소가 있는 경우 이러한 자식 요소는 시각적 요소의 형제 요소 전에 이동됩니다.  즉, 자식 시각적 요소의 콘텐츠는 시각적 요소 자체의 콘텐츠보다 먼저 렌더링됩니다.  
  
 ![시각적 트리 렌더링 순서의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.png "VisualLayerOverview06")  
표시 트리 렌더링 순서 다이어그램  
  
### 루트 시각적 요소  
 **루트 시각적 요소**는 표시 트리 계층 구조의 최상위 요소입니다.  대부분의 응용 프로그램에서 루트 시각적 요소의 기본 클래스는 <xref:System.Windows.Window> 또는 <xref:System.Windows.Navigation.NavigationWindow>입니다.  그러나 Win32 응용 프로그램에서 표시 개체를 호스팅하는 경우에는 루트 시각적 요소가 Win32 창에서 호스팅하는 최상위 시각적 요소가 됩니다.  자세한 내용은 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)을 참조하십시오.  
  
### 논리 트리와의 관계  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 논리 트리는 런타임의 응용 프로그램 요소를 나타냅니다.  이 트리를 직접 조작하지 않더라도 이 응용 프로그램 뷰는 속성 상속 및 이벤트 라우팅을 이해하는 데 유용합니다.  표시 트리와는 달리 논리 트리는 <xref:System.Windows.Documents.ListItem>과 같은 비표시 데이터 개체를 나타낼 수 있습니다.  많은 경우 논리 트리는 응용 프로그램의 태그 정의에 매우 밀접하게 매핑됩니다.  다음 코드에서는 태그로 정의된 <xref:System.Windows.Controls.DockPanel> 요소를 보여 줍니다.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 태그 예제에서 <xref:System.Windows.Controls.DockPanel> 요소를 구성하는 논리 개체를 열거하면 아래와 같은 논리 개체의 계층 구조가 나타납니다.  
  
 ![트리 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.png "Tree1\_wcp")  
논리 트리 다이어그램  
  
 표시 트리와 논리 트리 모두 현재의 응용 프로그램 요소 집합과 동기화되어 요소의 모든 추가, 삭제 또는 변경 내용을 반영합니다.  그러나 트리는 응용 프로그램에 대한 다른 뷰를 제공합니다.  표시 트리와 달리 논리 트리는 컨트롤의 <xref:System.Windows.Controls.ContentPresenter> 요소를 확장하지 않습니다.  즉, 같은 개체 집합에 대해 논리 트리와 표시 트리 간에 직접적인 일대일 대응이 이루어지지 않습니다.  사실 같은 요소를 매개 변수로 사용하여 **LogicalTreeHelper** 개체의 <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> 메서드와 **VisualTreeHelper** 개체의 <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> 메서드를 호출해도 서로 다른 결과가 발생합니다.  
  
 논리 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하십시오.  
  
### XamlPad를 사용하여 표시 트리 보기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 도구인 XamlPad는 현재 정의되어 있는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 콘텐츠에 해당하는 표시 트리를 보고 탐색하기 위한 옵션을 제공합니다.  메뉴 모음에서 **Show Visual Tree** 단추를 클릭하면 시각적 트리가 표시됩니다.  다음 그림에서는 XamlPad의 **Visual Tree Explorer** 패널에서 시각적 트리 노드로 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 콘텐츠를 확장하는 것을 보여 줍니다.  
  
 ![XamlPad의 시각적 트리 탐색기 패널](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
XamlPad의 Visual Tree Explorer 패널  
  
 여기서 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.Button> 컨트롤은 XamlPad의 **Visual Tree Explorer** 패널에 각각 별도의 시각적 개체 계층 구조를 표시합니다.  이는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 해당 컨트롤의 표시 트리를 포함하는 <xref:System.Windows.Controls.ControlTemplate>이 있기 때문입니다.  컨트롤을 명시적으로 참조하는 경우 해당 표시 계층 구조를 암시적으로 참조하게 됩니다.  
  
### 시각적 성능 프로파일링  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램의 런타임 동작을 분석하고 적용할 수 있는 성능 최적화 형식을 결정하는 데 사용할 수 있는 성능 프로파일링 도구 집합을 제공합니다.  Visual Profiler 도구는 응용 프로그램의 표시 트리에 직접 매핑하여 성능 데이터에 대한 풍부한 그래픽 뷰를 제공합니다.  다음 스크린 샷을 보면 Visual Profiler의 **CPU 사용** 섹션에 개체의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 서비스\(예: 렌더링 및 레이아웃\) 사용 정보가 자세히 분석되어 제공되어 있습니다.  
  
 ![Visual Profiler 표시 출력](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf\_VisualProfiler\_04")  
Visual Profiler 표시 출력  
  
<a name="visual_rendering_behavior"></a>   
## 시각적 요소 렌더링 동작  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 유지 모드 그래픽, 벡터 그래픽 및 장치 독립적인 그래픽과 같이 표시 개체의 렌더링 동작에 영향을 주는 여러 기능이 도입되었습니다.  
  
### 유지 모드 그래픽  
 표시 개체의 역할을 이해하기 위해서는 **직접 실행 모드** 그래픽 시스템과 **유지 모드** 그래픽 시스템 간의 차이를 이해하는 것이 중요합니다.  GDI 또는 GDI\+를 기반으로 하는 표준 Win32 응용 프로그램은 직접 실행 모드 그래픽 시스템을 사용합니다.  즉, 창 크기가 조정되거나 개체의 시각적 모양이 변경되는 등으로 인해 무효화된 클라이언트 영역의 부분을 응용 프로그램이 다시 그려야 합니다.  
  
 ![Win32 렌더링 시퀀스의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
Win32 렌더링 시퀀스 다이어그램  
  
 반대로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 유지 모드 시스템을 사용합니다.  즉, 시각적 모양이 있는 응용 프로그램 개체가 serialize된 그리기 데이터 집합을 정의합니다.  그리기 데이터가 정의된 후부터는 시스템이 응용 프로그램 개체 렌더링을 위한 모든 다시 그리기 요청에 응답합니다.  런타임에도 응용 프로그램 개체를 수정하거나 만들 수 있으며 시스템이 계속 그리기 요청에 응답합니다.  유지 모드 그래픽 시스템의 강점은 그리기 정보가 항상 응용 프로그램에 의해 serialize된 상태로 유지되지만 렌더링 작업은 시스템이 수행한다는 데 있습니다.  다음 다이어그램에서는 응용 프로그램이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 의존하여 그리기 요청에 응답하는 방식을 보여 줍니다.  
  
 ![WPF 렌더링 시퀀스의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
WPF 렌더링 시퀀스 다이어그램  
  
#### 지능형 다시 그리기  
 유지 모드 그래픽을 사용할 때의 가장 큰 장점은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 응용 프로그램에서 다시 그려야 할 부분을 효율적으로 최적화할 수 있다는 데 있습니다.  다양한 불투명도 수준이 있는 복잡한 장면의 경우에도 다시 그리기를 최적화하기 위해 특수 용도의 코드를 작성할 필요가 없습니다.  이를 Win32 프로그래밍과 비교해 보십시오. Win32에서는 업데이트 영역에서의 다시 그리기 작업을 최소화하여 응용 프로그램 최적화에 많은 노력을 기울여야 합니다.  Win32 응용 프로그램에서 다시 그리기를 최적화하는 작업과 관련된 여러 가지 복잡성에 대한 예는 [Redrawing in the Update Region](_win32_Redrawing_in_the_Update_Region)을 참조하십시오.  
  
### 벡터 그래픽  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 **벡터 그래픽**을 해당 렌더링 데이터 형식으로 사용합니다.  SVG\(확장 가능한 벡터 그래픽\), Windows 메타파일\(.wmf\) 및 트루타입 글꼴을 포함하는 벡터 그래픽은 렌더링 데이터를 저장했다가 그래픽 기본 요소를 사용하여 이미지를 다시 만드는 방법을 설명하는 지침 목록으로 이를 전송합니다.  예를 들어 트루타입 글꼴은 픽셀 배열이 아니라 선, 곡선 및 명령 집합을 설명하는 윤곽선 글꼴입니다.  벡터 그래픽의 중요한 장점 중 하나는 어떤 크기와 해상도로도 크기를 조정할 수 있다는 데 있습니다.  
  
 벡터 그래픽과 달리 비트맵 그래픽은 특정 해상도에 대해 사전에 렌더링된 이미지의 픽셀 단위 표현으로 렌더링 데이터를 저장합니다.  비트맵 그래픽 형식과 벡터 그래픽 형식 간의 중요한 차이점은 원래 소스 이미지에 대한 일관성에 있습니다.  예를 들어 소스 이미지의 크기가 수정되면 비트맵 그래픽 시스템은 이미지를 늘이는 데 반해 벡터 그래픽 시스템은 이미지의 일관성을 유지하면서 크기를 조정합니다.  
  
 다음 그림에서는 크기가 300% 확대된 소스 이미지를 보여 줍니다.  소스 이미지가 벡터 그래픽 이미지로 크기가 조정되지 않고 비트맵 그래픽 이미지로 늘어났을 때 나타나는 왜곡을 확인할 수 있습니다.  
  
 ![래스터 그래픽과 벡터 그래프의 차이](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
래스터 그래픽과 벡터 그래픽의 차이  
  
 다음 태그에서는 정의된 두 개의 <xref:System.Windows.Shapes.Path> 요소를 보여 줍니다.  두 번째 요소는 <xref:System.Windows.Media.ScaleTransform>을 사용하여 첫 번째 요소의 그리기 지침을 300% 확대합니다.  <xref:System.Windows.Shapes.Path> 요소의 그리기 지침은 그대로 유지됩니다.  
  
 [!code-xml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### 해상도 및 장치 독립적인 그래픽 정보  
 화면에서 텍스트와 그래픽의 크기는 해상도와 DPI라는 두 가지 시스템 요소로 결정됩니다.  해상도는 화면에 나타나는 픽셀 수를 설명합니다.  해상도가 높을수록 픽셀은 작아지므로 그래픽과 텍스트가 보다 작게 나타납니다.  1024 x 768로 설정된 모니터에 표시되는 그래픽은 해상도를 1600 x 1200으로 변경하면 더 작게 나타납니다.  
  
 또 다른 시스템 설정인 DPI는 픽셀 단위로 화면 인치 크기를 설명합니다.  대부분의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 시스템에서 DPI는 96이며 이는 화면 인치가 96픽셀임을 의미합니다.  DPI 설정을 늘리면 화면 인치가 커지고 DPI를 줄이면 화면 인치가 작아집니다.  즉, 화면 인치는 실제 인치와 크기가 다릅니다. 대부분의 시스템에서는 화면 인치가 실제 인치와 다릅니다.  DPI를 늘리면 화면 인치의 크기를 늘렸기 때문에 DPI를 인식하는 그래픽 및 텍스트가 커집니다.  DPI를 늘리면 특히 고해상도에서 텍스트를 보다 쉽게 읽을 수 있습니다.  
  
 모든 응용 프로그램이 DPI를 인식하는 것은 아닙니다. 어떤 응용 프로그램은 하드웨어 픽셀을 기본 측정 단위로 사용하므로 시스템 DPI를 변경해도 응용 프로그램에 아무런 영향이 없습니다.  다른 많은 응용 프로그램의 경우 DPI를 인식하는 단위를 사용하여 글꼴 크기를 설명하지만 다른 모든 항목을 설명할 때는 픽셀을 사용합니다.  응용 프로그램의 텍스트 크기는 시스템의 DPI 설정에 따라 조정되지만 응용 프로그램의 UI는 그렇지 않으므로 DPI를 너무 줄이거나 늘리면 이러한 응용 프로그램의 레이아웃에 문제가 발생할 수 있습니다.  이러한 문제는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 개발된 응용 프로그램에서 제거되었습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 하드웨어 픽셀 대신 장치 독립적인 픽셀을 기본 측정 단위로 사용하여 자동 배율 조정을 지원하므로 응용 프로그램 개발자가 별도의 작업을 수행하지 않아도 그래픽과 텍스트의 크기가 적절하게 조정됩니다.  다음 그림에서는 DPI 설정을 달리 지정했을 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 및 그래픽이 나타나는 방식의 예를 보여 줍니다.  
  
 ![서로 다른 DPI 설정에서의 그래픽과 텍스트](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm\_dpi\_setting\_examples")  
서로 다른 DPI 설정에서의 그래픽과 텍스트  
  
<a name="visualtreehelper_class"></a>   
## VisualTreeHelper 클래스  
 <xref:System.Windows.Media.VisualTreeHelper> 클래스는 표시 개체 수준에서의 프로그래밍을 위한 하위 수준 기능을 제공하는 정적 도우미 클래스로, 고성능 사용자 지정 컨트롤 개발과 같은 매우 특정한 시나리오에서 유용합니다.  대부분의 경우 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.TextBlock>과 같은 고급 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임워크 개체는 뛰어난 유연성과 사용 용이성을 제공합니다.  
  
### 적중 테스트  
 <xref:System.Windows.Media.VisualTreeHelper> 클래스는 기본 적중 테스트 지원이 사용자 요구를 충족시키지 못할 경우 표시 개체에 대해 적중 테스트를 수행하기 위한 메서드를 제공합니다.  <xref:System.Windows.Media.VisualTreeHelper> 클래스의 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 사용하여 기하 도형 또는 점 좌표 값이 컨트롤 또는 그래픽 요소와 같은 지정된 개체의 경계 내에 있는지 여부를 확인할 수 있습니다.  예를 들어 적중 테스트를 사용하여 개체의 경계 사각형 내에서의 마우스 클릭이 원 기하 도형 범위 내에 포함되는지 여부를 확인할 수 있습니다. 또한 적중 테스트의 기본 구현을 재정의하여 고유한 사용자 지정 적중 테스트 계산을 수행할 수 있습니다.  
  
 적중 테스트에 대한 자세한 내용은 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)를 참조하십시오.  
  
### 표시 트리 열거  
 <xref:System.Windows.Media.VisualTreeHelper> 클래스는 표시 트리의 멤버를 열거하기 위한 기능을 제공합니다.  부모를 검색하려면 <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A> 메서드를 호출합니다.  표시 개체의 자식 또는 직계 하위 항목을 검색하려면 <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> 메서드를 호출합니다.  이 메서드는 지정한 인덱스에서 부모의 자식 <xref:System.Windows.Media.Visual>을 반환합니다.  
  
 다음 예제에서는 표시 개체의 모든 하위 항목을 열거하는 방법을 보여 줍니다. 이는 표시 개체 계층 구조의 모든 렌더링 정보를 serialize하려는 경우 사용할 수 있는 기술입니다.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 대부분의 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는 논리 트리가 요소를 나타내는 데 보다 유용합니다.  논리 트리를 직접 수정하지 않더라도 이 응용 프로그램 뷰는 속성 상속 및 이벤트 라우팅을 이해하는 데 유용합니다.  표시 트리와는 달리 논리 트리는 <xref:System.Windows.Documents.ListItem>과 같은 비표시 데이터 개체를 나타낼 수 있습니다.  논리 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.VisualTreeHelper> 클래스는 표시 개체의 경계 사각형을 반환하기 위한 메서드를 제공합니다.  <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>를 호출하여 표시 개체의 경계 사각형을 반환할 수 있습니다.  <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>를 호출하여 표시 개체 자체를 비롯하여 표시 개체에 대한 모든 하위 항목의 경계 사각형을 반환할 수 있습니다.  다음 코드에서는 표시 개체 및 모든 해당 하위 항목의 경계 사각형을 계산하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 <xref:System.Windows.Media.DrawingVisual>   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)   
 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)   
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)