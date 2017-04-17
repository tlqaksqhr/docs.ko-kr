---
title: "Transform 개요 | Microsoft Docs"
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
  - "2차원 변환 클래스"
  - "클래스, 2차원 변환"
  - "FrameworkElement 개체, 회전"
  - "FrameworkElement 개체, 배율"
  - "FrameworkElement 개체, 기울이기"
  - "FrameworkElement 개체, 변환"
  - "변환 클래스, 2차원"
  - "변환, 변환 정보"
  - "변환, 변환 정보"
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Transform 개요
이 항목에서는 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> 클래스를 사용하여 <xref:System.Windows.FrameworkElement> 개체를 회전, 배율 조정, 이동\(위치 변환\) 및 기울이는 방법을 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whatIsATransformSection"></a>   
## Transform 정의  
 <xref:System.Windows.Media.Transform>은 점을 한 좌표 공간에서 다른 좌표 공간으로 매핑 또는 변환하는 방법을 정의합니다.  이 매핑은 값이 <xref:System.Double>인 세 열이 있는 세 행의 컬렉션인 <xref:System.Windows.Media.Matrix>의 변환으로 설명됩니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 행 중심의 매트릭스를 사용합니다.  벡터는 열 벡터가 아니라 행 벡터로 표현됩니다.  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매트릭스의 구조를 보여 줍니다.  
  
### 2차원 변환 매트릭스  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> 기본값: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> 기본값: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> 기본값: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> 기본값: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> 기본값: 0.0|1.0|  
  
 매트릭스 값을 조작하여 개체에 대해 회전, 배율 조정, 기울이기 및 이동\(위치 변환\) 작업을 수행할 수 있습니다.  예를 들어 세 번째 행의 첫 번째 열에 있는 값\(<xref:System.Windows.Media.Matrix.OffsetX%2A> 값\)을 100으로 변경하면 이를 사용하여 개체를 x축을 따라 100단위 이동할 수 있습니다.  세 번째 행의 두 번째 열에 있는 값을 3으로 변경하면 이를 사용하여 개체를 현재 높이보다 세 배 늘일 수 있습니다.  두 값을 모두 변경하면 개체가 x축을 따라 100단위 이동하며 높이는 계수 3만큼 늘어납니다.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 유사 변환만 지원하기 때문에 오른쪽 열의 값은 항상 0, 0, 1입니다.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 매트릭스 값을 직접 조작할 수도 있지만 내부 매트릭스 구조의 구성 방식을 모르더라도 개체를 변환할 수 있는 몇 개의 <xref:System.Windows.Media.Transform> 클래스도 제공합니다.  예를 들어 <xref:System.Windows.Media.ScaleTransform> 클래스를 사용하면 변환 매트릭스를 조작하는 대신 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성을 설정하여 개체의 배율을 조정할 수 있습니다.  마찬가지로 <xref:System.Windows.Media.RotateTransform> 클래스를 사용하면 <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성을 간단히 설정하여 개체를 회전할 수 있습니다.  
  
<a name="transformClassesSection"></a>   
## Transform 클래스  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 자주 사용되는 변환 작업에 사용할 수 있는 다음 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> 클래스를 제공합니다.  
  
|클래스|설명|예제|그림|  
|---------|--------|--------|--------|  
|<xref:System.Windows.Media.RotateTransform>|지정한 <xref:System.Windows.Media.RotateTransform.Angle%2A>만큼 요소를 회전합니다.|[개체 회전](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)||  
|<xref:System.Windows.Media.ScaleTransform>|지정한 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>에 따라 요소의 배율을 조정합니다.|[요소 배율 조정](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)||  
|<xref:System.Windows.Media.SkewTransform>|지정한 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 <xref:System.Windows.Media.SkewTransform.AngleY%2A>에 따라 요소를 기울입니다.|[요소 기울이기](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)||  
|<xref:System.Windows.Media.TranslateTransform>|지정한 <xref:System.Windows.Media.TranslateTransform.X%2A> 및 <xref:System.Windows.Media.TranslateTransform.Y%2A>에 따라 요소를 이동\(위치 변환\)합니다.|[요소 변환](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)||  
  
 더 복잡한 변환을 만들기 위해 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 다음 두 클래스를 제공합니다.  
  
|클래스|설명|예제|  
|---------|--------|--------|  
|<xref:System.Windows.Media.TransformGroup>|여러 <xref:System.Windows.Media.TransformGroup> 개체를 하나의 <xref:System.Windows.Media.Transform>으로 그룹화합니다. 이렇게 그룹화된 개체는 변환 속성에 적용할 수 있습니다.|[개체에 다중 변환 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|다른 <xref:System.Windows.Media.Transform> 클래스에서 제공하지 않는 사용자 지정 변환을 만듭니다.  <xref:System.Windows.Media.MatrixTransform>을 사용할 때는 매트릭스를 직접 조작합니다.|[MatrixTransform을 사용하여 사용자 지정 변환 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 변환도 제공합니다.  자세한 내용은 <xref:System.Windows.Media.Media3D.Transform3D> 클래스를 참조하십시오.  
  
<a name="transformationproperties"></a>   
## 일반적인 변환 속성  
 개체를 변환하는 방법 중 하나는 적절한 <xref:System.Windows.Media.Transform> 형식을 선언한 다음 개체의 변환 속성에 적용하는 것입니다.  개체 형식에 따라 변환 속성의 형식이 다릅니다.  다음 표는 자주 사용하는 몇 가지 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 형식 및 해당 변환 속성의 목록입니다.  
  
|형식|변환 속성|  
|--------|-----------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## 변환 및 좌표계  
 개체를 변환할 때에는 개체만 변환하는 것이 아니라 해당 개체가 존재하는 좌표 공간도 변환합니다.  기본적으로 변환은 대상 개체의 좌표계 원점인 \(0,0\)을 중심으로 합니다.  유일한 예외는 <xref:System.Windows.Media.TranslateTransform>입니다. 중심이 어디인지에 관계없이 변환 효과가 동일하기 때문에 <xref:System.Windows.Media.TranslateTransform>에는 설정할 중심 속성이 없습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Shapes.Rectangle> 요소\(<xref:System.Windows.FrameworkElement>의 한 형식\)를 기본 중심\(0,0\)을 기준으로 45도 회전합니다.  다음 그림에서는 회전의 효과를 보여 줍니다.  
  
 ![&#40;0,0&#41; 점을 기준으로 45도 회전시킨 FrameworkElement](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm\_FE\_rotated\_about\_upperleft\_corner")  
점 \(0,0\)을 중심으로 45도 회전된 사각형 요소  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 기본적으로 요소는 왼쪽 위 모퉁이인 \(0,0\)을 중심으로 회전합니다.  <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform> 및 <xref:System.Windows.Media.SkewTransform> 클래스는 변환을 적용할 점을 지정할 수 있는 CenterX 및 CenterY 속성을 제공합니다.  
  
 다음 예제에서도 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Shapes.Rectangle> 요소를 45도 회전하지만 이번에는 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성이 <xref:System.Windows.Media.RotateTransform>의 중심이 \(25, 25\)이도록 설정됩니다.  다음 그림에서는 회전의 효과를 보여 줍니다.  
  
 ![&#40;25, 25&#41; 점을 기준으로 45도 회전시킨 기하 도형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm\_FE\_rotated\_about\_center")  
점 \(25, 25\)를 중심으로 45도 회전된 사각형 요소  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## FrameworkElement 변환  
 <xref:System.Windows.FrameworkElement>에 변환을 적용하려면 <xref:System.Windows.Media.Transform>을 만든 다음 <xref:System.Windows.FrameworkElement> 클래스가 제공하는 두 속성 중 하나에 적용합니다.  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – 레이아웃 과정 전에 적용되는 변환.  변환이 적용되면 레이아웃 시스템에서 요소의 변환된 크기와 위치를 처리합니다.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> – 요소의 모양을 수정하지만 레이아웃 과정이 완료된 후 적용되는 변환.  <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성 대신 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용하면 성능을 높일 수 있습니다.  
  
 어떤 속성을 사용해야 할까요?  성능을 높일 수 있으므로 가능하면, <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용하는 것이 좋습니다. 특히 애니메이션이 적용된 <xref:System.Windows.Media.Transform> 개체를 사용할 때는 더욱 그렇습니다.  배율 조정, 회전 또는 기울이기를 수행할 때와 요소의 변환된 크기를 조정하기 위해 요소의 부모가 필요할 때는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성을 사용하십시오.  하지만 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성과 함께 사용하는 경우 <xref:System.Windows.Media.TranslateTransform> 개체는 요소에 아무런 효과를 미치지 않는 것처럼 보입니다.  이는 레이아웃 시스템에서 처리 도중 변환된 요소를 원래 위치로 되돌리기 때문입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서의 레이아웃에 대한 자세한 내용은 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md) 개요를 참조하십시오.  
  
<a name="exampleRotateAnElement45degSection"></a>   
## 예제: FrameworkElement를 45도 회전  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 단추를 시계 방향으로 45도 회전합니다.  이 단추는 다른 두 단추가 있는 <xref:System.Windows.Controls.StackPanel>에 포함되어 있습니다.  
  
 기본적으로 <xref:System.Windows.Media.RotateTransform>은 점 \(0, 0\)을 기준으로 회전합니다.  예제에서는 중심 값을 지정하지 않기 때문에 단추는 왼쪽 위 모퉁이인 점 \(0, 0\)을 기준으로 회전합니다.  <xref:System.Windows.Media.RotateTransform>이 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용됩니다.  다음 그림에서는 이 변환의 결과를 보여 줍니다.  
  
 ![RenderTransform을 사용하여 변환된 단추](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
왼쪽 위 모퉁이를 기준으로 시계 방향으로 45도 회전  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 다음 예제에서도 <xref:System.Windows.Media.RotateTransform>을 사용하여 단추를 시계 방향으로 45도 회전하지만 여기에서는 단추의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A>을 \(0.5, 0.5\)로 설정합니다.  <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성의 값은 단추 크기에 상대적입니다.  그 결과, 회전은 왼쪽 위 모퉁이가 아니라 단추의 중심에 대해 적용됩니다.  다음 그림에서는 이 변환의 결과를 보여 줍니다.  
  
 ![가운데를 중심으로 변환된 단추](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
가운데를 중심으로 시계 방향으로 45도 회전  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 다음 예제에서는 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 대신 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성을 사용하여 단추를 회전합니다.  이 경우 변환은 단추의 레이아웃에 영향을 미치며 이로 인해 레이아웃 시스템의 전체 전달이 트리거됩니다.  그 결과, 단추는 회전한 다음 그 크기가 변경되기 때문에 위치가 재조정됩니다.  다음 그림에서는 이 변환의 결과를 보여 줍니다.  
  
 ![LayoutTransform을 사용하여 변환된 단추](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm\_LayoutTransform")  
LayoutTransform을 사용한 단추 회전  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## 변환에 애니메이션 효과 주기  
 <xref:System.Windows.Media.Animation.Animatable> 클래스에서 상속되는 <xref:System.Windows.Media.Transform> 클래스에는 애니메이션 효과를 줄 수 있습니다.  <xref:System.Windows.Media.Transform>에 애니메이션 효과를 주려면 애니메이션 효과를 줄 속성에 호환 가능한 형식의 애니메이션을 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>과 함께 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Controls.Button>이 클릭되면 제자리에서 회전하도록 만듭니다.  
  
 [!code-xml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  애니메이션에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
<a name="freezable_features"></a>   
## Freezable 기능  
 <xref:System.Windows.Media.Transform> 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속되므로 몇 가지 특수한 기능을 제공합니다. 예를 들어 <xref:System.Windows.Media.Transform> 개체를 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)로 선언하거나, 여러 개체 간에 공유하거나, 읽기 전용으로 설정하여 성능을 향상시킬 수 있으며, 복제하거나, 스레드로부터 안전하게 보호할 수 있습니다.  <xref:System.Windows.Freezable> 개체가 제공하는 다양한 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Matrix>   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)