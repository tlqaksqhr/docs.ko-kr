---
title: GDI+의 펜, 선 및 사각형
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 86cc51006361d5628dc12999588520e28e62f166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>GDI+의 펜, 선 및 사각형
있는 선을 그리려면 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 만들어야 할 한 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다. <xref:System.Drawing.Graphics> 드로잉을 실제로 수행 하는 메서드를 제공 하는 개체 및 <xref:System.Drawing.Pen> 개체 선 색, 너비 및 스타일 등의 특성을 저장 합니다.  
  
## <a name="drawing-a-line"></a>선 그리기  
 선을 그리기 호출의 <xref:System.Drawing.Graphics.DrawLine%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다. <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드. 다음 예제에서는 점 (4, 2)에서 점 (12, 6) 선을 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> 오버 로드 된 메서드는 <xref:System.Drawing.Graphics> 클래스, 여러 가지 인수를 제공할 수 있습니다. 예를 들어 두 개의 생성할 수 있습니다 <xref:System.Drawing.Point> 개체 및 패스는 <xref:System.Drawing.Point> 개체에 대 한 인수는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>펜 생성  
 생성할 때 특정 특성을 지정할 수는 <xref:System.Drawing.Pen> 개체입니다. 예를 들어 하나 `Pen` 생성자를 사용 하면 색 및 너비를 지정할 수 있습니다. 다음 예에서는 너비 2의 파란색 선을 그립니다 (0, 0)를 (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>파선 및 선 끝  
 <xref:System.Drawing.Pen> 개체도 노출 속성을 같은 <xref:System.Drawing.Pen.DashStyle%2A>, 줄의 기능을 지정 하는 데 사용할 수 있는 합니다. 다음 예제에서 파선 그립니다 (100, 50)에 (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 속성을 사용할 수는 <xref:System.Drawing.Pen> 다양 한 특성 줄의 설정할 개체입니다. <xref:System.Drawing.Pen.StartCap%2A> 및 <xref:System.Drawing.Pen.EndCap%2A> 속성 선의 끝 모양을 지정, 플랫, 사각형, 둥근, 삼각형, 끝 수 또는 사용자 지정 셰이프. <xref:System.Drawing.Pen.LineJoin%2A> 속성 또는 지정할 수 있습니다 여부를 연결 된 선 됩니다 (조인 날카로운 모퉁이가) 음, 경사진, 반올림 잘립니다. 다음 그림에 cap 및 조인에 대 한 다양 한 스타일 포함 된 줄을 보여 줍니다.  
  
 ![줄](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>사각형 그리기  
 사각형과 그 그리기 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선을 그리는 것과 비슷합니다. 사각형을 그리려면 하려면는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다. <xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체 선 두께 및 색 등의 특성을 저장 합니다. <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드. 다음 예제에서는 왼쪽 위 모퉁이가으로 사각형을 그립니다 (100, 50), 80, 너비 및 높이 40의:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> 오버 로드 된 메서드는 <xref:System.Drawing.Graphics> 클래스, 여러 가지 인수를 제공할 수 있습니다. 예를 들어 생성할 수 있습니다는 <xref:System.Drawing.Rectangle> 개체를 전달는 <xref:System.Drawing.Rectangle> 개체는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드에 인수로:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 A <xref:System.Drawing.Rectangle> 개체에 메서드와 속성을 조작 하 고 사각형에 대 한 정보를 수집 합니다. 예를 들어는 <xref:System.Drawing.Rectangle.Inflate%2A> 및 <xref:System.Drawing.Rectangle.Offset%2A> 메서드 크기 및 사각형의 위치를 변경 합니다. <xref:System.Drawing.Rectangle.IntersectsWith%2A> 메서드 알려 여부 다른 사각형과 교차 사각형이 및 <xref:System.Drawing.Rectangle.Contains%2A> 메서드 알려 사각형 안에 지정된 된 지점 인지 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Rectangle?displayProperty=nameWithType>  
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [방법: Windows Form에 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)  
 [방법: 윤곽선이 있는 도형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
