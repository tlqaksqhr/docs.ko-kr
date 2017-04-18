---
title: "방법: 선형 그라데이션으로 영역 그리기 | Microsoft Docs"
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
  - "브러시, 선형 그라데이션으로 그리기"
  - "선형 그라데이션, 그리기"
  - "그리기, 선형 그라데이션으로"
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 선형 그라데이션으로 영역 그리기
이 예제에서는 <xref:System.Windows.Media.LinearGradientBrush> 클래스를 사용하여 선형 그라데이션으로 영역을 그리는 방법을 보여 줍니다.  다음 예제에서는 노랑, 빨강, 파랑, 황록색의 순서로 바뀌는 대각선 선형 그라데이션을 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  
  
## 예제  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![대각선 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.png "graphicsmm\_DiagonalLGB")  
  
 가로 방향의 선형 그라데이션을 만들려면 <xref:System.Windows.Media.LinearGradientBrush>의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>를 \(0,0.5\) 및 \(1,0.5\)로 변경합니다.  다음 예제에서는 가로 방향의 선형 그라데이션을 사용하여 <xref:System.Windows.Shapes.Rectangle>을 그립니다.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![가로 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.png "graphicsmm\_HorizontalLGB")  
  
 세로 방향의 선형 그라데이션을 만들려면 <xref:System.Windows.Media.LinearGradientBrush>의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>를 \(0.5,0\) 및 \(0.5,1\)로 변경합니다.  다음 예제에서는 세로 방향의 선형 그라데이션을 사용하여 <xref:System.Windows.Shapes.Rectangle>을 그립니다.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![세로 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.png "graphicsmm\_VerticalLGB")  
  
> [!NOTE]
>  이 항목의 예제에서는 기본 좌표계를 사용하여 시작점과 끝점을 설정합니다.  기본 좌표계는 경계 상자에 상대적입니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.  <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode?displayProperty=fullName>로 설정하여 이 좌표계를 변경할 수 있습니다.  절대 좌표계는 경계 상자에 상대적이지 않으며  값이 로컬 공간에서 직접 해석됩니다.  
  
 다른 예제를 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  그라데이션 및 다른 종류의 브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.