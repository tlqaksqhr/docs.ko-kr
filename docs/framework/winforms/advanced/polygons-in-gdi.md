---
title: "GDI+의 다각형 | Microsoft Docs"
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
  - "그리기, 다각형"
  - "GDI+, 다각형"
  - "다각형"
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# GDI+의 다각형
다각형은 세 개 이상의 직선면을 갖는 닫힌 도형입니다.  예를 들어 , 삼각형은 3면을 갖는 다각형이며, 사각형은 4면, 오각형은 5면을 갖는 다각형입니다.  다음 그림은 여러 가지 다각형을 보여 줍니다.  
  
 ![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.png "Aboutgdip02\_art07")  
  
## 다각형 그리기  
 다각형을 그리려면 <xref:System.Drawing.Graphics> 개체, <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Point> 또는 <xref:System.Drawing.PointF> 개체 배열이 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드를 제공합니다.  <xref:System.Drawing.Pen> 개체에는 다각형을 렌더링하는 데 사용되는 선의 색과 두께 같은 특성이 저장되고 <xref:System.Drawing.Point> 개체 배열에는 직선으로 연결할 점이 저장됩니다.  <xref:System.Drawing.Pen> 개체와 <xref:System.Drawing.Point> 개체 배열은 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드에 인수로 전달됩니다.  다음 예제에서는 3면 다각형을 그립니다.   `myPointArray`에는 \(0, 0\), \(50, 30\), \(30, 60\)의 세 점만 있습니다.  <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드는 점 \(30, 60\)에서 시작점 \(0, 0\)으로 선을 그려 자동으로 다각형을 닫습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 다음 그림은 다각형을 보여 줍니다.  
  
 ![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.png "Aboutgdip02\_art08")  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)