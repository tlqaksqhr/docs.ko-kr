---
title: "GDI+의 영역 | Microsoft Docs"
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
  - "그리기, 영역"
  - "GDI+, 영역"
  - "영역"
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# GDI+의 영역
영역은 출력 장치의 표시 영역의 한 부분입니다.  영역은 단일 사각형에서처럼 단순하거나 다각형과 폐곡선의 조합에서처럼 복잡할 수 있습니다.  다음 그림은 두 개의 영역을 보여 줍니다. 하나는 사각형에서 생성된 것이고 다른 하나는 패스에서 생성된 것입니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.png "AboutGdip02\_Art27")  
  
## 영역 사용  
 영역은 종종 클리핑 및 적중 테스트에 사용됩니다.  클리핑은 표시 영역의 특정 영역에 그리기를 제한하는데 일반적으로 이 영역은 업데이트가 필요한 부분을 나타냅니다.  적중 테스트는 마우스 단추가 눌려졌을 때 커서가 화면의 특정 영역에 있는지 여부를 확인합니다.  
  
 사각형 또는 패스에서 영역을 생성할 수 있습니다.  또한 기존 영역을 조합하여 복잡한 영역을 만들 수 있습니다.  <xref:System.Drawing.Region> 클래스는 영역을 결합하는 데 필요한 <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A> 및 <xref:System.Drawing.Region.Complement%2A> 메서드를 제공합니다.  
  
 두 영역의 교집합은 양쪽 영역에 속하는 모든 점의 집합입니다.  합집합은 두 영역 중 한 영역 이상에 속하는 모든 점들의 집합입니다.  영역의 보수\(complement\)는 해당 영역에 속하지 않는 모든 점들의 집합입니다.  다음 그림은 앞의 그림에서 보았던 두 영역의 교집합과 합집합을 보여 줍니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02\_Art28")  
  
 <xref:System.Drawing.Region.Xor%2A> 메서드를 한 쌍의 영역에 적용하면 두 영역 중 한 영역에만 속해 있는 점들을 포함하는 영역이 생깁니다.  <xref:System.Drawing.Region.Exclude%2A> 메서드를 한 쌍의 영역에 적용하면 두 번째 영역에 속하지 않고 첫 번째 영역에만 속하는 모든 점들을 포함하는 영역이 생깁니다.  다음 그림은 이 항목의 앞부분에서 보았던 두 영역에 <xref:System.Drawing.Region.Xor%2A> 및 <xref:System.Drawing.Region.Exclude%2A> 메서드를 적용했을 경우의 영역을 나타냅니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.png "AboutGdip02\_Art29")  
  
 영역을 채우려면 <xref:System.Drawing.Graphics> 개체, <xref:System.Drawing.Brush> 개체 및 <xref:System.Drawing.Region> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.FillRegion%2A> 메서드를 제공하며 <xref:System.Drawing.Brush> 개체는 색이나 패턴 같은 채우기 특성을 저장합니다.  다음 예제에서는 단색으로 영역을 채웁니다.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## 참고 항목  
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [영역 사용](../../../../docs/framework/winforms/advanced/using-regions.md)