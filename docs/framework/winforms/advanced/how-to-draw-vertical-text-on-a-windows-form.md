---
title: "방법: Windows Form에 세로로 텍스트 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringFormat.FormatFlags"
  - "Graphics.DrawString"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "문자열[Windows Forms], 세로로 그리기"
  - "텍스트[Windows Forms], 그리기"
  - "텍스트[Windows Forms], 세로로 그리기"
  - "텍스트[Windows Forms], 세로 텍스트"
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Form에 세로로 텍스트 그리기
다음 코드 예제에서는 <xref:System.Drawing.Graphics>의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드를 사용하여 폼에 세로로 텍스트를 그리는 방법을 보여 줍니다.  
  
## 예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## 코드 컴파일  
 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 이 메서드를 호출할 수 없습니다.  그려진 내용은 폼 크기가 조정되거나 다른 폼에 의해 가려지더라도 새로 그려지지 않습니다.  내용이 자동으로 다시 그려지려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의해야 합니다.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   Arial 글꼴이 설치되지 않은 경우  
  
## 참고 항목  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)