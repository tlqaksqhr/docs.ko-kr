---
title: "GDI+의 펜, 선 및 사각형 | Microsoft Docs"
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
  - "그리기, 선"
  - "그리기, 사각형"
  - "예제[Windows Forms], 선 및 모양 그리기"
  - "예제[Windows Forms], GDI+"
  - "예제[Windows Forms], 펜"
  - "GDI+, 선"
  - "GDI+, 펜"
  - "GDI+, 사각형"
  - "선"
  - "선, 파선"
  - "사각형"
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# GDI+의 펜, 선 및 사각형
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 선을 그리려면 <xref:System.Drawing.Graphics> 개체와 <xref:System.Drawing.Pen> 개체를 만들어야 합니다.  <xref:System.Drawing.Graphics> 개체는 실제로 그리기를 수행하는 메서드를 제공하며 <xref:System.Drawing.Pen> 개체에는 선의 색, 두께 및 스타일 같은 특성이 저장됩니다.  
  
## 선 그리기  
 선을 그리려면 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드를 호출합니다.  <xref:System.Drawing.Pen> 개체는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에 대한 인수 중 하나로 전달됩니다.  다음 예제에서는 점 \(4, 2\)와 점 \(12, 6\)을 연결하는 선을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A>은 <xref:System.Drawing.Graphics> 클래스의 오버로드된 메서드이므로 여러 가지 방법으로 여기에 인수를 제공할 수 있습니다.  예를 들어 <xref:System.Drawing.Point> 개체를 두 개 만든 다음 <xref:System.Drawing.Point> 개체를 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에 대한 인수로 전달할 수 있습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## Pen 개체 만들기  
 <xref:System.Drawing.Pen> 개체를 만들 때 몇 가지 특성을 지정할 수 있습니다.  예를 들어, `Pen` 생성자를 사용하여 색과 너비를 지정할 수 있습니다.  다음 예제에서는 \(0, 0\)과 \(60, 30\)을 연결하는 너비 2의 파랑 선을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## 파선 및 선 끝  
 <xref:System.Drawing.Pen> 개체는 <xref:System.Drawing.Pen.DashStyle%2A>과 같이 선의 특징을 지정하는 데 사용할 수 있는 속성도 제공합니다.  다음 예제에서는 \(100, 50\)과 \(300, 80\)을 연결하는 파선을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <xref:System.Drawing.Pen> 개체의 속성을 사용하여 선의 다양한 특성을 설정할 수 있습니다.  <xref:System.Drawing.Pen.StartCap%2A> 및 <xref:System.Drawing.Pen.EndCap%2A> 속성은 선 끝 모양을 지정합니다. 선 끝 모양은 평평하거나, 사각형이거나, 둥글거나, 삼각형일 수 있으며 모양을 사용자 지정할 수도 있습니다.  <xref:System.Drawing.Pen.LineJoin%2A> 속성을 사용하면 연결된 선을 마이터\(날카로운 모퉁이와 조인\), 빗면, 원형 스타일로 처리할지 아니면 클리핑할지 지정할 수 있습니다.  다음 그림은 다양한 끝 모양과 연결 스타일의 선을 보여 줍니다.  
  
 ![선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.png "Aboutgdip02\_art04")  
  
## 사각형 그리기  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 사각형을 그리는 작업은 선 그리기와 비슷합니다.  사각형을 그리려면 <xref:System.Drawing.Graphics> 개체와 <xref:System.Drawing.Pen> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 선의 색과 두께 같은 특성이 저장됩니다.  <xref:System.Drawing.Pen> 개체는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드에 대한 인수 중 하나로 전달됩니다.  다음 예제에서는 \(100,50\)에 왼쪽 위 모퉁이를 갖는 너비 80, 높이 40의 사각형을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>은 <xref:System.Drawing.Graphics> 클래스의 오버로드된 메서드이므로 여러 가지 방법으로 여기에 인수를 제공할 수 있습니다.  예를 들어 <xref:System.Drawing.Rectangle> 개체를 만든 다음 <xref:System.Drawing.Rectangle> 개체를 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드에 인수로 전달할 수 있습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <xref:System.Drawing.Rectangle> 개체에는 사각형의 정보를 조작하고 수집할 수 있는 메서드와 속성이 있습니다.  예를 들어 <xref:System.Drawing.Rectangle.Inflate%2A> 및 <xref:System.Drawing.Rectangle.Offset%2A> 메서드는 사각형의 크기와 위치를 변경합니다.  <xref:System.Drawing.Rectangle.IntersectsWith%2A> 메서드는 사각형이 다른 사각형과 교차하는지 여부를 나타내고 <xref:System.Drawing.Rectangle.Contains%2A> 메서드는 지정된 점이 사각형 내부에 있는지 여부를 나타냅니다.  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Rectangle?displayProperty=fullName>   
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [방법: Windows Form에 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)   
 [방법: 윤곽선이 있는 도형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)