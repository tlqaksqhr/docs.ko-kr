---
title: "방법: 단색으로 영역 그리기 | Microsoft Docs"
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
  - "브러시, 단색으로 그리기"
  - "그리기, 단색으로"
  - "단색, 그리기"
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 단색으로 영역 그리기
단색으로 영역을 그리려면 <xref:System.Windows.Media.Brushes.Red%2A> 또는 <xref:System.Windows.Media.Brushes.Blue%2A>와 같은 미리 정의된 시스템 브러시를 사용하거나 새 <xref:System.Windows.Media.SolidColorBrush>를 생성하고 알파, 빨강, 녹색 및 파랑 값을 사용하여 브러시의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 기술할 수 있습니다.  XAML에서는 16진수 표기법을 사용하여 단색으로 영역을 그릴 수도 있습니다.  
  
 다음 예제에서는 이러한 기술 각각을 사용하여 <xref:System.Windows.Shapes.Rectangle>을 파란색으로 그립니다.  
  
## 예제  
 **미리 정의된 브러시 사용**  
  
 다음 예제에서는 미리 정의된 브러시 <xref:System.Windows.Media.Brushes.Blue%2A>를 사용하여 사각형을 파란색으로 그립니다.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **16진수 표기법 사용**  
  
 다음 예제에서는 8자리 16진수 표기법을 사용하여 사각형을 파란색으로 그립니다.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **ARGB 값 사용**  
  
 다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>를 생성하고 파란색에 해당하는 ARGB 값을 사용하여 브러시의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 기술합니다.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 색을 기술하는 다른 방법에 대해서는 <xref:System.Windows.Media.Color> 구조체를 참조하십시오.  
  
 **관련 항목**  
  
 <xref:System.Windows.Media.SolidColorBrush>에 대한 자세한 내용과 추가 예제를 보려면 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) 개요를 참조하십시오.  
  
 이 코드 예제는 <xref:System.Windows.Media.SolidColorBrush> 클래스에 대해 제공되는 보다 큰 예제의 일부입니다.  전체 샘플을 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Brushes>