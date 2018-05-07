---
title: GDI+의 다각형
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="polygons-in-gdi"></a>GDI+의 다각형
다각형은 세 개 이상의 직선 면으로 폐쇄형된 도형입니다. 예를 들어 삼각형 세 면 있는 다각형 사각형은 네 면 있는 다각형 있고, 오각형은 5 면 합니다. 다음 그림에는 여러 다각형과 보여 줍니다.  
  
 ![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>다각형을 그리기  
 다각형을 그리려면 하려면는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Pen> 개체 및 배열을 <xref:System.Drawing.Point> (또는 <xref:System.Drawing.PointF>) 개체입니다. <xref:System.Drawing.Graphics> 개체는 제공 된 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드. <xref:System.Drawing.Pen> 개체 너비 다각형, 및 배열에 렌더링 하는 데 선의 색과 같은 특성이 저장 <xref:System.Drawing.Point> 개체를 직선으로 연결 포인트를 저장 합니다. <xref:System.Drawing.Pen> 개체와 배열을 <xref:System.Drawing.Point> 개체를 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드. 다음 예제에서는 3 면 다각형을 그립니다. 세 개의 요소는 `myPointArray`: (0, 0) (50, 30) (30, 60)입니다. <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드에서 선을 그려 다각형을 자동으로 닫습니다 (30, 60) (0, 0) 하 여 시작 지점으로 다시 합니다.  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 다음 그림에는 다각형 보여 줍니다.  
  
 ![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
