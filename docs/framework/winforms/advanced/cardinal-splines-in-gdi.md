---
title: GDI+의 카디널 스플라인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 93ae09c72415fa489e62f753e51e5a3ffcfb2425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cardinal-splines-in-gdi"></a>GDI+의 카디널 스플라인
카디널 스플라인에 더 큰 곡선을 형성 하는 개별 곡선 시퀀스입니다. 스플라인을은 포인트와 장력 매개 변수 배열에 의해 지정 됩니다. 카디널 스플라인; 배열에서 각 지점 매끄럽게 통과 날카로운 모퉁이가 없고 및 곡선의 다듬기에 급격 한 변경 내용이 없습니다. 다음 그림의 점과 집합의 각 요소를 통해 전달 되는 카디널 스플라인을 집합을 보여 줍니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>물리적 및 수학 곡선 스플라인  
 실제 스플라인은 목재 또는 유연한 기타 자료의 씬. 수학 스플라인 도입 되기 전에 디자이너는 곡선을 그리는 물리적 스플라인을 사용 합니다. 디자이너는 스플라인 종이에 배치 하 고 주어진된 점의 집합에 고정할 게 됩니다. 디자이너 만들 수는 곡선 스플라인 따라 그리는 방식으로 펜 또는 연필을 사용. 지정 된 일련의 점으로 다양 한 물리적 스플라인의 속성에 따라 곡선을 향상 시킬 합니다. 예를 들어 만들었을 높은 저항 잘 매우 유연한 스플라인 보다 다른 곡선을 생성 합니다.  
  
 수학 스플라인에 대 한 수식은 수학적 스플라인에 의해 만들어진 곡선의 곡선 물리적 스플라인으로 만들어 졌 던 비슷합니다 되므로 유연한 막대의 속성에 기반 합니다. 장력이 다른 물리적 스플라인 주어진된 점의 집합을 통해 다른 곡선을 생성 합니다, 처럼 수학 스플라인 장력 매개 변수에 대해 서로 다른 값으로는 주어진된 점의 집합을 통해 다른 곡선을 생성 합니다. 다음 그림에서는 동일한 점 집합을 통해 전달 되는 4 개의 카디널 스플라인 보여 줍니다. 각 스플라인 장력이 표시 됩니다. 0의 장력 점 간 최단 방식으로 (직선)를 사용 하 여 물리적 장력이 무한에 해당 합니다. 1의 장력 스플라인을 이상 총 벤드는 경로 없음 물리적 장력에 해당 합니다. 장력 값이 1 보다 큰, 곡선 긴 경로에 푸시 압축된 spring 처럼 동작 합니다.  
  
 ![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 앞의 그림에 4 개의 스플라인 시작 지점에 동일한 탄젠트 라인을 공유 합니다. 탄젠트는 곡선을 따라 다음 점으로 시작 지점에서 가져온 선입니다. 마찬가지로, 공유의 탄젠트 끝점은 곡선의 끝점에서 이전 지점으로 그린 선입니다.  
  
 카디널 스플라인 그리기, 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스는 <xref:System.Drawing.Pen>, 및의 배열을 <xref:System.Drawing.Point> 개체의 인스턴스는 <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.DrawCurve%2A> 스플라인을 그립니다, 메서드 및 <xref:System.Drawing.Pen> 선 두께 및 색 등 스플라인의 특성을 저장 합니다. 배열 <xref:System.Drawing.Point> 곡선은 통과 하는 지점을 저장 하는 개체입니다. 다음 코드 예제에는에 있는 요소를 통해 전달 되는 카디널 스플라인의 그리는 방법을 보여 줍니다 `myPointArray`합니다. 세 번째 매개 변수는 장력 합니다.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>참고 항목  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [곡선 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
