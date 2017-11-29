---
title: "GDI+의 타원 및 원호"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ebeae1d076a0ebcf36d52dee1af0c0ad5f04fdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a>GDI+의 타원 및 원호
타원 및 원호를 사용 하 여 쉽게 그릴 수는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 및 <xref:System.Drawing.Graphics.DrawArc%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.  
  
## <a name="drawing-an-ellipse"></a>타원 그리기  
 타원을 그리려면 하려면는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다. <xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체 너비 및 타원을 렌더링 하는 데 사용 되는 줄의 색을 같은 특성을 저장 합니다. <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드. 나머지 인수에 전달 된 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드 타원에 대 한 경계 사각형을 지정 합니다. 다음 그림에는 타원의 경계 사각형 함께 보여 줍니다.  
  
 ![타원 및 원호](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 다음 예제에서는; 되는 타원을 그립니다. 경계 사각형에 80, 40, 높이 및의 왼쪽 위 모퉁이의 너비 (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>오버 로드 된 메서드는 <xref:System.Drawing.Graphics> 클래스, 여러 가지 인수를 제공할 수 있습니다. 예를 들어 생성할 수 있습니다는 <xref:System.Drawing.Rectangle> 전달는 <xref:System.Drawing.Rectangle> 에 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드에 인수로:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>호를 그리기  
 원호는 타원의 부분입니다. 호출 호를 그리려면는 <xref:System.Drawing.Graphics.DrawArc%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다. 매개 변수는 <xref:System.Drawing.Graphics.DrawArc%2A> 의 매개 변수와 동일는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드와 비슷하지만 <xref:System.Drawing.Graphics.DrawArc%2A> 시작 각도 및 스윕 각도 필요로 합니다. 다음 예제에서는 30도의 시작 각도 및 스윕 각도 180도 호를 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 다음 그림에서는 호, 타원 및 경계 사각형을 보여 줍니다.  
  
 ![타원 및 원호](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [방법: 윤곽선이 있는 도형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
