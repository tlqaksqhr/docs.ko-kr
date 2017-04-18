---
title: "방법: 카디널 스플라인 그리기 | Microsoft Docs"
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
  - "카디널 스플라인, 그리기"
  - "그리기, 카디널 스플라인"
  - "그래픽, 카디널 스플라인"
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 카디널 스플라인 그리기
카디널 스플라인은 주어진 점의 집합을 매끄럽게 통과하며 그려지는 곡선입니다.  카디널 스플라인을 그리려면 <xref:System.Drawing.Graphics> 개체를 만들고 점 배열의 주소를 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드에 전달합니다.  
  
### 종 모양 카디널 스플라인 그리기  
  
-   다음 예제에서는 지정된 다섯 개의 점을 통과하는 종 모양의 카디널 스플라인을 그립니다.  아래 그림에서는 곡선과 다섯 개의 점을 보여 줍니다.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### 닫힌 카디널 스플라인 그리기  
  
-   <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드를 사용하여 닫힌 카디널 스플라인을 그립니다.  닫힌 카디널 스플라인에서는 곡선이 배열의 마지막 점을 지나 배열의 첫 번째 점으로 다시 연결됩니다.  다음 예제에서는 지정된 여섯 개의 점을 통과하는 닫힌 카디널 스플라인을 그립니다.  아래 그림에서는 여섯 개의 점을 따라 그려진 닫힌 스플라인을 보여 줍니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### 카디널 스플라인의 굴곡 변경  
  
-   장력 인수를 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드에 전달하여 카디널 스플라인의 굴곡 정도를 변경합니다.  다음 예제에서는 동일한 점 집합을 통과하는 세 개의 카디널 스플라인을 그립니다.  아래 그림에서는 세 가지 스플라인 및 각각의 장력 값을 보여 줍니다.  장력 값이 0이면 점은 직선으로 연결됩니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)