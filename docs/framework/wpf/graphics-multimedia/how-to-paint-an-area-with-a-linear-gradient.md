---
title: "방법: 선형 그라데이션으로 영역 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eec4ec2fc7ba99081eaafa6803d20c99bebc6c2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>방법: 선형 그라데이션으로 영역 그리기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.LinearGradientBrush> 선형 그라데이션으로 영역을 그리는 클래스입니다. 다음 예제에서는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 노란색에서 파랑 라임 녹색으로 빨간색으로 전환 되 대각선 선형 그라데이션으로 그려집니다.  
  
## <a name="example"></a>예  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 다음 그림에서는 앞의 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![대각선 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 가로 선형 그라데이션을 작성 하려면 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0, 0.5)에 (1, 0.5) 및 합니다. 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 가로 선형 그라데이션으로 그려집니다.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 다음 그림에서는 앞의 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![가로 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 세로 선형 그라데이션을 작성 하려면 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0.5, 0)에 (0.5, 1) 및 합니다. 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 세로 선형 그라데이션으로 그려집니다.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 다음 그림에서는 앞의 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![세로 선형 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  이 항목의 예제는 시작점 및 끝점을 설정 하기 위한 기본 좌표계를 사용 합니다. 경계 상자를 기준으로 기본 좌표계가: 0은 경계 상자의 0 %1의 경계 상자 100%를 나타냅니다. 이 좌표 시스템을 설정 하 여 변경할 수 있습니다는 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>합니다. 절대 좌표계는 경계 상자를 기준으로 하지 않습니다. 값은 로컬 공간에서 직접 해석됩니다.  
  
 추가 예제를 참조 하십시오. [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)합니다. 그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.
