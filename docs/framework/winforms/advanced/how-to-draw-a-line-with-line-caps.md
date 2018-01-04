---
title: "방법: 선 끝이 있는 선 그리기"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>방법: 선 끝이 있는 선 그리기
선 끝을 호출 하는 여러 셰이프 중 하나에 시작 또는 끝 줄을 그릴 수 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]화살촉이 라운드, 사각형, 다이아몬드 등 여러 선 끝을 지원합니다.  
  
## <a name="example"></a>예  
 선 끝 줄 (시작 cap), (end cap) 줄의 끝 또는 대시 (대시 cap) 파선의 시작에 대 한를 지정할 수 있습니다.  
  
 다음 예제에서는 다른 쪽 끝에서 둥근 단면 화살촉이 한쪽 끝에 선을 그립니다. 그림에는 결과 선을 나타냅니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 예제 코드를 붙여는 <xref:System.Windows.Forms.Control.Paint> 전달 하는 이벤트 처리기 `e` 으로 <xref:System.Windows.Forms.PaintEventArgs>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
