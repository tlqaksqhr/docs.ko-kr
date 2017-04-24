---
title: "이미징 개요 | Microsoft Docs"
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
  - "이미지 변환"
  - "이미지 자르기"
  - "이미지 형식 디코딩"
  - "이미지 표시"
  - "이미지 형식 인코딩"
  - "이미지의 형식 디코딩"
  - "이미지의 형식 인코딩"
  - "이미지 메타데이터"
  - "이미지, 이미징 정보"
  - "이미징 API"
  - "메타데이터, 이미지"
  - "이미지로 그리기"
  - "이미지 회전"
  - "이미지 늘이기"
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# 이미징 개요
이 항목에서는 [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]에 대해 소개합니다.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]을 사용하여 개발자는 이미지를 표시하거나 변환하고 형식을 지정할 수 있습니다.  
  
   
  
<a name="_wpfImaging"></a>   
## WPF 이미징 구성 요소  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 매우 향상된 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 이미징 기능을 제공합니다.  비트맵을 표시하거나 공통 컨트롤에 이미지를 사용하는 등의 이미징 기능은 이전에는 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] 또는 [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)] 라이브러리에 의존했었습니다.  이러한 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]는 기준 이미징 기능은 제공하지만 코덱 확장성 및 고품질 이미지 지원 등과 같은 기능이 없습니다.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]는 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 및 [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]의 단점을 극복하고 응용 프로그램 내에서 이미지를 표시 및 사용하기 위한 새로운 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 집합을 제공하도록 다시 디자인되었습니다.  
  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에는 관리되는 구성 요소와 관리되지 않는 구성 요소를 사용하여 액세스할 수 있습니다.  관리되지 않는 구성 요소는 다음과 같은 기능을 제공합니다.  
  
-   새 이미지 형식 또는 독점적인 이미지 형식을 위한 확장성 모델  
  
-   [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)], 아이콘\(.ico\) 등의 네이티브 이미지 형식에 대한 성능 및 보안 개선  
  
-   채널당 최대 8비트\(픽셀당 32비트\)의 높은 비트 수준 이미지 데이터 유지  
  
-   안전한 이미지 배율 조정, 자르기 및 회전  
  
-   간단한 색 관리  
  
-   파일 내의 독점적 메타데이터 지원  
  
-   관리되는 구성 요소는 관리되지 않는 인프라를 활용하여 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], 애니메이션 및 그래픽과 같은 다른 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 기능과의 자연스러운 이미지 통합 기능을 제공합니다.  또한 관리되는 구성 요소는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 새로운 이미지 형식을 자동으로 인식하는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 이미징 코덱 확장성 모델을 활용합니다.  
  
 관리되는 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]의 대부분은 <xref:System.Windows.Media.Imaging?displayProperty=fullName> 네임스페이스에 들어 있습니다. 그러나 <xref:System.Windows.Media.ImageBrush> 및 <xref:System.Windows.Media.ImageDrawing>과 같은 일부 중요한 형식은 <xref:System.Windows.Media?displayProperty=fullName> 네임스페이스에 들어 있고, <xref:System.Windows.Controls.Image>는 <xref:System.Windows.Controls?displayProperty=fullName> 네임스페이스에 들어 있습니다.  
  
 이러한 항목은 관리되는 구성 요소에 대한 추가 정보를 제공합니다.  관리되지 않는 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에 대한 자세한 내용은 [Windows Imaging 구성 요소](_wic_lh) 설명서를 참조하십시오.  
  
<a name="_imageformats"></a>   
## WPF 이미지 형식  
 코덱은 특정 미디어 형식을 인코딩하거나 디코딩하는 데 사용됩니다.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에는 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 및 ICON 이미지 형식에 대한 코덱이 포함되어 있습니다.  이러한 각각의 코덱을 사용하여 응용 프로그램은 해당 이미지 형식을 디코딩하고 인코딩\(ICON 제외\)할 수 있습니다.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>는 이미지의 디코딩 및 인코딩에 사용되는 중요한 클래스입니다.  이는 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] 파이프라인의 기본 빌딩 블록으로, 특정 크기 및 해상도의 단일 상수 픽셀 집합을 나타냅니다.  <xref:System.Windows.Media.Imaging.BitmapSource>는 여러 프레임 이미지의 개별 프레임일 수도 있고 <xref:System.Windows.Media.Imaging.BitmapSource>에 대해 수행된 변환의 결과일 수도 있습니다.  이는 <xref:System.Windows.Media.Imaging.BitmapFrame>과 같은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 이미징에 사용되는 많은 기본 클래스의 부모입니다.  
  
 <xref:System.Windows.Media.Imaging.BitmapFrame>은 이미지 형식의 실제 비트맵 데이터를 저장하는 데 사용됩니다.  많은 이미지 형식이 하나의 <xref:System.Windows.Media.Imaging.BitmapFrame>만을 지원하지만 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 및 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]는 이미지당 여러 개의 프레임을 지원합니다.  프레임은 디코더에서 입력 데이터로 사용되며, 인코더에 전달되어 이미지 파일을 만듭니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapSource>에서 <xref:System.Windows.Media.Imaging.BitmapFrame>을 만든 다음 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 이미지에 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[BitmapFrameExample#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### 이미지 형식 디코딩  
 이미지 디코딩은 이미지 형식을 시스템에서 사용할 수 있는 이미지 데이터로 변환하는 것입니다.  그런 다음 이미지 데이터는 다른 형식을 표시 또는 처리하거나 다른 형식으로 인코딩하는 데 사용될 수 있습니다.  디코더 선택은 이미지 형식에 따라 달라집니다.  코덱은 특정 디코더를 지정하지 않은 한 자동으로 선택됩니다.  [WPF에서 이미지 표시](#_displayingimages) 단원의 예제에서는 자동 디코딩을 보여 줍니다.  관리되지 않는 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] 인터페이스를 사용하여 개발되고 시스템에 등록된 사용자 지정 형식 디코더는 자동으로 디코더 선택에 포함됩니다.  따라서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 사용자 지정 형식이 자동으로 표시됩니다.  
  
 다음 예제에서는 비트맵 디코더를 사용하여 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 형식 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### 이미지 형식 인코딩  
 이미지 인코딩은 이미지 데이터를 특정 이미지 형식으로 변환하는 것입니다.  인코딩된 이미지 데이터는 새로운 이미지 파일을 만드는 데 사용될 수 있습니다.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]는 위에서 설명한 각 이미지 형식에 대한 인코더를 제공합니다.  
  
 다음 예제에서는 인코더를 사용하여 새로 만든 비트맵 이미지를 저장하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## WPF에서 이미지 표시  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램에서 이미지를 표시하는 방법에는 몇 가지가 있습니다.  이미지는 <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 표시하거나, <xref:System.Windows.Media.ImageBrush>를 사용하여 시각적 요소로 그리거나, <xref:System.Windows.Media.ImageDrawing>을 사용하여 그릴 수 있습니다.  
  
### 이미지 컨트롤 사용  
 <xref:System.Windows.Controls.Image>는 프레임워크 요소로, 응용 프로그램에서 이미지를 표시할 수 있는 기본적인 방법입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.Image>는 특성 구문과 속성 구문에서 사용될 수 있습니다.  다음 예제에서는 특성 구문과 속성 태그 구문을 모두 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 많은 예제에서 <xref:System.Windows.Media.Imaging.BitmapImage> 개체를 사용하여 이미지 파일을 참조합니다.  <xref:System.Windows.Media.Imaging.BitmapImage>는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 로딩을 위해 최적화된 특수화된 <xref:System.Windows.Media.Imaging.BitmapSource>로, 이미지를 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A>로 표시하는 간단한 방법입니다.  
  
 다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage>는 여러 속성에 대한 초기화를 최적화하기 위해 <xref:System.ComponentModel.ISupportInitialize> 인터페이스를 구현합니다.  속성 변경은 개체 초기화 중에만 수행할 수 있습니다.  초기화가 시작되었음을 신호로 보내려면 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>를 호출하고, 초기화가 완료되었음을 신호로 보내려면 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>를 호출합니다.  초기화가 되고 나면 속성 변경이 무시됩니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### 이미지의 회전, 변환 및 자르기  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 사용자가 <xref:System.Windows.Media.Imaging.BitmapImage>의 속성을 사용하거나 <xref:System.Windows.Media.Imaging.CroppedBitmap> 또는 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>과 같은 추가 <xref:System.Windows.Media.Imaging.BitmapSource> 개체를 사용하여 이미지를 변환할 수 있습니다.  이러한 이미지 변환에는 이미지의 배율을 조정하거나 이미지를 회전하거나 이미지의 픽셀 형식을 변경하거나 이미지를 자르는 작업이 포함됩니다.  
  
 이미지 회전은 <xref:System.Windows.Media.Imaging.BitmapImage>의 <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> 속성을 사용하여 수행됩니다.  회전은 90도 단위로 증가하는 방식으로만 수행됩니다.  다음 예제에서 이미지는 90도 회전합니다.  
  
 [!code-xml[ImageElementExample#TransformedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 이미지를 회색조와 같은 다른 픽셀 형식으로 변환할 때는 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>을 사용합니다.  다음 예제에서 이미지는 <xref:System.Windows.Media.PixelFormats.Gray4%2A>로 변환됩니다.  
  
 [!code-xml[ImageElementExample_snip#ConvertedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 이미지를 잘라내는 경우 <xref:System.Windows.Controls.Image>의 <xref:System.Windows.UIElement.Clip%2A> 속성 또는 <xref:System.Windows.Media.Imaging.CroppedBitmap>을 사용할 수 있습니다.  일반적으로 이미지의 일부분만 표시하려는 경우에는 <xref:System.Windows.UIElement.Clip%2A>을 사용해야 합니다.  잘라낸 이미지를 인코딩 및 저장해야 하는 경우 <xref:System.Windows.Media.Imaging.CroppedBitmap>을 사용해야 합니다.  다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>를 사용하는 Clip 속성을 사용하여 이미지를 자릅니다.  
  
 [!code-xml[ImageElementExample_snip#CroppedXAMLUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### 이미지 늘이기  
 <xref:System.Windows.Controls.Image.Stretch%2A> 속성은 해당 컨테이너를 채우도록 이미지를 늘이는 방법을 제어합니다.  <xref:System.Windows.Controls.Image.Stretch%2A> 속성은 <xref:System.Windows.Media.Stretch> 열거형으로 정의되는 다음과 같은 값을 사용합니다.  
  
-   <xref:System.Windows.Media.Stretch>: 이미지를 늘려 출력 영역을 채우지 않습니다.  이미지가 출력 영역보다 큰 경우 이미지를 출력 영역에 그리고 맞지 않는 부분은 잘라냅니다.  
  
-   <xref:System.Windows.Media.Stretch>: 출력 영역에 맞게 이미지 배율을 조정합니다.  이미지의 높이와 너비의 배율이 개별적으로 조정되기 때문에 이미지의 원래 가로 세로 비율이 유지되지 않을 수 있습니다.  즉, 출력 컨테이너를 완벽하게 채우기 위해 이미지가 휘어질 수 있습니다.  
  
-   <xref:System.Windows.Media.Stretch>: 출력 영역 안에 이미지가 완전히 들어오도록 이미지 배율을 조정합니다.  이미지의 가로 세로 비율이 유지됩니다.  
  
-   <xref:System.Windows.Media.Stretch>: 이미지의 원래 가로 세로 비율을 유지하면서 출력 영역을 완전하게 채우도록 이미지 배율을 조정합니다.  
  
 다음 예제에서는 사용 가능한 각각의 <xref:System.Windows.Media.Stretch> 열거형을 <xref:System.Windows.Controls.Image>에 적용합니다.  
  
 다음 이미지에서는 예제의 출력을 보여 주고 다른 <xref:System.Windows.Controls.Image.Stretch%2A> 설정을 이미지에 적용했을 때 미치는 영향을 보여 줍니다.  
  
 ![여러 TileBrush Stretch 설정](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
여러 가지 늘이기 설정  
  
 [!code-xml[ImageElementExample_snip#ImageStretchExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### 이미지 그리기  
 응용 프로그램에서 이미지는 <xref:System.Windows.Media.Brush>를 사용한 그리기로 표시될 수도 있습니다.  브러시를 사용하면 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르기까지 모든 것을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 개체를 그릴 수 있습니다.  이미지를 그리려면 <xref:System.Windows.Media.ImageBrush>를 사용합니다.  <xref:System.Windows.Media.ImageBrush>는 콘텐츠를 비트맵 이미지로 정의하는 <xref:System.Windows.Media.TileBrush> 형식입니다.  <xref:System.Windows.Media.ImageBrush>는 해당 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 속성에 지정된 단일 이미지를 표시합니다.  이미지 왜곡을 방지하고 패턴 및 기타 효과를 만드는 동시에 이미지를 늘이고 정렬하고 바둑판식으로 배열하는 방법을 제어할 수 있습니다.  다음 그림에서는 <xref:System.Windows.Media.ImageBrush>로 얻을 수 있는 몇 가지 효과를 보여 줍니다.  
  
 ![ImageBrush 출력 예제](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
이미지 브러시는 도형, 컨트롤, 텍스트 등을 채울 수 있음  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>를 사용하여 이미지가 있는 단추의 배경을 그리는 방법을 보여 줍니다.  
  
 [!code-xml[UsingImageBrush#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 <xref:System.Windows.Media.ImageBrush> 및 이미지 그리기에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
<a name="_metadata"></a>   
## 이미지 메타데이터  
 일부 이미지 파일에는 해당 파일의 내용이나 특성을 설명하는 메타데이터가 있습니다.  예를 들어 대부분의 디지털 사진에 포함된 메타데이터를 분석하면 사진 촬영에 사용한 카메라의 제조업체와 모델을 알 수 있습니다.  각 이미지 형식은 메타데이터를 다르게 처리하지만 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 지원되는 각 이미지 형식에 대한 메타데이터를 일관된 방식으로 저장하고 검색합니다.  
  
 메타데이터는 <xref:System.Windows.Media.Imaging.BitmapSource> 개체의 <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> 속성을 통해 액세스할 수 있습니다.  <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>는 이미지가 갖고 있는 모든 메타데이터를 포함하는 <xref:System.Windows.Media.Imaging.BitmapMetadata> 개체를 반환합니다.  이 데이터는 하나의 메타데이터 스키마일 수도 있고 여러 스키마가 조합된 것일 수도 있습니다.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt\(PNG 텍스트 데이터\), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)]. [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)] 등의 이미지 메타데이터 스키마를 지원합니다.  
  
 메타데이터를 읽는 과정을 단순화하기 위해 <xref:System.Windows.Media.Imaging.BitmapMetadata>는 <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> 및 <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>과 같이 쉽게 액세스할 수 있는 몇 가지 명명된 속성을 제공합니다.  이러한 명명된 속성 중 많은 수가 메타데이터 작성에도 사용될 수 있습니다.  메타데이터 쿼리 판독기를 통해 메타데이터 읽기에 대한 추가 지원을 받을 수 있습니다.  <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> 메서드는 *"\/app1\/exif\/"*와 같은 문자열 쿼리를 제공하여 메타데이터 쿼리 판독기를 검색하는 데 사용됩니다.  다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>를 사용하여 *"\/Text\/Description"* 위치에 저장된 텍스트를 구하는 방법을 보여 줍니다.  
  
 [!code-cpp[BitmapMetadata#GetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 메타데이터를 작성하기 위해서는 메타데이터 쿼리 작성기를 사용합니다.  <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>는 쿼리 작성기를 구하고 원하는 값을 설정합니다.  다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>를 사용하여 *"\/Text\/Description"* 위치에 저장된 텍스트를 작성하는 방법을 보여 줍니다.  
  
 [!code-cpp[BitmapMetadata#SetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## 코덱 확장성  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]의 핵심 기능은 새로운 이미지 코덱에 대한 확장성 모델입니다.  이러한 관리되지 않는 인터페이스를 통해 코덱 개발자는 코덱과 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 통합하므로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 새로운 이미지 형식을 자동으로 사용할 수 있습니다.  
  
 확장성 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]의 샘플을 보려면 [Win32 Sample Codec](http://go.microsoft.com/fwlink/?LinkID=160052)을 참조하십시오.  이 샘플에서는 사용자 지정 이미지 형식을 위해 디코더와 인코더를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  시스템이 코덱을 인식하려면 코덱에 디지털 서명이 필요합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.Imaging.BitmapSource>   
 <xref:System.Windows.Media.Imaging.BitmapImage>   
 <xref:System.Windows.Controls.Image>   
 <xref:System.Windows.Media.Imaging.BitmapMetadata>   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Win32 샘플 Codec](http://go.microsoft.com/fwlink/?LinkID=160052)