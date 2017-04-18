---
title: "RichTextBox 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RichTextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "RichTextBox 컨트롤[Windows Forms], RichTextBox 컨트롤 정보"
  - "텍스트 상자, 텍스트 상자 정보"
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# RichTextBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 서식 있는 텍스트를 표시, 입력 및 조작하는 데 사용됩니다.  <xref:System.Windows.Forms.RichTextBox> 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤의 모든 기능을 수행할 뿐만 아니라 글꼴, 색 및 링크를 표시하고, 파일에서 텍스트 및 포함 이미지를 로드하고, 지정된 문자를 검색합니다.  <xref:System.Windows.Forms.RichTextBox> 컨트롤은 대개 텍스트를 조작하고 Microsoft Word와 같은 워드프로세서 응용 프로그램과 유사한 기능을 표시하는 데 사용됩니다.  <xref:System.Windows.Forms.TextBox> 컨트롤처럼 <xref:System.Windows.Forms.RichTextBox> 컨트롤도 스크롤 막대를 표시할 수 있지만 <xref:System.Windows.Forms.TextBox> 컨트롤과 달리 이 컨트롤은 기본적으로 필요에 따라 가로 및 세로 스크롤 막대를 모두 표시하며 스크롤 막대를 추가로 설정할 수도 있습니다.  
  
## RichTextBox 컨트롤 작업  
 <xref:System.Windows.Forms.TextBox> 컨트롤에서처럼 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 통해 표시할 텍스트를 설정합니다.  <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 텍스트 서식 지정에 사용되는 많은 속성이 포함되어 있습니다.  이러한 속성에 대한 자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) 및 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)을 참조하십시오.  파일 조작을 위해 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 및 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드는 일반 텍스트, 유니코드 일반 텍스트 및 RTF\(서식 있는 텍스트\)를 포함한 여러 종류의 파일 형식을 표시하고 작성할 수 있습니다.  사용 가능한 파일 형식은 [RichTextBoxStreamType 열거형](frlrfSystemWindowsFormsRichTextBoxStreamTypeClassTopic)에 나열되어 있습니다.  <xref:System.Windows.Forms.RichTextBox.Find%2A> 메서드를 사용하여 텍스트 문자열이나 특정 문자를 찾을 수 있습니다.  
  
 또한 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트 처리 코드를 작성하여 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 웹 스타일 링크에 대해 사용할 수 있습니다.  자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)를 참조하십시오.  <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> 속성을 `true`로 설정하여 사용자가 컨트롤의 전체 또는 일부 텍스트를 조작하지 못하도록 할 수 있습니다.  
  
 <xref:System.Windows.Forms.TextBoxBase.Undo%2A> 및 <xref:System.Windows.Forms.RichTextBox.Redo%2A> 메서드를 호출하여 <xref:System.Windows.Forms.RichTextBox> 컨트롤에서 수행한 대부분의 편집 작업을 실행 취소하거나 다시 실행할 수 있습니다.  <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> 메서드를 사용하면 사용자가 실행 취소한 마지막 작업을 해당 컨트롤에 다시 적용할 수 있는지 여부를 확인할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)