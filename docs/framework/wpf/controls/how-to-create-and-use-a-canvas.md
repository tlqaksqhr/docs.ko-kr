---
title: "방법: 캔버스 만들기 및 사용 | Microsoft Docs"
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
  - "Canvas 컨트롤, 만들기"
  - "Canvas 컨트롤, using"
  - "컨트롤, Canvas"
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 캔버스 만들기 및 사용
이 예제에서는 <xref:System.Windows.Controls.Canvas> 인스턴스를 만들고 사용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Canvas.SetTop%2A> 및 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 메서드를 사용하여 두 개의 <xref:System.Windows.Controls.TextBlock> 요소를 명시적으로 배치합니다.  이 예제에서는 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Control.Background%2A>에 `LightSteelBlue` 색도 할당합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Controls.TextBlock> 요소를 배치할 때는 <xref:System.Windows.Controls.Canvas.Top%2A> 및 <xref:System.Windows.Controls.Canvas.Left%2A> 속성을 사용합니다.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.TextBlock>   
 <xref:System.Windows.Controls.Canvas.SetTop%2A>   
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)