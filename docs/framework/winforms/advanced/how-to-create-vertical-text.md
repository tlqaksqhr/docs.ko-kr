---
title: "방법: 세로 텍스트 만들기 | Microsoft Docs"
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
  - "문자열[Windows Forms], 세로로 그리기"
  - "텍스트[Windows Forms], 세로로 그리기"
  - "세로 텍스트, 그리기"
  - "Windows Forms, 세로 텍스트 그리기"
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 세로 텍스트 만들기
<xref:System.Drawing.StringFormat> 개체를 사용하면 텍스트를 가로 대신 세로로 그리도록 지정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Drawing.StringFormatFlags> 값을 <xref:System.Drawing.StringFormat> 개체의 <xref:System.Drawing.StringFormat.FormatFlags%2A> 속성에 할당합니다.  해당 <xref:System.Drawing.StringFormat> 개체가 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달됩니다.  <xref:System.Drawing.StringFormatFlags> 값은 <xref:System.Drawing.StringFormatFlags> 열거형의 멤버입니다.  
  
 아래 그림에서는 세로로 표시된 텍스트를 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## 코드 컴파일  
  
-   앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e` 를 필요로 합니다.  
  
## 참고 항목  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)