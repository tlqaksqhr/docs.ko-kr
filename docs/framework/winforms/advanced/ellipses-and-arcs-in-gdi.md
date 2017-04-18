---
title: "GDI+의 타원 및 원호 | Microsoft Docs"
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
  - "원호"
  - "그리기, 원호"
  - "그리기, 타원"
  - "타원"
  - "GDI+, 원호"
  - "GDI+, 타원"
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# GDI+의 타원 및 원호
<xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawEllipse%2A> 및 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드를 사용하여 타원과 원호를 쉽게 그릴 수 있습니다.  
  
## 타원 그리기  
 타원을 그리려면 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 타원을 렌더링하는 데 사용되는 선의 색과 두께 같은 특성이 저장됩니다.  <xref:System.Drawing.Pen> 개체는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드에 대한 인수 중 하나로 전달됩니다.  <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드에 전달되는 나머지 인수는 타원의 경계 사각형을 지정합니다.  다음 그림은 타원을 경계 사각형과 함께 보여 줍니다.  
  
 ![타원 및 원호](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.png "Aboutgdip02\_art05")  
  
 다음 예제에서는 너비 80, 높이 40이며 왼쪽 위 모퉁이가 \(100,50\)인 경계 사각형을 갖는 타원을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>은 <xref:System.Drawing.Graphics> 클래스의 오버로드된 메서드이므로 여러 가지 방법으로 여기에 인수를 제공할 수 있습니다.  예를 들어, <xref:System.Drawing.Rectangle>을 생성하고 <xref:System.Drawing.Rectangle>을 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드에 인수로 전달할 수 있습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## 원호 그리기  
 원호는 타원의 일부분입니다.  원호를 그리려면 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드를 호출합니다.  <xref:System.Drawing.Graphics.DrawArc%2A> 메서드의 매개 변수는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드의 매개 변수와 같지만 <xref:System.Drawing.Graphics.DrawArc%2A>에는 시작 각도와 전진 각도가 필요합니다.  다음 예제에서는 시작 각도 30도, 전진 각도 180도인 원호를 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 다음 그림은 원호, 타원 및 경계 사각형을 보여 줍니다.  
  
 ![타원 및 원호](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.png "Aboutgdip02\_art06")  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [방법: 윤곽선이 있는 도형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)