---
title: "방법: 리플렉션 만들기 | Microsoft Docs"
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
  - "브러시, 리플렉션 만들기"
  - "리플렉션 만들기"
  - "리플렉션., 만들기"
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 리플렉션 만들기
이 예제에서는 <xref:System.Windows.Media.VisualBrush>를 사용하여 리플렉션을 만드는 방법을 보여 줍니다.  <xref:System.Windows.Media.VisualBrush>는 기존의 시각적 효과를 표시할 수 있으므로 이 기능을 사용하여 리플렉션 및 확대와 같은 흥미로운 시각적 효과를 만들 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualBrush>를 사용하여 여러 개의 요소가 포함된 <xref:System.Windows.Controls.Border>의 리플렉션을 만듭니다.  다음 그림에서는 이 예제가 만들어내는 결과를 보여 줍니다.  
  
 ![반사된 표시 개체](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
반사된 표시 개체  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 화면 일부를 확대하고 리플렉션을 만드는 방법을 보여 주는 예제가 포함된 전체 샘플을 보려면 [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.VisualBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)