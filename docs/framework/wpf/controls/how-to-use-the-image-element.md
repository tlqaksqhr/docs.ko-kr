---
title: "방법: Image 요소 사용 | Microsoft Docs"
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
  - "BitmapImage 클래스"
  - "클래스, BitmapImage"
  - "컨트롤, 이미지"
  - "Image 컨트롤"
  - "이미지 렌더링"
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: Image 요소 사용
이 예제에서는 <xref:System.Windows.Controls.Image> 요소를 사용하여 응용 프로그램에 이미지를 포함시키는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  이 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 특성 구문과 속성 태그 구문을 모두 사용하여 이미지를 정의합니다.  특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  <xref:System.Windows.Media.Imaging.BitmapImage>는 이미지의 소스 데이터를 정의하는 데 사용되고 속성 태그 구문 예제에 명시적으로 정의되어 있습니다.  또한 <xref:System.Windows.Media.Imaging.BitmapImage>의 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>는 <xref:System.Windows.Controls.Image>의 <xref:System.Windows.FrameworkElement.Width%2A>와 같은 너비로 설정됩니다.  이렇게 하는 이유는 이미지 렌더링에 사용되는 메모리 양을 최소화하기 위해서입니다.  
  
> [!NOTE]
>  일반적으로 렌더링된 이미지의 크기를 지정하려는 경우 <xref:System.Windows.FrameworkElement.Width%2A>와 <xref:System.Windows.FrameworkElement.Height%2A>를 모두 지정할 필요 없이 하나만 지정하면 됩니다.  둘 중 하나만 지정하면 이미지의 [가로 세로 비율](GTMT)이 유지됩니다.  그렇지 않으면 이미지가 예기치 않게 늘어나거나 휘어질 수 있습니다.  이미지가 늘어나는 동작을 제어하려면 <xref:System.Windows.Controls.Image.Stretch%2A> 및 <xref:System.Windows.Controls.Image.StretchDirection%2A> 속성을 사용합니다.  
  
> [!NOTE]
>  <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A>를 사용하여 이미지의 크기를 지정하는 경우 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 또는 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A>도 각각 같은 크기로 설정해야 합니다.  
  
 <xref:System.Windows.Controls.Image.Stretch%2A> 속성은 이미지 요소를 채우도록 이미지 소스를 늘이는 방법을 제어합니다.  자세한 내용은 <xref:System.Windows.Media.Stretch> 열거형을 참조하십시오.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## 예제  
 다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> 속성 설정은 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 및 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 블록 내에서 수행해야 합니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)