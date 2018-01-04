---
title: "방법: 질감으로 채워진 선 그리기"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aaba7981dc68bf7bdfe6dbd45685e61f7b763a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>방법: 질감으로 채워진 선 그리기
단색으로 선 대신, 질감으로 줄을 그릴 수 있습니다. 선 및 곡선 질감으로을 그리려면 만듭니다는 <xref:System.Drawing.TextureBrush> 개체를 전달 하는 <xref:System.Drawing.TextureBrush> 개체를 한 <xref:System.Drawing.Pen.%23ctor%2A> 생성자입니다. 펜의 스트로크 바둑판식으로 배열 된 질감의 특정 픽셀에서 확인 되 면 펜 선 또는 곡선 그리면 및 질감 브러시와 연결 된 비트맵 평면 (눈에 보이지 않게) 타일에 사용 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 한 <xref:System.Drawing.Bitmap> 개체 파일에서 `Texture1.jpg`합니다. 해당 비트맵 생성에 사용 되는 <xref:System.Drawing.TextureBrush> 개체 및 <xref:System.Drawing.TextureBrush> 개체를 생성 하는 데 사용 됩니다는 <xref:System.Drawing.Pen> 개체입니다. 에 대 한 호출 <xref:System.Drawing.Graphics.DrawImage%2A> 왼쪽 위 모퉁이가 인 비트맵을 그립니다 (0, 0). 에 대 한 호출 <xref:System.Drawing.Graphics.DrawEllipse%2A> 사용 하 여는 <xref:System.Drawing.Pen> 질감된 타원을 그릴 개체입니다.  
  
 다음 그림에서는 비트맵 및 질감된 타원을 보여 줍니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 앞의 코드에 붙여는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다. 대체 `Texture.jpg` 를 시스템에서 사용할 이미지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
