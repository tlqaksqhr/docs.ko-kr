---
title: "단색 및 그라데이션을 사용한 그리기 개요 | Microsoft Docs"
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
  - "브러시, 그라데이션으로 그리기"
  - "브러시, 단색으로 그리기"
  - "그라데이션, 그리기"
  - "그라데이션으로 그리기"
  - "단색으로 그리기"
  - "단색, 그리기"
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 단색 및 그라데이션을 사용한 그리기 개요
이 항목에서는 <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush> 및 <xref:System.Windows.Media.RadialGradientBrush> 개체를 사용하여 단색, 선형 그라데이션 및 방사형 그라데이션으로 그리는 방법을 설명합니다.  
  
   
  
<a name="solidcolor"></a>   
## 단색으로 영역 그리기  
 모든 플랫폼에서 가장 일반적으로 수행하는 작업 중 하나는 단일 <xref:System.Windows.Media.Color>로 영역을 그리는 것입니다.  이 작업을 수행하기 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 <xref:System.Windows.Media.SolidColorBrush> 클래스를 제공합니다.  다음 단원에서는 <xref:System.Windows.Media.SolidColorBrush>로 그릴 수 있는 여러 가지 방법을 설명합니다.  
  
<a name="solidcolorinxaml"></a>   
### "XAML"에서 SolidColorBrush 사용  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 단색으로 영역을 그리려면 다음 옵션 중 하나를 사용합니다.  
  
-   이름별로 미리 정의된 단색 브러시를 선택합니다.  예를 들어 단추의 <xref:System.Windows.Controls.Control.Background%2A>를 "Red" 또는 "MediumBlue"로 설정할 수 있습니다.  미리 정의된 다른 단색 브러시 목록은 <xref:System.Windows.Media.Brushes> 클래스의 정적 속성을 참조하십시오.  예를 들면 다음과 같습니다.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   단색으로 조합할 빨간색, 녹색 및 파란색의 양을 지정하여 32비트 색상표에서 색을 선택합니다.  32비트 팔레트에서 색을 지정하는 형식은 "*\#rrggbb*"입니다. 여기서 *rr*은 빨간색의 상대적인 양을 지정하는 2자리 16진수이며 *gg*는 녹색의 양을 지정하고 *bb*는 파란색의 양을 지정합니다.  색을 "\#*aarrggbb*"로도 지정할 수 있습니다. 여기서 *aa*는 색의 알파 값 또는 투명도를 지정합니다.  이 방법을 사용하면 부분적으로 투명한 색을 만들 수 있습니다.  다음 예제에서 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>는 16진수 표기법을 사용하여 완전히 불투명한 빨간색으로 설정됩니다.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   속성 태그 구문을 사용하여 <xref:System.Windows.Media.SolidColorBrush>를 설명합니다.  보다 자세한 이 구문을 사용하면 브러시의 불투명도와 같은 추가 설정을 지정할 수 있습니다.  다음 예제에서 두 <xref:System.Windows.Controls.Button> 요소의 <xref:System.Windows.Controls.Control.Background%2A> 속성은 완전히 불투명한 빨간색으로 설정됩니다.  첫 번째 브러시의 색은 미리 정의된 색 이름을 사용하여 설명되고  두 번째 브러시의 색은 16진수 표기법을 사용하여 설명됩니다.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### 코드에서 SolidColorBrush를 사용하여 그리기  
 코드에서 단색으로 영역을 그리려면 다음 옵션 중 하나를 사용합니다.  
  
-   <xref:System.Windows.Media.Brushes> 클래스에서 제공하는 미리 정의된 브러시 중 하나를 사용합니다.  다음 예제에서 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>는 <xref:System.Windows.Media.Brushes.Red%2A>로 설정됩니다.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   <xref:System.Windows.Media.SolidColorBrush>를 만들고 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성을 <xref:System.Windows.Media.Color> 구조체를 사용하여 설정합니다.  <xref:System.Windows.Media.Colors> 클래스의 미리 정의된 색을 사용하거나 정적 <xref:System.Windows.Media.Color.FromArgb%2A> 메서드를 사용하여 <xref:System.Windows.Media.Color>를 만들 수 있습니다.  
  
     다음 예제에서는 미리 정의된 색을 사용하여 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성을 설정하는 방법을 보여 줍니다.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 정적 <xref:System.Windows.Media.Color.FromArgb%2A>를 사용하면 색의 [알파](GTMT), 빨간색, 녹색 및 파란색 값을 지정할 수 있습니다.  이러한 값 각각의 일반적인 범위는 0\-255입니다.  예를 들어 [알파](GTMT) 값 0은 색이 완전히 투명함을 나타내며 값 255는 색이 완전히 불투명함을 나타냅니다.  마찬가지로 빨간색 값 0은 색에 전혀 빨간색이 없음을 나타내며 값 255는 색에 최대한의 빨간색이 있음을 나타냅니다.  다음 예제에서는 알파, 빨간색, 녹색 및 파란색 값을 지정하여 브러시의 색을 설명합니다.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 색을 지정하는 다른 방법은 <xref:System.Windows.Media.Color> 참조 항목을 참조하십시오.  
  
<a name="gradient"></a>   
## 그라데이션으로 영역 그리기  
 그라데이션 브러시는 축을 따라 서로 혼합되는 여러 가지 색으로 영역을 그립니다.  이러한 브러시를 통해 명암 효과를 만들어 컨트롤에 3차원 느낌을 줄 수 있습니다.  또한 유리, 크롬, 물 및 기타 부드러운 표면을 시뮬레이션할 수도 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 <xref:System.Windows.Media.LinearGradientBrush> 및 <xref:System.Windows.Media.RadialGradientBrush>라는 두 가지 그라데이션 브러시 형식을 제공합니다.  
  
<a name="lineargradientbrush"></a>   
## 선형 그라데이션  
 <xref:System.Windows.Media.LinearGradientBrush>는 하나의 선, 즉 그라데이션 축을 따라 정의된 그라데이션으로 영역을 그립니다.  <xref:System.Windows.Media.GradientStop> 개체를 사용하여 그라데이션 축을 따라 그라데이션의 색과 해당 위치를 지정합니다.  가로 및 세로 그라데이션을 만들고 그라데이션 방향을 반대로 바꿀 수 있도록 하는 그라데이션 축을 수정할 수도 있습니다.  그라데이션 축은 다음 단원에서 설명합니다.  기본적으로 대각선 그라데이션이 만들어집니다.  
  
 다음 예제에서는 네 가지 색을 사용하여 선형 그라데이션을 만드는 코드를 보여 줍니다.  
  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 이 코드는 다음과 같은 그라데이션을 생성합니다.  
  
 ![대각선 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diaglgradient-nolabel.png "wcpsdk\_graphicsmm\_diaglgradient\_nolabel")  
  
 **참고:** 이 항목의 그라데이션 예제에서는 시작점과 끝점을 설정하기 위해 기본 좌표계를 사용합니다.  기본 좌표계는 경계 상자에 상대적입니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.  <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성을 값 <xref:System.Windows.Media.BrushMappingMode>로 설정하여 이 좌표계를 변경할 수 있습니다.  절대 좌표계는 경계 상자에 상대적이지 않으며  값이 로컬 공간에서 직접 해석됩니다.  
  
 <xref:System.Windows.Media.GradientStop>은 그라데이션 브러시의 기본 빌딩 블록입니다.  그라데이션 중지점은 <xref:System.Windows.Media.GradientStop.Offset%2A>에서 그라데이션 축을 따라 <xref:System.Windows.Media.GradientStop.Color%2A>를 지정합니다.  
  
-   그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Color%2A> 속성은 그라데이션 중지점의 색을 지정합니다.  미리 정의된 색\(<xref:System.Windows.Media.Colors> 클래스에서 제공\)을 사용하거나 ScRGB 또는 ARGB 값을 지정하여 색을 설정할 수 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 16진수 표기법을 사용하여 색을 설명할 수도 있습니다.  자세한 내용은 <xref:System.Windows.Media.Color> 구조체를 참조하십시오.  
  
-   그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Offset%2A> 속성은 그라데이션 축에서 그라데이션 중지점 색의 위치를 지정합니다.  오프셋은 0\-1 범위의 <xref:System.Double>입니다.  그라데이션 중지점의 오프셋 값이 0에 가까울수록 색이 그라데이션의 시작 부분에 가까워집니다.  또한 그라데이션의 오프셋 값이 1에 가까울수록 색이 그라데이션의 끝 부분에 가까워집니다.  
  
 그라데이션 중지점 사이에 있는 각 지점의 색은 두 경계 그라데이션 중지점으로 지정한 색의 조합으로 선형 보간됩니다.  다음 그림에서는 이전 예제의 그라데이션 중지점을 강조 표시합니다.  원은 그라데이션 중지점의 위치를 표시하고 파선은 그라데이션 축을 표시합니다.  
  
 ![선형 그라데이션에서 그라데이션 중지](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk\_graphicsmm\_4gradientstops")  
  
 첫 번째 그라데이션 중지점은 `0.0`의 오프셋에서 노란색을 지정합니다.  두 번째 그라데이션 중지점은 `0.25`의 오프셋에서 빨간색을 지정합니다.  이러한 두 중지점 사이의 지점은 그라데이션 축을 따라 왼쪽에서 오른쪽으로 이동하면서 점차적으로 노란색에서 빨간색으로 변경됩니다.  세 번째 그라데이션 중지점은 `0.75`의 오프셋에서 파란색을 지정합니다.  두 번째와 세 번째 그라데이션 중지점 사이의 지점은 점차적으로 빨간색에서 파란색으로 변경됩니다.  네 번째 그라데이션 중지점은 `1.0`의 오프셋에서 황록색을 지정합니다.  세 번째와 네 번째 그라데이션 중지점 사이의 지점은 점차적으로 파란색에서 황록색으로 변경됩니다.  
  
<a name="gradientaxis"></a>   
### 그라데이션 축  
 앞에서도 언급했듯이 선형 그라데이션 브러시의 그라데이션 중지점은 하나의 선, 즉 그라데이션 축을 따라 배치됩니다.  브러시의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 속성을 사용하여 선의 방향과 크기를 변경할 수 있습니다.  브러시의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>를 조작하면 가로 및 세로 그라데이션을 만들고, 그라데이션 방향을 반대로 바꾸고, 그라데이션 범위를 압축하는 등의 작업을 수행할 수 있습니다.  
  
 기본적으로 선형 그라데이션 브러시의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>는 그리는 영역에 상대적입니다.  \(0, 0\) 지점은 그리는 영역의 왼쪽 위 모퉁이를 나타내고 \(1, 1\)은 그리는 영역의 오른쪽 아래 모퉁이를 나타냅니다.  <xref:System.Windows.Media.LinearGradientBrush>의 기본 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>는 \(0,0\)이고 기본 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>는 \(1,1\)입니다. 이 경우 왼쪽 위 모퉁이에서 시작하여 그리는 영역의 오른쪽 아래 모퉁이로 확장되는 대각선 그라데이션이 만들어집니다.  다음 그림에서는 기본 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>를 사용하여 선형 그라데이션 브러시의 그라데이션 축을 보여 줍니다.  
  
 ![대각선 선형 그라데이션의 그라데이션 축](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk\_graphicsmm\_diagonalgradientaxis")  
  
 다음 예제에서는 브러시의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>를 지정하여 가로 그라데이션을 만드는 방법을 보여 줍니다.  그라데이션 중지점은 이전 예제의 그라데이션 중지점과 같습니다. 여기서는 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>만 변경하여 그라데이션을 대각선에서 가로로 변경했습니다.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 다음 그림에서는 만들어진 그라데이션을 보여 줍니다.  그라데이션 축은 파선으로 표시되고 그라데이션 중지점은 원으로 표시됩니다.  
  
 ![가로 선형 그라데이션의 그라데이션 축](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-horizontalgradient.png "wcpsdk\_graphicsmm\_horizontalgradient")  
  
 다음 예제에서는 세로 그라데이션을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 다음 그림에서는 만들어진 그라데이션을 보여 줍니다.  그라데이션 축은 파선으로 표시되고 그라데이션 중지점은 원으로 표시됩니다.  
  
 ![세로 그라데이션의 그라데이션 축](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-verticalgradient.png "wcpsdk\_graphicsmm\_verticalgradient")  
  
<a name="radialgradients"></a>   
## 방사형 그라데이션  
 <xref:System.Windows.Media.LinearGradientBrush>처럼 <xref:System.Windows.Media.RadialGradientBrush>는 축을 따라 함께 혼합되는 색으로 영역을 그립니다.  이전 예제에서는 선형 그라데이션 브러시의 축이 직선임을 보여 주었습니다.  그러나 방사형 그라데이션 브러시의 축은 원으로 정의되며 해당 색이 원점에서 바깥쪽으로 "방사"합니다.  
  
 다음 예제에서는 사각형의 내부를 그리기 위해 방사형 그라데이션 브러시가 사용됩니다.  
  
 [!code-xml[GradientBrushExamples_snip#RadialGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  브러시의 그라데이션 중지점이 강조 표시되었습니다.  결과는 다르지만 이 예제의 그라데이션 중지점은 이전 선형 그라데이션 브러시 예제의 그라데이션 중지점과 같습니다.  
  
 ![방사형 그라데이션에서 중지된 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
 <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>은 방사형 그라데이션 브러시의 그라데이션 축에 대한 시작점을 지정합니다.  그라데이션 축은 그라데이션 원점에서 그라데이션 원으로 방사합니다.  브러시의 그라데이션 원은 해당 <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> 및 <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> 속성으로 정의합니다.  
  
 다음 그림에서는 다양한 <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> 및 <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> 설정이 지정된 여러 가지 방사형 그라데이션을 보여 줍니다.  
  
 ![RadialGradientBrush 설정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-originscirclesandradii.png "wcpsdk\_graphicsmm\_originscirclesandradii")  
다양한 GradientOrigin, Center, RadiusX 및 RadiusY 설정이 지정된 RadialGradientBrush  
  
<a name="specifyinggradientcolors"></a>   
## 투명하거나 부분적으로 투명한 그라데이션 중지점 지정  
 그라데이션 중지점은 불투명도 속성을 제공하지 않으므로 태그에서 [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] 16진수 표기법을 사용하여 색의 알파 채널을 지정하거나 <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName> 메서드를 사용하여 투명하거나 부분적으로 투명한 그라데이션 중지점을 만들어야 합니다.  다음 단원에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드에서 부분적으로 투명한 그라데이션 중지점을 만드는 방법을 보여 줍니다.  전체 브러시의 불투명도를 설정하는 방법에 대한 자세한 내용은 [브러시의 불투명도 지정](#brushesAndOpacity) 단원을 참조하십시오.  
  
<a name="argbsyntax"></a>   
### "XAML"에서 색 불투명도 지정  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] 16진수 표기법을 사용하여 개별 색의 불투명도를 지정합니다.  [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] 16진수 표기법에는 다음 구문이 사용됩니다.  
  
 `#`**aa** *rrggbb*  
  
 위 줄에서 *aa*는 색의 불투명도를 지정하는 데 사용되는 2자리 16진수 값을 나타냅니다.  *rr*, *gg* 및 *bb*는 각각 색에서 빨간색, 녹색 및 파란색의 양을 지정하는 데 사용되는 2자리 16진수 값을 나타냅니다.  각 16진수는 0\-9 또는 A\-F의 값을 가집니다.  0이 가장 작은 값이고 F가 가장 큰 값입니다.  알파 값이 00이면 색이 완전히 투명해지고 알파 값이 FF이면 색이 완전히 불투명해집니다.  다음 예제에서는 두 개의 색을 지정하기 위해 16진수 [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] 표기법이 사용됩니다.  첫 번째는 부분적으로 투명\(알파 값: x20\)하고 두 번째는 완전히 불투명합니다.  
  
 [!code-xml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### 코드에서 색 불투명도 지정  
 코드를 사용할 경우 정적 <xref:System.Windows.Media.Color.FromArgb%2A> 메서드를 사용하면 색을 만들 때 알파 값을 지정할 수 있습니다.  이 메서드는 <xref:System.Byte> 형식의 네 가지 매개 변수를 사용합니다.  첫 번째 매개 변수는 색의 알파 채널을 지정하고 다른 세 매개 변수는 빨간색, 녹색 및 파란색 값을 지정합니다.  각 값은 0 이상 255 이하여야 합니다.  알파 값이 0이면 색이 완전히 투명해지고 알파 값이 255이면 색이 완전히 불투명해집니다.  다음 예제에서는 두 개의 색을 생성하기 위해 <xref:System.Windows.Media.Color.FromArgb%2A> 메서드가 사용됩니다.  첫 번째 색은 부분적으로 투명\(알파 값: 32\)하고 두 번째 색은 완전히 불투명합니다.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 ScRGB 값을 사용하여 색을 만들 수 있도록 하는 <xref:System.Windows.Media.Color.FromScRgb%2A> 메서드를 사용할 수도 있습니다.  
  
<a name="otherbrushes"></a>   
## 이미지, 그림, 시각적 표시 및 패턴으로 그리기  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush> 클래스를 사용하면 이미지, 그림 및 시각적 표시로 영역을 그릴 수 있습니다.  이미지, 그림 및 패턴으로 그리는 방법에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)