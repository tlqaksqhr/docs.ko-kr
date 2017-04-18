---
title: "방법: 일련의 3차원 곡선 스플라인 그리기 | Microsoft Docs"
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
  - "3차원 곡선 스플라인, 일련의 스플라인 그리기"
  - "스플라인, 3차원 곡선 그리기"
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 일련의 3차원 곡선 스플라인 그리기
<xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawBeziers%2A> 메서드를 사용하면 연결된 일련의 3차원 곡선 스플라인을 그릴 수 있습니다.  
  
## 예제  
 다음 예제에서는 3차원 곡선 스플라인 두 개로 연결된 곡선을 그립니다.  첫 번째 3차원 곡선 스플라인의 끝점은 두 번째 3차원 곡선 스플라인의 시작점입니다.  
  
 아래 그림에서는 일곱 개의 점을 따라 그려진 연결된 스플라인을 보여 줍니다.  
  
 ![3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [GDI\+의 3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)