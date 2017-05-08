---
title: "방법: 사각형 안에 줄 바꿈된 텍스트 그리기 | Microsoft Docs"
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
  - "문자열[Windows Forms], 사각형에 그리기"
  - "텍스트[Windows Forms], 사각형에 그리기"
  - "Windows Forms, 사각형에 텍스트 그리기"
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 사각형 안에 줄 바꿈된 텍스트 그리기
<xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF> 매개 변수를 사용하는 <xref:System.Drawing.Graphics> 클래스의 오버로드된 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 사각형 안에 줄 바꿈된 텍스트를 그릴 수 있습니다.  <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Font>도 사용해야 합니다.  
  
 <xref:System.Drawing.Rectangle> 및 <xref:System.Windows.Forms.TextFormatFlags> 매개 변수를 사용하는 <xref:System.Windows.Forms.TextRenderer>의 오버로드된 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용하여 사각형 안에 줄 바꿈된 텍스트를 그릴 수도 있습니다.  <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>도 사용해야 합니다.  
  
 다음 그림에서는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 사각형 안에 그린 텍스트의 출력을 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### GDI\+를 사용하여 사각형 안에 줄 바꿈된 텍스트를 그리려면  
  
1.  오버로드된 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 원하는 텍스트, <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Brush>를 전달합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### GDI를 사용하여 사각형 안에 줄 바꿈된 텍스트를 그리려면  
  
1.  <xref:System.Windows.Forms.TextFormatFlags> 열거형 값을 사용하면 원하는 텍스트, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Color>를 전달하여 오버로드된 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드로 줄 바꿈할 텍스트를 지정할 수 있습니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`  
  
## 참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [방법: 지정된 위치에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)