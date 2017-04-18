---
title: "방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기 | Microsoft Docs"
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
  - "클래스, MatrixTransform"
  - "그래픽[WPF], 사용자 지정 변환"
  - "MatrixTransform 클래스"
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기
이 예제에서는 <xref:System.Windows.Media.MatrixTransform>을 사용하여 <xref:System.Windows.Controls.Button>에 대해 위치 변환\(이동\), 늘이기 및 [기울이기](GTMT)를 수행하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.MatrixTransform> 클래스를 사용하면 <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform> 또는 <xref:System.Windows.Media.TranslateTransform> 클래스가 제공하지 않는 사용자 지정 변환을 만들 수 있습니다.  
  
## 예제  
 [!code-xml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## 참고 항목  
 <xref:System.Windows.Media.MatrixTransform>   
 <xref:System.Windows.Media.Transform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)