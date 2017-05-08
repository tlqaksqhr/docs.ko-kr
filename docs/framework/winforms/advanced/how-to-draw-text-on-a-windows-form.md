---
title: "방법: Windows Form에 텍스트 그리기 | Microsoft Docs"
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
  - "폼, 텍스트 그리기"
  - "텍스트, 그리기"
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Form에 텍스트 그리기
다음 코드 예제에서는 <xref:System.Drawing.Graphics>의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 폼에 텍스트를 그리는 방법을 보여 줍니다.  또는 <xref:System.Windows.Forms.TextRenderer>를 사용하여 폼에 텍스트를 그릴 수도 있습니다.  자세한 내용은 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)를 참조하십시오.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## 코드 컴파일  
 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 호출할 수 없습니다.  그려진 내용은 폼 크기가 조정되거나 다른 폼에 의해 가려지더라도 새로 그려지지 않습니다.  내용이 자동으로 다시 그려지려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의해야 합니다.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   Arial 글꼴이 설치되지 않은 경우  
  
## 참고 항목  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.TextFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)