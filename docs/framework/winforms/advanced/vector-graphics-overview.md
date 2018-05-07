---
title: 벡터 그래픽 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 31fec6d0d3769251d21783b4657d00b06431e942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vector-graphics-overview"></a>벡터 그래픽 개요
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 좌표계에 선, 사각형 및 기타 도형을 그립니다. 좌표 시스템의 다양 한에서 선택할 수 있지만 기본 좌표계 x 축이 오른쪽에 y 축은 아래쪽을 향하고 왼쪽 위 모퉁이에 원점에 있습니다. 기본 좌표 시스템의 측정 단위 픽셀입니다.  
  
## <a name="the-building-blocks-of-gdi"></a>GDI +의 구성 요소  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 컴퓨터 모니터의 점 그림 요소 또는 픽셀을 호출 하는 사각형 배열을에 디스플레이 만듭니다. 다음 모니터를 한 화면에 표시 하는 픽셀 수가 다릅니다 있으며 각 모니터에 표시 되는 픽셀 수 일반적으로 구성할 수 있습니다 어느 정도 까지는 사용자가 있습니다.  
  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선, 사각형 또는 곡선을 그리려면 항목에 대 한 주요 정보를 제공 합니다. 예를 들어 두 점을 제공 하 여 줄을 지정할 수 있습니다 및 지정, 높이 및 너비를 제공 하 여 사각형을 지정할 수 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 픽셀을 선, 사각형 또는 곡선을 표시 하도록 설정 해야 결정 하는 디스플레이 드라이버 소프트웨어와 함께 작동 합니다. 다음 그림에서는 점 (12, 8) (4, 2) 점에서 선을 표시 하려면 켜져 있는 픽셀을 보여 줍니다.  
  
 ![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 시간이 지남에 따라 특정 기본 빌딩 블록 입증 된 2 차원 그림을 만드는 데 가장 유용 합니다. 지원 이러한 빌딩 블록 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 다음 목록에 지정 됩니다.  
  
-   선  
  
-   사각형  
  
-   타원  
  
-   타원  
  
-   다각형  
  
-   카디널 스플라인  
  
-   3차원 곡선 스플라인  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>그래픽 개체를 사용 하 여 그리기 위한 메서드  
 <xref:System.Drawing.Graphics> 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 위 목록에 항목을 그리기 위한 메서드를 제공: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (카디널 스플라인 용) 및 <xref:System.Drawing.Graphics.DrawBezier%2A>. 이러한 메서드의 오버 로드 됩니다. 즉, 각 메서드는 여러 가지 다른 매개 변수 목록을 지원합니다. 예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 다른 변형이 하는 동안 4 개의 정수는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 두 개의 <xref:System.Drawing.Point> 개체입니다.  
  
 선, 사각형 및 3 차원 곡선 스플라인 그리기 위한 메서드는 단일 호출에서 여러 항목을 그릴 동반 메서드: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, 및 <xref:System.Drawing.Graphics.DrawBeziers%2A>합니다. 또한는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드 도우미 메서드를가지고 <xref:System.Drawing.Graphics.DrawClosedCurve%2A>닫히는 연결 곡선의 끝 지점을 시작 하 여 곡선 지점, 합니다.  
  
 모든 그리기 메서드에 <xref:System.Drawing.Graphics> 와 함께에서 작업 클래스는 <xref:System.Drawing.Pen> 개체입니다. 모든 항목을 그리려면 개체 두 개 이상 만들어야 합니다:는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다. <xref:System.Drawing.Pen> 개체 선 두께 및 색을 그릴 수 있도록 항목의 같은 특성을 저장 합니다. <xref:System.Drawing.Pen> 개체 그리기 메서드를 인수 중 하나로 전달 됩니다. 예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 너비를 100, 50의 높이의 왼쪽 위 모퉁이를 사각형 그리기 다음 예에서 같이 4 개의 정수 (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
