---
title: "방법: Windows Form에 텍스트 그리기"
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
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e663f455a348b2699331ec5bf1ea6df2e54493
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-on-a-windows-form"></a>방법: Windows Form에 텍스트 그리기
다음 코드 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 폼에 텍스트를 그리는 합니다. 사용할 수 있습니다 <xref:System.Windows.Forms.TextRenderer> 폼에 텍스트를 그리기 위한 합니다. 자세한 내용은 참조 [하는 방법: GDI와 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)합니다.  
  
## <a name="example"></a>예  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 호출할 수 없습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 에서 메서드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다. 그려지는 콘텐츠 활성 및 비활성 폼 크기를 조정 하거나 다른 형식으로 가려진 경우. 자동으로 다시 그려야 하 여 콘텐츠를 재정의 해야 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   Arial 글꼴 설치 되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
