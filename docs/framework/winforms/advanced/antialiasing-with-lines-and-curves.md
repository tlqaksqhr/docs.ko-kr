---
title: "선과 곡선의 앤티 앨리어싱 | Microsoft Docs"
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
  - "앤티 앨리어싱"
  - "앤티 앨리어싱, 다듬기 모드"
  - "GDI+, 앤티 앨리어싱"
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 선과 곡선의 앤티 앨리어싱
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 선을 그리는 경우 선의 시작점과 끝점을 지정하지만 선의 개별 픽셀에 대한 정보는 제공할 필요가 없습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 디스플레이 드라이버 소프트웨어와 함께 작동하여 특정 디스플레이 장치에서 선을 표시하기 위해 설정할 픽셀을 결정합니다.  
  
## 앨리어싱  
 점 \(4, 2\)에서 점 \(16, 10\)까지의 빨강 직선을 생각해 봅시다.  좌표계의 원점이 왼쪽 위 모퉁이에 있고 단위가 픽셀이라고 가정합시다.  또한 x 축은 오른쪽을 향하고 y 축은 아래를 향한다고 가정합시다.  다음 그림은 다중 색의 배경에 그려진 빨강 선을 확대해서 표시한 것입니다.  
  
 ![선, 앤티 앨리어싱 사용 안 함](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.png "AboutGdip02\_Art33")  
  
 선을 렌더링하는 데 사용되는 빨강 픽셀은 불투명합니다.  선에 부분적으로 투명한 픽셀은 없습니다.  이러한 유형의 선 렌더링을 사용하면 선이 거칠어 보이고 약간 계단처럼 보입니다.  선을 계단식으로 표현하는 기술을 앨리어싱이라고 합니다. 여기서 계단 모양이 이론적인 선의 앨리어스입니다.  
  
## 앤티 앨리어싱  
 선을 렌더링하는 더 정교한 기술은 불투명한 픽셀과 함께 부분적으로 투명한 픽셀을 사용하는 것입니다.  픽셀은 선에서 어느 정도 가까이 있는지에 따라 순수한 빨강 또는 배경색과 빨강의 혼합으로 설정됩니다.  이러한 유형의 렌더링을 앤티 앨리어싱이라고 하며 그 결과는 선이 사람 눈에 더 매끄럽게 보입니다.  다음 그림은 특정 픽셀이 앤티 앨리어싱 선을 나타내기 위해 배경색과 혼합되는 방법을 보여 줍니다.  
  
 ![선 앤티 앨리어싱](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.png "AboutGdip02\_Art34")  
  
 곡선에도 앤티 앨리어싱\(다듬기\)을 적용할 수 있습니다.  다음 그림은 매끄러운 타원을 확대해서 표시한 것입니다.  
  
 ![곡선 앤티 앨리어싱](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.png "AboutGdip02\_Art35")  
  
 다음 그림은 동일한 타원을 실제 크기로 보여 주는데 한 번은 앤티 앨리어싱되지 않았고 한 번은 앤티 앨리어싱된 것입니다.  
  
 ![앤티 앨리어싱 예](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02\_Art36")  
  
 앤티 앨리어싱을 사용하는 선과 곡선을 그리려면 <xref:System.Drawing.Graphics> 클래스의 인스턴스를 만들고 <xref:System.Drawing.Graphics.SmoothingMode%2A> 속성을 <xref:System.Drawing.Drawing2D.SmoothingMode> 또는 <xref:System.Drawing.Drawing2D.SmoothingMode>로 설정합니다.  그런 다음 같은 <xref:System.Drawing.Graphics> 클래스의 그리기 메서드 중 하나를 호출합니다.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 텍스트에 앤티 앨리어싱 사용](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)