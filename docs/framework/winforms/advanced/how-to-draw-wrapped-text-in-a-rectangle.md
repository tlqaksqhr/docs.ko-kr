---
title: '방법: 사각형 안에 줄 바꿈된 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>방법: 사각형 안에 줄 바꿈된 텍스트 그리기
사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드를 오버 로드는 <xref:System.Drawing.Graphics> 클래스를 사용 하는 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF> 매개 변수입니다. 사용할 수도 있습니다는 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Font>합니다.  
  
 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수도 있습니다는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드를 오버 로드는 <xref:System.Windows.Forms.TextRenderer> 를 사용 하는 <xref:System.Drawing.Rectangle> 및 <xref:System.Windows.Forms.TextFormatFlags> 매개 변수입니다. 사용할 수도 있습니다는 <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>합니다.  
  
 다음 그림과 텍스트 출력을 사용 하 여 그린 사각형에는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>GDI + 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기  
  
1.  사용 하 여는 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트를 전달 하는 메서드를 오버 로드 된 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Brush>합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>GDI 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기  
  
1.  사용 하 여는 <xref:System.Windows.Forms.TextFormatFlags> 와 텍스트를 지정 하려면 열거형 값을 래핑하는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 텍스트를 전달 하는 메서드를 오버 로드 된 <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Color>합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이전 예제 필요합니다.  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [방법: 지정된 위치에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
