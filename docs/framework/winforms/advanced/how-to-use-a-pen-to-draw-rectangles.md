---
title: "방법: 펜을 사용하여 사각형 그리기"
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
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 032f53ffe3bccd329b3e2eea4fbf13949f35c3cd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>방법: 펜을 사용하여 사각형 그리기
사각형 그리기, 하려면는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다. <xref:System.Drawing.Graphics> 개체를 제공는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체 선의 색 및 너비와 같은 기능을 저장 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 왼쪽 위 모퉁이가으로 사각형을 그립니다 (10, 10). 사각형의 너비를 100 고 50 높이입니다. 에 전달 되는 두 번째 인수는 <xref:System.Drawing.Pen.%23ctor%2A> 생성자 펜 너비는 5 픽셀 임을 나타냅니다.  
  
 사각형을 그릴 때 펜 사각형의 경계에서 가운데 맞춤 됩니다. 사각형의 면은 그려지는 5 픽셀의 펜 너비는 5 이므로 해당 1 픽셀 그려집니다 너비로 자체 경계에 2 픽셀은 내부적으로 그려지며 2 픽셀 바깥쪽에 그려집니다. 펜 맞춤에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 펜 굵기 설정 및 맞춤](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)합니다.  
  
 다음 그림에서는 결과 사각형을 보여 줍니다. 여기서 사각형 그려지는 펜 굵기 하나의 픽셀 했다면 점선은 표시 합니다. 사각형의 왼쪽 위 모퉁이의 확대 뷰 두꺼운 검정 선 가운데 해당 텍스트에 표시 됩니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
