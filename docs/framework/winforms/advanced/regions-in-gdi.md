---
title: "GDI+의 영역"
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d3805c2d67f5241425ef72d3802aba996d33cfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="regions-in-gdi"></a>GDI+의 영역
영역에는 출력 장치의 표시 영역의 일부입니다. 영역 (단일 사각형) 단순 또는 복합 (다각형 및 폐곡선 조합) 될 수 있습니다. 다음 그림에는 두 개의 영역을 보여 줍니다: 하나는 사각형에서 구현 되 고 다른 경로에서 구성 됩니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>영역 사용  
 영역은 자주 클리핑에 사용 및 적중 테스트 합니다. 클리핑은 그리기의 표시 영역을 업데이트 해야 하는 부분 일반적으로 특정 영역으로 제한 하는 작업이 포함 됩니다. 적중 테스트는 마우스 단추를 누를 때 커서 화면의 특정 영역에 인지 확인할 수 있습니다.  
  
 사각형 또는 경로에서 영역을 만들 수 있습니다. 기존 영역을 결합 하 여 복잡 한 영역을 만들 수도 있습니다. <xref:System.Drawing.Region> 영역을 결합 하기 위한 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, 및 <xref:System.Drawing.Region.Complement%2A>합니다.  
  
 두 지역의 교집합 영역 모두에 속하는 모든 데이터 요소 집합입니다. Union은 하나 또는 다른 또는 두 지역에 속한 모든 데이터 요소 집합입니다. 영역의 보수는 지역에 있지 않은 모든 데이터 요소 집합입니다. 다음 그림에서는 교차와 앞의 그림에 표시 된 두 개의 영역의 합집합을 보여 줍니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 <xref:System.Drawing.Region.Xor%2A> 메서드를 쌍의 영역에 적용 한 지역 또는 서로 다르다는 것에 속해 있는 모든 점을 포함 하는 영역을 생성 합니다. <xref:System.Drawing.Region.Exclude%2A> 메서드를 쌍의 영역에 적용 된 첫 번째 지역에 두 번째 지역에 있지 않은 모든 점을 포함 하는 영역을 생성 합니다. 다음 그림에는 적용 지역이 표시는 <xref:System.Drawing.Region.Xor%2A> 및 <xref:System.Drawing.Region.Exclude%2A> 메서드를이 항목의 시작 부분에 표시 된 두 개의 영역입니다.  
  
 ![영역](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 영역을 채울 필요는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Brush> 개체 및 <xref:System.Drawing.Region> 개체입니다. <xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.FillRegion%2A> 메서드, 및 <xref:System.Drawing.Brush> 개체 특성 채우기 색 또는 패턴을 저장 합니다. 다음 예제를 단색으로 영역을 채웁니다.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [영역 사용](../../../../docs/framework/winforms/advanced/using-regions.md)
