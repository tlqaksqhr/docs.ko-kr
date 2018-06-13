---
title: GDI+에서 그리기 화면 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: b457e94acb334dc012f017090c63189de372592d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523925"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>GDI+에서 그리기 화면 제한
클리핑은 그리기 특정 사각형 또는 영역을 제한 하는 작업이 포함 됩니다. 다음 그림과 문자열 "Hello" 하트 모양의 영역 잘립니다.  
  
 ![제한 된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>클리핑 영역  
 영역 경로에서 생성 될 수 있습니다 및 클리핑에 대해 개략적으로 설명 된 텍스트를 사용할 수 있도록 경로 문자열의 윤곽을 포함할 수 있습니다. 다음 그림에는 텍스트 문자열의 내부에 클리핑된 동심 타원의 집합을 보여 줍니다.  
  
 ![제한 된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 클리핑을 그리려면 만들기는 <xref:System.Drawing.Graphics> 개체, 설정 해당 <xref:System.Drawing.Graphics.Clip%2A> 속성을 다음의 그리기 메서드를 호출 동일한 <xref:System.Drawing.Graphics> 개체:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [영역 사용](../../../../docs/framework/winforms/advanced/using-regions.md)
