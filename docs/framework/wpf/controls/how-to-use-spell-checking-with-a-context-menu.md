---
title: "방법: 상황에 맞는 메뉴로 맞춤법 검사 사용 | Microsoft Docs"
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
  - "텍스트 상자에서 맞춤법 검사 사용[WPF]"
  - "텍스트 상자에서 맞춤법 검사 다시 사용[WPF]"
  - "상황에 맞는 메뉴로 맞춤법 검사[WPF]"
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 상황에 맞는 메뉴로 맞춤법 검사 사용
기본적으로 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>와 같은 편집 컨트롤에서 맞춤법 검사를 사용하면 상황에 맞는 메뉴에 맞춤법 검사 옵션이 나타납니다.  예를 들어 사용자가 철자가 잘못된 단어를 마우스 오른쪽 단추로 클릭하면 철자 제안 단어 또는 **모두 무시** 옵션이 나타납니다.  하지만 기본으로 제공되는 상황에 맞는 메뉴를 사용자 지정 상황에 맞는 메뉴로 재정의하면 이 기능이 사라지므로 상황에 맞는 메뉴에 맞춤법 검사 기능이 다시 나타나도록 하려면 코드를 작성해야 합니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBox>에서 이 기능을 활성화하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 상황에 맞는 메뉴를 구현하는 데 사용하는 몇 가지 이벤트로 <xref:System.Windows.Controls.TextBox>를 만드는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 보여 줍니다.  
  
 [!code-xml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## 예제  
 다음 예제에서는 상황에 맞는 메뉴를 구현하는 코드를 보여 줍니다.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <xref:System.Windows.Controls.RichTextBox>에 이 작업을 수행하는 데 사용되는 코드는 비슷합니다.  가장 주된 차이는 `GetSpellingError` 메서드로 전달되는 매개 변수에 있습니다.  <xref:System.Windows.Controls.TextBox>의 경우에는 캐럿 위치의 정수 인덱스를 전달합니다.  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <xref:System.Windows.Controls.RichTextBox>의 경우에는 캐럿 위치를 지정하는 <xref:System.Windows.Documents.TextPointer>를 전달합니다.  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)   
 [TextBox에 사용자 지정 컨텍스트 메뉴 사용](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)