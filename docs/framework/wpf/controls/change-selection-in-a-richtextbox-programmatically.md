---
title: "프로그래밍 방식으로 RichTextBox의 선택 변경 | Microsoft Docs"
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
  - "RichTextBox의 선택 변경[WPF]"
  - "텍스트 상자의 선택 변경[WPF]"
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 프로그래밍 방식으로 RichTextBox의 선택 변경
이 예제에서는 <xref:System.Windows.Controls.RichTextBox>의 현재 선택을 자동으로 변경하는 방법을 보여 줍니다.  이 선택은 사용자가 사용자 인터페이스를 사용하여 콘텐츠를 선택한 것과 같습니다.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드에서는 간단한 콘텐츠가 있는 이름이 지정된 <xref:System.Windows.Controls.RichTextBox> 컨트롤을 설명합니다.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## 예제  
 다음 코드에서는 사용자가 <xref:System.Windows.Controls.RichTextBox> 내에서 클릭하면 몇 가지 임의의 텍스트를 프로그래밍 방식으로 선택합니다.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## 참고 항목  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)