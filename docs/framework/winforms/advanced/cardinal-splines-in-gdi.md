---
title: "GDI+의 카디널 스플라인 | Microsoft Docs"
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
  - "카디널 스플라인"
  - "GDI+, 카디널 스플라인"
  - "스플라인, 카디널"
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# GDI+의 카디널 스플라인
카디널 스플라인은 대형 곡선을 형성하는 개별 곡선 순서 집합입니다.  스플라인은 점 배열과 장력 매개 변수에 의해 지정됩니다.  카디널 스플라인은 배열의 각 점을 매끄럽게 통과합니다. 날카로운 모퉁이가 없고 곡선의 팽팽한 정도가 갑작스럽게 변하지도 않습니다.  다음 그림은 점 집합과 이 집합의 각 점을 모두 통과하는 카디널 스플라인을 보여 줍니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.png "Aboutgdip02\_art09")  
  
## 물리적 스플라인과 수학적 스플라인  
 물리적인 스플라인은 나무 또는 기타 유연한 재질의 얇은 조각입니다.  수학적 스플라인이 나타나기 전에는 디자이너들이 물리적 스플라인을 사용하여 곡선을 그렸습니다.  디자이너는 스플라인을 종이에 올려 놓고 이를 일련의 점에 맞추어 고정시켰습니다.  그런 다음 펜이나 연필을 사용하여 스플라인을 따라 곡선을 그렸습니다.  주어진 점 집합은 물리적 스플라인의 특성에 따라 다양한 곡선을 만들어냈습니다.  예를 들어, 잘 휘지 않는 스플라인은 매우 유연한 스플라인과는 다른 곡선을 만들었을 것입니다.  
  
 수학적 스플라인의 수식은 유연한 막대의 특성을 기반으로 하므로 수학적 스플라인에 의해 만들어진 곡선은 이전에 물리적 스플라인에 의해 만들어졌던 곡선과 유사합니다.  장력이 다른 물리적 스플라인이 주어진 점 집합을 통과하는 상이한 곡선을 만들듯이 장력 매개 변수가 다른 수학적 스플라인 또한 주어진 점 집합을 통과하는 상이한 곡선을 만듭니다.  다음 그림은 같은 점 집합을 통과하는 네 개의 카디널 스플라인을 보여 줍니다.  각 스플라인의 장력이 표시됩니다.  장력이 0이면 물리적 장력이 무한하다는 의미이므로 점 사이를 연결하는 최단 곡선인 직선을 만듭니다.  장력이 1이면 물리적 장력이 없다는 의미이며, 총 구부림이 가장 적은 스플라인을 만듭니다.  장력 값이 1보다 크면 곡선은 더 긴 행로를 갖도록 압축된 스프링처럼 작동합니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.png "Aboutgdip02\_art10")  
  
 이전 그림에 나오는 네 개의 스플라인은 시작점에서 하나의 접선을 공유합니다.  접선은 시작점에서 곡선의 다음점으로 그린 선입니다.  마찬가지로, 끝점의 공유 접선은 끝점에서 곡선의 이전 점으로 그린 선입니다.  
  
 카디널 스플라인을 그리려면 <xref:System.Drawing.Graphics> 클래스 인스턴스, <xref:System.Drawing.Pen> 및 <xref:System.Drawing.Point> 개체 배열이 필요합니다. <xref:System.Drawing.Graphics> 클래스 인스턴스는 스플라인을 그리는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 선 색과 두께 같은 스플라인 특성이 저장됩니다.  <xref:System.Drawing.Point> 개체 배열에는 곡선이 통과할 점이 저장됩니다.  다음 코드 예제에서는  `myPointArray`의 점을 통과하는 카디널 스플라인을 그리는 방법을 보여 줍니다.  세 번째 매개 변수는 장력입니다.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## 참고 항목  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)