---
title: "방법: 비디오로 영역 그리기 | Microsoft Docs"
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
  - "브러시, 비디오를 사용하여 그리기"
  - "비디오를 사용하여 그리기"
  - "비디오, 그리기"
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 비디오로 영역 그리기
이 예제에서는 미디어를 사용하여 영역을 그리는 방법을 보여 줍니다.  미디어로 영역을 그리는 한 가지 방법은 <xref:System.Windows.Controls.MediaElement>와 <xref:System.Windows.Media.VisualBrush>를 함께 사용하는 것입니다.  <xref:System.Windows.Controls.MediaElement>를 사용하여 미디어를 로드 및 재생하고 이 미디어를 사용하여 <xref:System.Windows.Media.VisualBrush>의 <xref:System.Windows.Media.VisualBrush.Visual%2A> 속성을 설정합니다.  그런 다음 <xref:System.Windows.Media.VisualBrush>를 사용하여 로드된 미디어로 영역을 그릴 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.VisualBrush>를 사용하여 비디오로 <xref:System.Windows.Controls.TextBlock> 컨트롤의 <xref:System.Windows.Controls.TextBlock.Foreground%2A>를 그립니다.  이 예제는 <xref:System.Windows.Controls.MediaElement>의 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 속성을 `true`로 설정하므로 사운드가 재생되지 않습니다.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## 예제  
 <xref:System.Windows.Media.VisualBrush>는 <xref:System.Windows.Media.TileBrush> 클래스에서 상속되기 때문에 몇 가지 바둑판식 배열 모드도 제공합니다.  <xref:System.Windows.Media.VisualBrush>의 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 <xref:System.Windows.Media.TileMode>로 설정하고 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성을 그리려는 영역보다 작은 값으로 설정하면 바둑판식 배열 패턴을 만들 수 있습니다.  
  
 다음 예제는 <xref:System.Windows.Media.VisualBrush>가 비디오에서 패턴을 생성한다는 점만 제외하고 이전 예제와 동일합니다.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 응용 프로그램에 미디어 파일과 같은 콘텐츠 파일을 추가하는 방법에 대한 자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)을 참조하십시오.  미디어 파일을 추가할 때는 리소스 파일이 아닌 콘텐츠 파일로 추가해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.VisualBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [TileBrush 개요](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [멀티미디어 개요](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)