---
title: 이미징 개요
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
caps.latest.revision: 32
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8715f04f6cdec84e74d53213c0a5a5ff360c7d28
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="imaging-overview"></a>이미징 개요
이 항목에서는 [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]를 소개합니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]를 사용하여 개발자는 이미지를 표시 및 변환하고 서식을 지정할 수 있습니다.  
  
  
<a name="_wpfImaging"></a>   
## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 내에서 향상된 이미징 기능을 제공합니다. 비트맵을 표시하거나 공용 컨트롤에서 이미지를 사용하는 것과 같은 이미징 기능에는 이전에는 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] 또는 [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)] 라이브러리가 필요했습니다. 이러한 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]는 기준 이미징 기능은 제공했지만 코덱 확장성 및 고품질 이미지 지원 등과 같은 기능이 없었습니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]는 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 및 [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]의 단점을 보완하고 응용 프로그램 내에서 이미지를 표시 및 사용하기 위한 새로운 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 집합을 제공하도록 다시 디자인되었습니다.  
  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에 액세스하는 방법에는 관리되는 구성 요소와 관리되지 않는 구성 요소의 두 가지 방법이 있습니다. 관리되지 않는 구성 요소는 다음과 같은 기능을 제공합니다.  
  
-   새롭거나 또는 독자적인 이미지 형식에 대한 확장성 모델  
  
-   [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] 및 아이콘(.ico)을 포함하는 네이티브 이미지 형식에 대한 향상된 성능 및 보안  
  
-   채널당 8비트(픽셀당 32비트)까지 높은 비트 수준의 이미지 데이터 보존  
  
-   비파괴 이미지 크기 조정, 자르기 및 회전  
  
-   단순화된 색 관리  
  
-   파일 내 독점 메타데이터에 대한 지원  
  
-   관리되는 구성 요소는 관리되지 않는 인프라를 활용하여 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], 애니메이션 및 그래픽 등의 기타 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 기능에 이미지를 원활하게 통합할 수 있도록 합니다. 관리 되는 구성 요소는 Windows Presentation Foundation (WPF) 이미징 코덱에 확장성 모델을 자동으로 새로운 이미지 형식 인식에서 점은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램입니다.  
  
 대부분의 관리 되는 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 에 <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> 네임 스페이스와 같은 몇 가지 중요 한 형식은 있지만 <xref:System.Windows.Media.ImageBrush> 및 <xref:System.Windows.Media.ImageDrawing> 에 <xref:System.Windows.Media?displayProperty=nameWithType> 네임 스페이스 및 <xref:System.Windows.Controls.Image> 는 에있는<xref:System.Windows.Controls?displayProperty=nameWithType> 네임 스페이스입니다.  
  
 이 항목에서는 관리되는 구성 요소에 대한 추가 정보를 제공합니다. 관리되지 않는 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에 대한 자세한 내용은 [관리되지 않는 WPF Imaging Component](https://msdn.microsoft.com/library/ee719902.aspx) 설명서를 참조하세요.  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>WPF 이미지 형식  
 코덱은 특정 미디어 형식을 인코딩하거나 디코딩하는 데 사용됩니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]는 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 및 ICON 이미지 형식에 대한 코덱을 포함합니다. 이러한 각 코덱을 사용하여 응용 프로그램은 ICON을 제외한 해당 이미지 형식을 디코딩 및 인코딩할 수 있습니다.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> 중요 한 클래스 디코딩 및 인코딩 이미지에 사용 됩니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] 파이프라인의 기본 구성 요소이며 픽셀의 단일 상수 집합을 특정 크기 및 해상도로 나타냅니다. A <xref:System.Windows.Media.Imaging.BitmapSource> 개별 프레임의 다중 프레임 이미지 될 수 있습니다 또는에서 수행 된 변환의 결과 수는 <xref:System.Windows.Media.Imaging.BitmapSource>합니다. 많은에 사용 되는 기본 클래스의 부모인 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 같은 이미징 <xref:System.Windows.Media.Imaging.BitmapFrame>합니다.  
  
 A <xref:System.Windows.Media.Imaging.BitmapFrame> 이미지 형식의 실제 비트맵 데이터를 저장 하는 데 사용 됩니다. 다양 한 이미지 형식에는 단일만 지원 <xref:System.Windows.Media.Imaging.BitmapFrame>하지만, 같은 형식 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 및 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 이미지 당 여러 프레임을 지원 합니다. 프레임은 디코더에서 입력 데이터로 사용되고 이미지 파일을 만들기 위해 인코더에 전달됩니다.  
  
 다음 예제에서는 어떻게는 <xref:System.Windows.Media.Imaging.BitmapFrame> 에서 만든는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 추가 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 이미지입니다.  
  
 [!code-csharp[BitmapFrameExample#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>이미지 형식 디코딩  
 이미지 디코딩은 이미지 형식을 시스템에서 사용할 수 있는 이미지 데이터로 변환하는 것입니다. 그런 후 이미지 데이터를 다른 형식으로 표시, 처리 또는 인코딩할 수 있습니다. 디코더를 선택할 때는 이미지 형식을 고려해야 합니다. 특정 디코더를 지정하지 않으면 코덱이 자동으로 선택됩니다. [WPF로 이미지 표시](#_displayingimages) 섹션의 예제는 자동 디코딩을 보여 줍니다. 관리되지 않는 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] 인터페이스를 사용하여 개발하고 시스템에 등록된 사용자 지정 형식 디코더는 디코더 선택 항목에 자동으로 포함됩니다. 이를 통해 사용자 지정 형식이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 자동으로 표시될 수 있습니다.  
  
 다음 예제에서는 비트맵 디코더를 사용하여 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 형식 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>이미지 형식 인코딩  
 이미지 인코딩은 이미지 데이터를 특정 이미지 형식으로 변환하는 것입니다. 인코딩된 이미지 데이터는 새 이미지 파일을 만드는 데 사용할 수 있습니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 위에 설명된 각 이미지 형식에 대한 인코더를 제공합니다.  
  
 다음 예제에서는 인코더를 사용하여 새로 만든 비트맵 이미지를 저장하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>WPF로 이미지 표시  
 Windows Presentation Foundation (WPF) 응용 프로그램에서 이미지를 표시 하는 방법은 여러 가지가 있습니다. 사용 하 여 이미지를 표시할 수 있습니다는 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하는 visual에 그릴는 <xref:System.Windows.Media.ImageBrush>, 또는 사용 하 여 그린는 <xref:System.Windows.Media.ImageDrawing>합니다.  
  
### <a name="using-the-image-control"></a>Image 컨트롤 사용  
 <xref:System.Windows.Controls.Image> 프레임 워크 요소 및 응용 프로그램에서 이미지를 표시 하는 기본적인 방법은 됩니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> 두 가지 방법으로; 특성 구문 또는 속성 구문을 사용할 수 있습니다. 다음 예제에서는 특성 구문 및 속성 태그 구문 둘 다를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다. 특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 많은 예제를 사용 하는 <xref:System.Windows.Media.Imaging.BitmapImage> 이미지 파일을 참조할 개체입니다. <xref:System.Windows.Media.Imaging.BitmapImage> 특수화 된 <xref:System.Windows.Media.Imaging.BitmapSource> 에 최적화 되 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 로드 및 이미지를 표시 하는 쉬운 방법은 <xref:System.Windows.Controls.Image.Source%2A> 의 <xref:System.Windows.Controls.Image> 제어 합니다.  
  
 다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> 구현 하는 <xref:System.ComponentModel.ISupportInitialize> 여러 속성에 대 한 초기화를 최적화 하는 인터페이스입니다. 개체 초기화 동안에만 속성 변경이 발생할 수 있습니다. 호출 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 신호를 보내 해당 초기화가 시작 하 고 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 신호를 보내 해당 초기화가 완료 합니다. 일단 초기화되면 속성 변경은 무시됩니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>이미지 회전, 변환 및 자르기  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 사용자가 속성을 사용 하 여 이미지를 변형할 수 있도록 <xref:System.Windows.Media.Imaging.BitmapImage> 또는 추가 사용 하 여 <xref:System.Windows.Media.Imaging.BitmapSource> 와 같은 개체 <xref:System.Windows.Media.Imaging.CroppedBitmap> 또는 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>합니다. 이러한 이미지 변환은 이미지 크기를 조정 또는 이미지를 회전하거나, 이미지의 픽셀 형식을 변경하거나, 이미지를 잘라낼 수 있습니다.  
  
 이미지 회전 사용 하 여 수행 되는 <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> 속성 <xref:System.Windows.Media.Imaging.BitmapImage>합니다. 회전은 90도 단위로만 수행할 수 있습니다. 다음 예제에서 이미지는 90도 회전됩니다.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 회색조 이루어진다는 같은 이미지를 다른 픽셀 형식 변환 사용 하 여 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>합니다. 다음 예에서는 이미지도 변환 됩니다 <xref:System.Windows.Media.PixelFormats.Gray4%2A>합니다.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 하거나 이미지를 자르려면는 <xref:System.Windows.UIElement.Clip%2A> 속성 <xref:System.Windows.Controls.Image> 또는 <xref:System.Windows.Media.Imaging.CroppedBitmap> 사용할 수 있습니다. 일반적으로 필요한 경우에 이미지의 부분을 표시 하려면 <xref:System.Windows.UIElement.Clip%2A> 사용 해야 합니다. 인코딩 및 자른된 이미지를 저장 해야 할 경우는 <xref:System.Windows.Media.Imaging.CroppedBitmap> 사용 해야 합니다. 사용 하 여 클립 속성을 사용 하 여 이미지를 자릅니다 하는 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>합니다.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>이미지 늘이기  
 <xref:System.Windows.Controls.Image.Stretch%2A> 속성을 해당 컨테이너를 채우도록 이미지를 늘립니다 하는 방법을 제어 합니다. <xref:System.Windows.Controls.Image.Stretch%2A> 속성에 의해 정의 된 다음 값은 허용 된 <xref:System.Windows.Media.Stretch> 열거형:  
  
-   <xref:System.Windows.Media.Stretch.None>: 이미지 출력 영역을 채우는 늘어나지 않습니다. 이미지가 출력 영역보다 큰 경우 이미지가 출력 영역으로 그려지고 맞지 않는 부분은 클리핑됩니다.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: 이미지 출력 영역에 맞게 크기가 조정 됩니다. 이미지의 높이 및 너비가 독립적으로 조정되므로 이미지의 원래 가로 세로 비율이 유지되지 않을 수 있습니다. 즉, 출력 컨테이너를 완전히 채우도록 이미지를 이동해야 할 수 있습니다.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: 출력 영역 내에서 완전히 맞도록 이미지 배율을 조정 합니다. 이미지의 가로 세로 비율이 유지됩니다.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: 이미지의 원래 가로 세로 비율을 유지 하면서 출력 영역을 채우도록 완전히 이미지 배율을 조정 합니다.  
  
 다음 예제에서 사용 가능한 각 적용 <xref:System.Windows.Media.Stretch> 열거형에는 <xref:System.Windows.Controls.Image>합니다.  
  
 다음 이미지는 예제에서 출력 보여주며, 영향을 주는 여러 가지 방법을 보여 줍니다 <xref:System.Windows.Controls.Image.Stretch%2A> 설정 했을 때 이미지에 적용 합니다.  
  
 ![여러 TileBrush Stretch 설정](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
여러 늘이기 설정  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>이미지로 그리기  
 이미지도 응용 프로그램에 사용한 그리기로 표시할 수는 <xref:System.Windows.Media.Brush>합니다. 브러시를 사용하여 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르는 모든 방식으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 개체를 그릴 수 있습니다. 이미지를 그리려면를 사용 하 여 프로그램 <xref:System.Windows.Media.ImageBrush>합니다. <xref:System.Windows.Media.ImageBrush> 는 유형의 <xref:System.Windows.Media.TileBrush> 비트맵 이미지 형식으로 해당 콘텐츠를 정의 하는 합니다. <xref:System.Windows.Media.ImageBrush> 변수에 지정 된 단일 이미지를 표시 합니다. 해당 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 속성입니다. 이미지를 늘이고, 정렬하고, 바둑판식으로 배열하는 방식을 제어하여 왜곡을 방지하고 패턴 및 기타 효과를 생성할 수 있습니다. 다음 그림에 나와 있는 얻을 수 있는 몇 가지 효과 <xref:System.Windows.Media.ImageBrush>합니다.  
  
 ![ImageBrush 출력 예제](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
이미지 브러시로 도형, 컨트롤, 텍스트 등을 채울 수 있습니다.  
  
 다음 예제에서는을 사용 하 여 이미지와 단추의 배경을 그리는 방법을 <xref:System.Windows.Media.ImageBrush>합니다.  
  
 [!code-xaml[UsingImageBrush#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 이미지 그리기 참조 및 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>이미지 메타데이터  
 일부 이미지 파일에는 파일의 콘텐츠나 특성을 설명하는 메타데이터가 포함되어 있습니다. 예를 들어 대부분의 디지털 카메라는 이미지를 캡처하는 데 사용되는 카메라의 제조업체와 모델에 대한 메타데이터를 포함하는 이미지를 만듭니다. 각 이미지 형식은 메타데이터를 다르게 처리하지만 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 지원되는 각 이미지 형식에 대한 메타데이터를 저장하고 검색하는 일관된 방법을 제공합니다.  
  
 메타 데이터에 대 한 액세스를 통해 제공 됩니다는 <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> 의 속성을 <xref:System.Windows.Media.Imaging.BitmapSource> 개체입니다. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> 반환 된 <xref:System.Windows.Media.Imaging.BitmapMetadata> 이미지에 포함 된 모든 메타 데이터를 포함 하는 개체입니다. 이 데이터는 하나의 메타데이터 스키마이거나 여러 다른 스키마의 조합일 수 있습니다. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]에서는 [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt(PNG 텍스트 데이터), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] 및 [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)]의 이미지 메타데이터 스키마를 지원합니다.  
  
 메타 데이터를 읽는 프로세스를 간소화 하기 위해 <xref:System.Windows.Media.Imaging.BitmapMetadata> 쉽게 액세스할 수와 같은 여러 명명 된 속성을 제공 <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, 및 <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>합니다. 이러한 명명된 속성 중 대부분은 메타데이터를 작성하는 데도 사용할 수 있습니다. 메타데이터 읽기에 대한 추가 지원이 메타데이터 쿼리 판독기를 통해 제공됩니다. <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> 메서드를 사용 하는 메타 데이터 쿼리 판독기와 같은 문자열 쿼리를 제공 하 여 검색 *"/ app1/exif /"* 합니다. 다음 예에서 <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> 에 저장 된 텍스트를 가져오기 위해 사용 하는 *"/ 텍스트/설명이"* 위치 합니다.  
  
 [!code-cpp[BitmapMetadata#GetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 메타데이터를 작성하기 위해 메타데이터 쿼리 작성기가 사용됩니다. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> 쿼리 작성기를 가져오고 원하는 값을 설정 합니다. 다음 예에서 <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> 에 저장 된 텍스트를 쓰는 데 사용 되는 *"/ 텍스트/설명이"* 위치 합니다.  
  
 [!code-cpp[BitmapMetadata#SetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>코덱 확장성  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]의 핵심 기능은 새로운 이미지 코덱에 대한 확장성 모델입니다. 이러한 관리되지 않는 인터페이스를 통해 코덱 개발자들은 코덱을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 통합할 수 있으므로 새로운 이미지 형식이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 자동으로 사용될 수 있습니다.  
  
 확장성 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]의 샘플을 보려면 [Win32 샘플 코덱](http://go.microsoft.com/fwlink/?LinkID=160052)을 참조하세요. 이 샘플에는 사용자 지정 이미지 형식용 디코더 및 인코더를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  시스템이 코덱을 인식하려면 디지털로 서명되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Imaging.BitmapSource>  
 <xref:System.Windows.Media.Imaging.BitmapImage>  
 <xref:System.Windows.Controls.Image>  
 <xref:System.Windows.Media.Imaging.BitmapMetadata>  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Win32 샘플 코덱](http://go.microsoft.com/fwlink/?LinkID=160052)
