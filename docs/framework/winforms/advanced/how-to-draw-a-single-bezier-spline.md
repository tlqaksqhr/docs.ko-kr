---
title: "방법: 단일 3차원 곡선 스플라인 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "3차원 곡선 스플라인, 그리기"
  - "그리기, 3차원 곡선 스플라인"
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 단일 3차원 곡선 스플라인 그리기
3차원 곡선 스플라인은 네 개의 점, 즉 시작점, 끝점 및 두 개의 제어점으로 정의됩니다.  
  
## 예제  
 다음 예제에서는 시작점이 \(10, 100\)이고 끝점이 \(200, 100\)인 3차원 곡선 스플라인을 그립니다.  이 예제에서 제어점은 \(100, 10\)과 \(150, 150\)입니다.  
  
 다음 그림에서는 위의 예제를 실행하여 만든 3차원 곡선 스플라인과 이 스플라인의 시작점, 제어점 및 끝점을 보여 줍니다.  그림에는 스플라인의 네 점을 직선으로 연결하여 형성된 볼록 다각형도 나타나 있습니다.  
  
 ![3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Graphics.DrawBezier%2A>   
 [GDI\+의 3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [방법: 일련의 3차원 곡선 스플라인 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)