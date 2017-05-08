---
title: "방법: TextBox 컨트롤에서 포커스 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "포커스, 설정"
  - "TextBox 컨트롤, 포커스 설정"
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: TextBox 컨트롤에서 포커스 설정
이 예제에서는 <xref:System.Windows.UIElement.Focus%2A> 메서드를 사용하여 <xref:System.Windows.Controls.TextBox> 컨트롤에 포커스를 설정하는 방법을 보여 줍니다.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 *tbFocusMe*라는 간단한 <xref:System.Windows.Controls.TextBox> 컨트롤을 설명합니다.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.UIElement.Focus%2A> 메서드를 호출하여 *tbFocusMe*라는 <xref:System.Windows.Controls.TextBox> 컨트롤에 포커스를 설정합니다.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## 참고 항목  
 <xref:System.Windows.UIElement.Focusable%2A>   
 <xref:System.Windows.UIElement.IsFocused%2A>   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)