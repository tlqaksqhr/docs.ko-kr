---
title: "방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], Margin 속성"
  - "컨트롤[Windows Forms], 개요"
  - "컨트롤[Windows Forms], Padding 속성"
  - "Margin 속성[Windows Forms]"
  - "여백"
  - "여백, Windows Forms"
  - "Padding 속성[Windows Forms]"
  - "안쪽 여백, Windows Forms"
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기
다음 코드 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 주위에 테두리 또는 외곽선을 만드는 방법을 보여 줍니다.  예제에서는 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Padding> 속성 값을 5로 설정하고 자식 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A>를 <xref:System.Drawing.Color.Blue%2A>로 설정하면 <xref:System.Windows.Forms.RichTextBox> 컨트롤 주위에 파란색 테두리가 만들어집니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.Padding>   
 [Windows Forms 컨트롤의 여백 및 안쪽 여백](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)