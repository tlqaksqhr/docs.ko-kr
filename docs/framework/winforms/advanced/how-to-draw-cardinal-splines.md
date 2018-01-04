---
title: "방법: 카디널 스플라인 그리기"
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
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64661bbdcb267e2f2ce33b8a8db2ab2aac9a86f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-cardinal-splines"></a>방법: 카디널 스플라인 그리기
카디널 스플라인 주어진된 점의 집합을 통해 원활 하 게 전달 되는 곡선입니다. 카디널 스플라인 그리기, 하려면 만듭니다는 <xref:System.Drawing.Graphics> 개체를 가리키는 배열 주소 전달는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>종 모양 카디널 스플라인 그리기  
  
-   다음 예제에서는 5 개의 지정 된 점을 통해 전달 되는 종 모양의 카디널 스플라인을 그립니다. 다음 그림에서는 5 개의 점과 곡선을 보여 줍니다.  
  
     ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>폐쇄형된 카디널 스플라인 그리기  
  
-   사용 하 여는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스 되는 폐쇄형된 카디널 스플라인을 그립니다. 폐쇄형된 카디널 스플라인 곡선 배열에서 마지막 점을 계속 하 고 첫 번째 포인터는 배열에 연결 합니다. 다음 예제에서는 6 개의 지정 된 점을 통과 하는 폐쇄형된 카디널 스플라인을 그립니다. 다음 그림에서는 6 개 포인트에 따라 닫힌된 스플라인 보여 줍니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>카디널 스플라인 굴곡 변경  
  
-   카디널 스플라인의 장력 인수를 전달 하 여 굴곡 방식을 변경는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드. 다음 예제에서는 동일한 점 집합이 통과 하는 세 개의 카디널 스플라인을 그립니다. 다음 그림에서는 세 가지 스플라인 해당 장력 값과 함께 보여 줍니다. 참고는 장력이 0 인 점 직선으로 연결 되어 있습니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요한 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.  
  
## <a name="see-also"></a>참고 항목  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
