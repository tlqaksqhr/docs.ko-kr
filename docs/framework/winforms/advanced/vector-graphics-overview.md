---
title: "벡터 그래픽 개요 | Microsoft Docs"
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
  - "좌표계"
  - "그래픽, 벡터 그래픽"
  - "포함-포함 종점"
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 벡터 그래픽 개요
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 좌표계에 선, 사각형 및 기타 도형을 그립니다.  다양한 좌표계가 있지만 기본 좌표계에는 원점이 왼쪽 위 모퉁이에 있으며 x 축은 오른쪽을 향하고 y 축은 아래쪽을 향합니다.  기본 좌표계의 눈금 단위는 픽셀입니다.  
  
## GDI\+의 빌딩 블록  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.png "AboutGdip02\_Art01")  
  
 컴퓨터 모니터는 그림 요소 또는 픽셀이라고 부르는 점들의 사각형 배열에 디스플레이를 만듭니다.  화면에 나타나는 픽셀의 수는 모니터별로 다르며 각 모니터에 나타나는 픽셀 수는 사용자가 어느 정도 구성할 수 있습니다.  
  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.png "AboutGdip02\_Art02")  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 선, 사각형 또는 곡선을 그리는 경우 그릴 항목에 대한 주요 정보를 제공해야 합니다.  예를 들어 두 점을 제공하여 선을 지정하고 점, 높이 및 너비를 제공하여 사각형을 지정할 수 있습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 디스플레이 드라이버 소프트웨어와 함께 작동하여 선, 사각형 또는 곡선을 표시하기 위해 설정할 픽셀을 결정합니다.  다음 그림은 점 \(4, 2\)와 점 \(12, 8\)을 연결하는 선을 표시하기 위해 켜 놓은 픽셀을 보여 줍니다.  
  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.png "AboutGdip02\_Art03")  
  
 시간이 지나면서 특정한 기본 빌딩 블록이 2차원 그림을 만들 때 가장 유용한 것으로 판명되었습니다.  다음 빌딩 블록은 모두 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 지원됩니다.  
  
-   줄  
  
-   사각형  
  
-   타원  
  
-   원호  
  
-   다각형  
  
-   카디널 스플라인  
  
-   3차원 곡선 스플라인  
  
## Graphics 개체를 사용하는 그리기 메서드  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 <xref:System.Drawing.Graphics> 클래스는 위의 목록에 있는 항목을 그리는 데 사용할 수 있도록 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A>\(카디널 스플라인용\) 및 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드를 제공합니다.  이러한 메서드는 모두 오버로드됩니다. 즉 각 메서드는 다양한 매개 변수 목록을 지원합니다.  예를 들어 <xref:System.Drawing.Graphics.DrawLine%2A>에서 변형된 한 메서드는 <xref:System.Drawing.Pen> 개체와 네 개의 정수를 받고 <xref:System.Drawing.Graphics.DrawLine%2A>에서 변형된 다른 메서드는 <xref:System.Drawing.Pen> 개체와 두 개의 <xref:System.Drawing.Point> 개체를 받습니다.  
  
 <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A> 및 <xref:System.Drawing.Graphics.DrawBeziers%2A> 등과 같이 선, 사각형 및 3차원 곡선 스플라인을 그리는 메서드는 한 번 호출하여 여러 항목을 그리는 동반 메서드를 여러 개 갖습니다.  또한 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드는 곡선의 끝점을 시작점과 연결하여 곡선을 닫는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드를 동반합니다.  
  
 <xref:System.Drawing.Graphics> 클래스의 모든 그리기 메서드는 <xref:System.Drawing.Pen> 개체와 함께 사용됩니다.  어떤 도형을 그리더라도 최소한 <xref:System.Drawing.Graphics> 개체와 <xref:System.Drawing.Pen> 개체를 만들어야 합니다.  <xref:System.Drawing.Pen> 개체에는 그리려는 대상 항목의 선 두께와 색 같은 특성이 저장됩니다.  <xref:System.Drawing.Pen> 개체는 그리기 메서드에 대한 인수 중 하나로 전달됩니다.  예를 들어 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에서 변형된 한 메서드는 아래에 나오는 너비 100, 높이 50, 왼쪽 위 모퉁이 \(20, 10\)의 사각형 그리기 예제와 같이 <xref:System.Drawing.Pen> 개체와 네 개의 정수를 받습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)