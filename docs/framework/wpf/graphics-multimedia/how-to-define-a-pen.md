---
title: "방법: 펜 정의 | Microsoft Docs"
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
  - "만들기, 펜"
  - "펜, 정의"
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 2
---
# 방법: 펜 정의
이 예제에서는 <xref:System.Windows.Media.Pen>을 사용하여 모양 윤곽선을 그리는 방법을 보여 줍니다.  간단한 <xref:System.Windows.Media.Pen>을 만들 때는 <xref:System.Windows.Media.Pen.Thickness%2A>와 <xref:System.Windows.Media.Pen.Brush%2A>만 지정하면 됩니다.  <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A> 및 <xref:System.Windows.Media.Pen.EndLineCap%2A>을 지정하면 좀 더 복잡한 펜을 만들 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Pen>을 사용하여 <xref:System.Windows.Media.GeometryDrawing>으로 정의된 모양의 윤곽선을 그립니다.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![펜으로 만들어진 윤곽선](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.png "graphicsmm\_simple\_pen")  
GeometryDrawing