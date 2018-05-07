---
title: '방법: GDI를 사용하여 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: e18ff96ea97eb636de8ab73aaa094c07b10fd456
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-with-gdi"></a>방법: GDI를 사용하여 텍스트 그리기
와 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 에서 메서드는 <xref:System.Windows.Forms.TextRenderer> 클래스에 액세스할 수 있습니다 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 폼 이나 컨트롤에 텍스트를 그리기 위한 기능입니다. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트 렌더링은 일반적으로 더 나은 성능과 더 정확한 텍스트 보다 측정 제공 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드는 <xref:System.Windows.Forms.TextRenderer> 인쇄를 위한 클래스를 사용할 수 없습니다. 인쇄할 때 항상 사용는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용 하 여 사각형 내에서 여러 줄 텍스트를 그리는 방법을 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 텍스트를 렌더링 하는 <xref:System.Windows.Forms.TextRenderer> 필요한 클래스는 <xref:System.Drawing.IDeviceContext>와 같은 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Font>, 텍스트 및 있는 것을 그려야 색을 그리는 데 위치 합니다. 필요에 따라 사용 하 여 텍스트 서식을 지정할 수 있습니다는 <xref:System.Windows.Forms.TextFormatFlags> 열거형입니다.  
  
 구입에 대 한 자세한 내용은 <xref:System.Drawing.Graphics>, 참조 [하는 방법: 그리기에 대 한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)합니다. 구성에 대 한 자세한 내용은 <xref:System.Drawing.Font>, 참조 [하는 방법: 글꼴 패밀리를 생성 및 글꼴](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이전 코드 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요는 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
