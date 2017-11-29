---
title: "B &#233; zier GDI +의 곡선 스플라인"
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
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52cead578ad03052b5734c5b7a5b5a897dd48732
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="b233zier-splines-in-gdi"></a>B &#233; zier GDI +의 곡선 스플라인
점이 4 개로 지정 된 곡선을 베 지 어 스플라인을: 두 끝점 (p1 및 p2) 및 두 개의 제어점 (c1, c2). 곡선 p 1에서 시작 되 고 p 2에서 끝납니다. 곡선의 제어점 통해서도 전달 되지 않지만 제어점 자석과 곡선 특정 방향으로 가져와서 곡률 하는 방식에 영향을 주는 역할을 합니다. 다음 그림에서는 해당 끝점 및 제어점 함께 베 지 어 곡선을 보여 줍니다.  
  
 ![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 곡선 p 1에서 시작 하 고 제어점 c 1을 향해 이동 합니다. P 1에서 곡선 접선은 p 1에서 c 1에 그려진 선입니다. Endpoint p 2에서 접선은 c 2에서 p 2로 가져온 선입니다.  
  
## <a name="drawing-bzier-splines"></a>3 차원 곡선 스플라인 그리기  
 3 차원 곡선 스플라인 그리기, 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Pen>합니다. 인스턴스는 <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드, 및 <xref:System.Drawing.Pen> 너비는 곡선을 렌더링 하는 데 사용 되는 선의 색과 같은 특성을 저장 합니다. <xref:System.Drawing.Pen> 에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드. 나머지 인수에 전달 된 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드는 끝점 및 제어점입니다. 다음 예제에서는 시작 지점 (0, 0)으로 베 지 어 스플라인을 그립니다 포인트 (40, 20) 및 (80, 150)을 제어 하 고 끝 지점 (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 다음 그림에서는 곡선, 제어 지점 및 두 개의 접선을 보여 줍니다.  
  
 ![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 베 지 어 스플라인은 디자인 자동차 산업에 대 한 원래 피에르 베 지 어에서 개발한 것입니다. 다양 한 유형의 컴퓨터 보조 디자인에 유용한 것으로 입증 된 이후로 하며 글꼴 윤곽선을 정의 하는 됩니다. 베 지 어 스플라인을 다양 한 셰이프를 다음 그림에 나와 중 일부는 양도할 수 있습니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
