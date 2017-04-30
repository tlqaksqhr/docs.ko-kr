---
title: "그래픽 및 멀티미디어 | Microsoft Docs"
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
- media, features
- video effects
- sound effects
- animation, features
- graphics features
- transition effects
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: ea78944133412f43075d8d094cd5fa93685299f9
ms.lasthandoff: 04/08/2017

---
# <a name="graphics-and-multimedia"></a>그래픽 및 멀티미디어
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 멀티미디어, 벡터 그래픽, 애니메이션 및 콘텐츠 컴퍼지션을 지원하여 개발자가 흥미로운 사용자 인터페이스 및 콘텐츠를 쉽게 작성할 수 있도록 합니다. [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 벡터 그래픽이나 복잡한 애니메이션을 만든 후 미디어를 응용 프로그램에 통합할 수 있습니다.  
  
 이 항목에서는 그래픽, 전환 효과, 소리 및 비디오를 응용 프로그램에 추가할 수 있도록 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 그래픽, 애니메이션 및 미디어 기능을 소개합니다.  
  
> [!NOTE]
>  Windows 서비스에서 WPF 유형을 사용해서는 안 됩니다. Windows 서비스에서 WPF 유형을 사용하려고 하면 서비스가 예상대로 작동하지 않을 수 있습니다.   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>WPF 4에 포함된 그래픽 및 멀티미디어의 새로운 기능  
 그래픽 및 애니메이션에 관련해서 몇 가지 사항이 변경되었습니다.  
  
-   레이아웃 조정  
  
     개체 가장자리가 픽셀 장치 중앙에 놓이면 DPI 독립적 그래픽 시스템은 흐릿한 가장자리 또는 반투명 가장자리와 같은 렌더링 아티팩트를 만들 수 있습니다. 이전 버전의 WPF에는 이러한 경우를 처리하는 데 도움이 되는 픽셀 맞추기 기능이 포함되어 있습니다. Silverlight 2에서는 가장자리가 전체 픽셀 경계에 딱 맞게 요소를 이동하는 또 다른 방법인 레이아웃 조정이 도입되었습니다. 이제 WPF는 <xref:System.Windows.FrameworkElement>에 대해 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 연결된 속성을 사용하여 레이아웃 조정을 지원합니다.  
  
-   캐시된 컴퍼지션  
  
     새로운 <xref:System.Windows.Media.BitmapCache> 및 <xref:System.Windows.Media.BitmapCacheBrush> 클래스를 사용하여 시각적 트리의 복잡한 부분을 비트맵으로 캐시하고 렌더링 시간을 크기 향상시킬 수 있습니다. 비트맵은 마우스 클릭 같은 사용자 입력에 응답하며, 브러시처럼 다른 요소에 칠할 수 있습니다.  
  
-   픽셀 셰이더 3 지원  
  
     WPF 4는 PS(픽셀 셰이더) 버전 3.0을 사용하여 응용 프로그램이 효과를 작성하도록 함으로써 WPF 3.5 SP1에 도입되었던 <xref:System.Windows.Media.Effects.ShaderEffect> 지원을 토대로 구축되었습니다. PS 3.0 셰이더 모델은 PS 2.0보다 더 정교해졌으며 지원되는 하드웨어에 더 많은 영향을 미칠 수 있습니다.  
  
-   감속/가속 함수  
  
     감속/가속 함수를 사용하여 애니메이션을 개선하고 동작을 좀 더 강력히 제어할 수 있습니다. 예를 들어 <xref:System.Windows.Media.Animation.ElasticEase>를 애니메이션에 적용하여 애니메이션에 튕기는 동작을 부여할 수 있습니다. 자세한 내용은 <xref:System.Windows.Media.Animation> 네임스페이스의 감속/가속 형식을 참조하세요.  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a>그래픽 및 렌더링  
 WPF는 고품질의 2차원 그래픽을 지원합니다. 기능으로는 브러시, 기하 도형, 이미지, 도형 및 변환 기능이 있습니다. 자세한 내용은 [그래픽](../../../../docs/framework/wpf/graphics-multimedia/graphics.md)을 참조하세요. 그래픽 요소 렌더링은 <xref:System.Windows.Media.Visual> 클래스를 기준으로 합니다. 화면의 시각적 개체 구조는 시각적 트리로 설명됩니다. 자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.  
  
### <a name="2-d-shapes"></a>2차원 도형  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 다음 그림에 표시된 사각형 및 타원과 같은 일반적인 벡터 기반의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 도형 라이브러리를 제공합니다.  
  
 ![타원 및 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 이러한 내장 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 도형은 단순히 도형이 아닙니다. 키보드 및 마우스 입력을 포함하는 가장 일반적인 컨트롤에서 기대하는 많은 기능을 구현하는 프로그래밍 가능 요소입니다. 다음 예제에서는 <xref:System.Windows.Shapes.Ellipse> 요소를 클릭하여 발생한 <xref:System.Windows.UIElement.MouseUp> 이벤트를 처리하는 방법을 보여 줍니다.  
  
```xaml  
\<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  x:Class="Window1" >  
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />  
</Window>  
```  
  
```csharp  
public partial class Window1  : Window  
{  
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)  
    {  
        MessageBox.Show("You clicked the ellipse!");  
    }  
}  
```  
  
```vb  
Partial Public Class Window1  
    Inherits Window  
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)  
        MessageBox.Show("You clicked the ellipse!")  
    End Sub  
End Class  
  
```  
  
 다음 그림에서는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 코드 숨김에 대한 출력을 보여 줍니다.  
  
 !["you clicked the ellipse&#33;" 텍스트가 있는 창](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)를 참조하세요. 기본 샘플을 보려면 [도형 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하세요.  
  
### <a name="2-d-geometries"></a>2차원 기하 도형  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 제공하는 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 도형으로 충분하지 않을 경우 기하 도형 및 경로에 대한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 지원을 사용하여 도형을 직접 만들 수 있습니다. 다음 그림에서는 기하 도형을 그리기 브러시로 사용하여 도형을 만들고 다른 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소를 클리핑하는 방법을 보여 줍니다.  
  
 ![Path의 다양한 용도](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 자세한 내용은 [기하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)를 참조하세요. 기본 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.  
  
### <a name="2-d-effects"></a>2차원 효과  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 다양한 효과 만드는 데 사용할 수 있는 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 클래스 라이브러리를 제공합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 렌더링 기능은 그라데이션, 비트맵, 그림 및 비디오가 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 그리고 회전, 크기 조정 및 기울이기를 사용하여 조작하는 기능을 제공합니다. 다음 그림에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 브러시를 사용하여 획득할 수 있는 많은 효과의 예를 보여 줍니다.  
  
 ![여러 브러시의 설명](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 자세한 내용은 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)를 참조하세요. 기본 샘플을 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요.  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a>3차원 렌더링  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 더 흥미로운 레이아웃, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 및 데이터 시각화를 만들 수 있도록 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽 지원을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 통합하는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 렌더링 기능 집합을 제공합니다. 다음 그림과 같이 스펙트럼의 한쪽 끝에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 이미지를 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 도형 표면 위에 렌더링할 수 있습니다.  
  
 ![Visual3D 샘플 스크린샷](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 자세한 내용은 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)를 참조하세요. 기본 샘플을 보려면 [3차원 단색 샘플](http://go.microsoft.com/fwlink/?LinkID=159964)을 참조하세요.  
  
<a name="animation"></a>   
## <a name="animation"></a>애니메이션  
 애니메이션으로 컨트롤 및 요소가 커지거나, 흔들리거나, 회전하거나, 사라지도록 하여 흥미로운 페이지 전환 등을 만들 수 있습니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 대부분의 속성에 애니메이션 효과를 줄 수 있을 뿐 아니라 대부분의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 개체에도 애니메이션 효과를 줄 수 있으므로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하여 만든 사용자 지정 개체에 애니메이션 효과를 줄 수도 있습니다.  
  
 ![애니메이션 효과가 적용된 큐브의 이미지](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요. 기본 샘플을 보려면 [애니메이션 예제 갤러리](http://go.microsoft.com/fwlink/?LinkID=159969)를 참조하세요.  
  
<a name="media"></a>   
## <a name="media"></a>미디어  
 이미지, 비디오 및 오디오는 미디어를 통해 정보 및 사용자 환경을 전달하는 방법입니다.  
  
### <a name="images"></a>이미지  
 아이콘, 배경 및 애니메이션 일부를 포함하는 이미지는 대부분의 응용 프로그램에서 핵심적인 부분입니다. 이미지를 자주 사용해야 하므로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 여러 가지 방법으로 이미지로 작업하는 기능을 제공합니다. 다음 그림에서는 해당 방법 중 하나만 보여 줍니다.  
  
 ![스타일 샘플 스크린샷](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
 자세한 내용은 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)를 참조하세요.  
  
### <a name="video-and-audio"></a>비디오 및 오디오  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 제공하는 그래픽 기능 중 핵심 기능은 비디오 및 오디오를 포함하는 멀티미디어로 작업할 수 있도록 지원하는 것입니다. 다음 예제에서는 미디어 플레이어를 응용 프로그램에 삽입하는 방법을 보여 줍니다.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement>는 비디오 및 오디오 둘 다를 재생할 수 있도록 하며 사용자 지정 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 쉽게 만들 수 있도록 확장 가능합니다.  
  
 자세한 내용은 [멀티미디어 개요](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [애니메이션 및 타이밍](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [3차원 그래픽](http://msdn.microsoft.com/en-us/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [멀티미디어](http://msdn.microsoft.com/en-us/44a8dcd0-80cb-4db0-a222-87cde68c2fac)
