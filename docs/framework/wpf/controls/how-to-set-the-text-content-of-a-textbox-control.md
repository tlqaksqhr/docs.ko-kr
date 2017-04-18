---
title: "방법: TextBox 컨트롤의 텍스트 내용 설정 | Microsoft Docs"
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
  - "텍스트 내용, 설정"
  - "TextBox 컨트롤, 텍스트 콘텐츠 설정"
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: TextBox 컨트롤의 텍스트 내용 설정
이 예제에서는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 사용하여 <xref:System.Windows.Controls.TextBox> 컨트롤의 초기 텍스트 콘텐츠를 설정하는 방법을 보여 줍니다.  
  
 **참고** [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 버전의 예제에서는 각 단추의 <xref:System.Windows.Controls.TextBox> 콘텐츠 텍스트를 `<TextBox.Text>` 태그로 묶을 수도 있지만 <xref:System.Windows.Controls.TextBox>는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성에 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성을 적용하기 때문에 그럴 필요가 없습니다.  자세한 내용은 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  
  
## 예제  
 [!code-xml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## 예제  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)