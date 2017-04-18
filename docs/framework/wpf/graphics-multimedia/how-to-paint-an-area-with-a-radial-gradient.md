---
title: "방법: 방사형 그라데이션으로 영역 그리기 | Microsoft Docs"
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
  - "브러시, 방사형 그라데이션으로 그리기"
  - "그리기, 방사형 그라데이션으로"
  - "방사형 그라데이션, 그리기"
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 방사형 그라데이션으로 영역 그리기
이 예제에서는 <xref:System.Windows.Media.RadialGradientBrush> 클래스를 사용하여 방사형 그라데이션으로 영역을 그리는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.RadialGradientBrush>를 사용하여 노랑, 빨강, 파랑, 황록색의 순서로 바뀌는 방사형 그라데이션으로 사각형을 그립니다.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 다음 그림에서는 이전 예제의 그라데이션을 보여 줍니다.  그라데이션의 중지점이 강조 표시되었습니다.  
  
 ![방사형 그라데이션에서 중지된 그라데이션](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
> [!NOTE]
>  이 항목의 예제에서는 기본 좌표계를 사용하여 컨트롤 지점을 설정합니다.  기본 좌표계는 경계 상자에 상대적입니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.  <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성을 값 <xref:System.Windows.Media.BrushMappingMode>로 설정하여 이 좌표계를 변경할 수 있습니다.  절대 좌표계는 경계 상자에 상대적이지 않으며  값이 로컬 공간에서 직접 해석됩니다.  
  
 다른 <xref:System.Windows.Media.RadialGradientBrush> 예제를 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  그라데이션 및 다른 종류의 브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.