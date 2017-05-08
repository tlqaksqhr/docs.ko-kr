---
title: "방법: 시각적 요소의 그리기 콘텐츠 열거 | Microsoft Docs"
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
  - "Visual의 콘텐츠 열거[WPF]"
  - "Visual의 DrawingGroup 값 검색[WPF]"
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# 방법: 시각적 요소의 그리기 콘텐츠 열거
<xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.Media.Visual>의 콘텐츠를 열거하는 개체 모델을 제공합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용하여 <xref:System.Windows.Media.Visual>의 <xref:System.Windows.Media.DrawingGroup> 값을 검색하고 이를 열거합니다.  
  
> [!NOTE]
>  시각적 요소의 콘텐츠를 열거할 경우 <xref:System.Windows.Media.Drawing> 개체를 검색하는 것이며 렌더링 데이터의 기본 표현을 벡터 그래픽 지침 목록으로 검색하는 것이 아닙니다.  자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하십시오.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)