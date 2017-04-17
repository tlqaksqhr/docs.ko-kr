---
title: "방법: 그린 텍스트 맞추기 | Microsoft Docs"
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
  - "텍스트, 맞추기"
  - "Windows Forms, 그린 텍스트 맞추기"
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 그린 텍스트 맞추기
사용자 지정 그리기를 수행할 때 폼이나 컨트롤에 그려진 텍스트를 가운데에 맞춰야 하는 경우가 많습니다.  올바른 서식 개체를 만들고 적절한 서식 플래그를 설정하여 <xref:System.Drawing.Graphics.DrawString%2A> 또는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드로 그린 텍스트를 손쉽게 맞출 수 있습니다.  
  
### GDI\+\(DrawString\)를 사용하여 가운데에 맞춰진 텍스트를 그리려면  
  
1.  적절한 <xref:System.Drawing.Graphics.DrawString%2A> 메서드와 함께 <xref:System.Drawing.StringFormat>을 사용하여 가운데에 맞춰진 텍스트를 지정합니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### GDI\(DrawText\)를 사용하여 가운데에 맞춰진 텍스트를 그리려면  
  
1.  <xref:System.Windows.Forms.TextFormatFlags> 열거형을 사용하여 텍스트를 래핑하고 적절한 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드를 사용하여 텍스트를 가로와 세로 방향으로 가운데에 맞춥니다.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## 코드 컴파일  
 앞의 코드 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)