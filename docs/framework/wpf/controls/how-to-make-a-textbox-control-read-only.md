---
title: "방법: TextBox 컨트롤을 읽기 전용으로 설정 | Microsoft Docs"
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
  - "읽기 전용 TextBox 컨트롤"
  - "TextBox 컨트롤 읽기 전용"
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: TextBox 컨트롤을 읽기 전용으로 설정
이 예제에서는 사용자 입력이나 수정을 허용하지 않도록 <xref:System.Windows.Controls.TextBox> 컨트롤을 구성하는 방법을 보여 줍니다.  
  
## 예제  
 사용자가 <xref:System.Windows.Controls.TextBox> 컨트롤의 콘텐츠를 수정하지 못하게 하려면 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성을 **true**로 설정합니다.  
  
 [!code-xml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성은 사용자 입력에만 영향을 미치며 <xref:System.Windows.Controls.TextBox> 컨트롤의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설명에 설정된 텍스트나 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 통해 프로그래밍 방식으로 설정된 텍스트에는 영향을 미치지 않습니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>의 기본값은 **false**입니다.  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)