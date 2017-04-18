---
title: "방법: 지정된 위치에 텍스트 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "텍스트 그리기"
  - "텍스트 그리기, 지정된 위치[Windows Forms]"
  - "텍스트, 지정된 위치에 그리기[Windows Forms]"
  - "Windows Forms, 지정된 위치에 텍스트 그리기"
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 지정된 위치에 텍스트 그리기
사용자 지정 그리기를 수행할 때 텍스트를 지정된 위치에서 가로줄 하나로 그릴 수 있습니다.  <xref:System.Drawing.Point> 또는 <xref:System.Drawing.PointF> 매개 변수를 사용하는 <xref:System.Drawing.Graphics> 클래스의 오버로드된 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 이러한 방식으로 텍스트를 그릴 수 있습니다.  <xref:System.Drawing.Graphics.DrawString%2A> 메서드에는 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Font>도 필요합니다.  
  
 <xref:System.Windows.Forms.TextRenderer>에서 <xref:System.Drawing.Point>를 사용하는 오버로드된 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용할 수도 있습니다.  <xref:System.Windows.Forms.TextRenderer.DrawText%2A>에는 <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>도 필요합니다.  
  
 다음 그림에서는 오버로드된 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 지정된 위치에 그린 텍스트의 출력을 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### GDI\+를 사용하여 한 줄의 텍스트를 그리려면  
  
1.  원하는 텍스트, <xref:System.Drawing.Point> 또는 <xref:System.Drawing.PointF>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Brush>를 전달하여 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### GDI를 사용하여 한 줄의 텍스트를 그리려면  
  
1.  원하는 텍스트, <xref:System.Drawing.Point>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Color>를 전달하여 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`  
  
## 참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [방법: 사각형 안에 줄 바꿈된 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)