---
title: "GDI+의 그래픽 경로"
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e027228ea1cc047f213c28ac3a4984c2f0227c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="graphics-paths-in-gdi"></a>GDI+의 그래픽 경로
경로 선, 사각형 및 간단한 곡선을 결합 하 여 구성 됩니다. 설명한 대로 [벡터 그래픽 개요](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) 다음과 같은 기본 빌딩 블록 그림 그리기에 대 한 가장 유용한 입증 되었습니다.  
  
-   선  
  
-   사각형  
  
-   타원  
  
-   타원  
  
-   다각형  
  
-   카디널 스플라인  
  
-   3 차원 곡선 스플라인  
  
 GDI +에서 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 사용 하면 단일 단위로 이러한 빌딩 블록의 시퀀스를 수집할 수 있습니다. 선, 사각형, 다각형 및 곡선의 전체 시퀀스를 호출 하 여 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다. 다음 그림에는 선, 호를 베 지 어 스플라인 및 카디널 스플라인을 결합 하 여 만든 경로 보여 줍니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>경로 사용 하 여  
 <xref:System.Drawing.Drawing2D.GraphicsPath> 을 그릴 수 있도록 항목의 시퀀스를 만들기 위한 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (카디널 스플라인 용) 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>합니다. 이러한 메서드의 오버 로드 됩니다. 즉, 각 메서드는 여러 가지 다른 매개 변수 목록을 지원합니다. 예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드 4 개의 정수 및 다른 변형이 수신는 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드 두 수신 <xref:System.Drawing.Point> 개체입니다.  
  
 경로에 선, 사각형 및 베 지 어 스플라인을 추가 하기 위한 메서드는 한 번의 호출 경로에 여러 개의 항목을 추가 하는 동반 메서드가: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>합니다. 또한는 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 메서드는 도우미 메서드가 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, 폐곡선 또는 원형 경로에 추가 하는 합니다.  
  
 패스를 그릴 하려면는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다. <xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체는 경로 렌더링 하는 데 사용 하는 줄의 색, 너비 등의 속성에 저장 합니다. <xref:System.Drawing.Drawing2D.GraphicsPath> 개체의 선 및 곡선의 경로 구성 하는 순서를 저장 합니다. <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드. 다음 예제에서는 줄, 타원, 및 되는 베 지 어 스플라인을 구성 되는 경로 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 다음 그림의 경로 보여 줍니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 선, 사각형 및 곡선으로 분할 경로 추가 하는 것 외에도 경로에 경로 추가할 수 있습니다. 이 옵션을 사용 하면 대규모의 복잡 한 경로 형성 하는 기존 경로 결합할 수 있습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 경로에 추가할 수 있습니다 다른 두 개의 항목이: 문자열 및 파이 합니다. 원형에는 타원의 내부의 일부입니다. 다음 예제에서는 호, 카디널 스플라인을, 문자열, 및 원형에서 경로 만듭니다.  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 다음 그림의 경로 보여 줍니다. 경로를; 연결 하지 않은 참고 호, 카디널 스플라인을, 문자열 및 원형 구분 됩니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
