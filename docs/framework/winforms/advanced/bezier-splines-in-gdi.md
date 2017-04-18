---
title: "GDI+의 3차원 곡선 스플라인 | Microsoft Docs"
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
  - "3차원 곡선 스플라인"
  - "GDI+, 3차원 곡선 스플라인"
  - "스플라인, 3차원 곡선"
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# GDI+의 3차원 곡선 스플라인
3차원 곡선 스플라인은 두 개의 끝점 \(p1, p2\)와 두 개의 제어점 \(c1, c2\)로 지정되는 곡선입니다.  곡선은 p1에서 시작하여 p2에서 끝납니다.  곡선은 제어점을 통과하지 않지만 제어점은 자석과 같은 역할을 하여 곡선을 특정 방향으로 끌어당기고 곡선이 구부러지는 방식에 영향을 미칩니다.  다음 그림은 3차원 곡선 및 이 곡선의 끝점과 제어점을 보여 줍니다.  
  
 ![3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.png "Aboutgdip02\_art11a")  
  
 곡선은 p1에서 시작하고 제어점 c1을 향해 움직입니다.  p1에서의 곡선의 접선은 p1에서 c1으로 그린 선입니다.  또한 끝점 p2의 접선은 c2에서 p2까지 그린 선입니다.  
  
## 3차원 곡선 스플라인 그리기  
 3차원 곡선 스플라인을 그리려면 <xref:System.Drawing.Graphics> 클래스 인스턴스와 <xref:System.Drawing.Pen> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 클래스 인스턴스는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 곡선을 렌더링하는 데 사용된 선의 두께와 색 같은 특성이 저장됩니다.  <xref:System.Drawing.Pen> 개체는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드에 대한 인수 중 하나로 전달됩니다.  <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드에 전달되는 나머지 인수는 끝점과 제어점입니다.  다음 예제에서는 시작점 \(0, 0\), 제어점 \(40, 20\)과 \(80, 150\), 끝점 \(100, 10\)을 갖는 3차원 곡선 스플라인을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 다음 그림은 곡선, 제어점 및 두 개의 접선을 보여 줍니다.  
  
 ![3차원 곡선 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.png "Aboutgdip02\_art12")  
  
 3차원 곡선 스플라인은 원래 Pierre Bézier가 자동차 산업 디자인을 위해 개발한 것입니다.  이 곡선은 그 후 다양한 유형의 CAD에 유용한 것으로 판명되었으며 글꼴 윤곽선을 정의하는 데에도 사용됩니다.  3차원 곡선 스플라인을 사용하면 다양한 도형을 만들 수 있으며 다음 그림에서 그 중 일부를 볼 수 있습니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.png "Aboutgdip02\_art13")  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)