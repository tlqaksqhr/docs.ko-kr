---
title: "방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치 | Microsoft Docs"
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
  - "연결된 속성[WPF Designer]"
  - "Canvas 컨트롤, 연결된 속성"
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치
이 예제에서는 <xref:System.Windows.Controls.Canvas>의 [연결된 속성](GTMT)을 사용하여 자식 요소를 배치하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 네 개의 <xref:System.Windows.Controls.Button> 요소를 부모 <xref:System.Windows.Controls.Canvas>의 자식 요소로 추가합니다.  각 자식 요소는 <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A> 및 <xref:System.Windows.Controls.Canvas.Top%2A>의 서로 다른 연결된 속성을 나타냅니다.  각 <xref:System.Windows.Controls.Button>은 부모 <xref:System.Windows.Controls.Canvas>를 기준으로, 각각에 할당된 속성 값에 따라 배치됩니다.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.Canvas.Bottom%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 <xref:System.Windows.Controls.Canvas.Right%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Button>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)   
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)