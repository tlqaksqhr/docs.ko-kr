---
title: "방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용 | Microsoft Docs"
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
  - "맞춤법 검사"
  - "실시간 맞춤법 검사"
  - "맞춤법 검사"
  - "맞춤법 검사기"
  - "TextBox 컨트롤, 실시간 맞춤법 검사"
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용
다음 예제에서는 <xref:System.Windows.Controls.SpellCheck> 클래스의 <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> 속성을 사용하여 <xref:System.Windows.Controls.TextBox>에서 실시간 맞춤법 검사를 사용하는 방법을 보여 줍니다.  
  
## 예제  
 [!code-xml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## 참고 항목  
 [상황에 맞는 메뉴로 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)