---
title: '방법: 구부러진 경로를 선으로 펴기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a3a8467dc5906a88911672316bb0f2ed3607d3a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>방법: 구부러진 경로를 선으로 펴기
A <xref:System.Drawing.Drawing2D.GraphicsPath> 선과 베 지 어 스플라인을의 시퀀스를 저장 하는 개체입니다. 경로에 여러 종류의 곡선 (줄임표, 타원, 카디널 스플라인)를 추가할 수 있습니다 하지만 경로에 저장 되기 전에 각 곡선 되는 베 지 어 스플라인을으로 변환 됩니다. 병합 경로 일련의 직선 각 베 지 어 스플라인을 변환으로 구성 됩니다. 다음 그림 전후의 경로 보여 줍니다.  
  
 ![직선 및 곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>경로를  
  
-   호출 된 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 의 메서드는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다. <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 메서드 결합 된 경로 원래 경로 간의 최대 거리를 지정 하는 평면 인수를 받습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
