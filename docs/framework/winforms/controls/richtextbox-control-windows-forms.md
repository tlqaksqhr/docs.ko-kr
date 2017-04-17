---
title: "RichTextBox 컨트롤(Windows Forms) | Microsoft Docs"
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
  - "rich edit 컨트롤"
  - "RichTextBox 컨트롤[Windows Forms]"
  - "텍스트 상자"
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# RichTextBox 컨트롤(Windows Forms)
Windows Forms `RichTextBox` 컨트롤은 서식 있는 텍스트를 표시, 입력 및 조작하는 데 사용됩니다.  `RichTextBox` 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤의 모든 기능을 수행할 수 있으며, 그 외에도 글꼴, 색 및 링크를 표시하고, 파일로부터 텍스트 및 포함 이미지를 로드하고, 편집 작업을 실행 취소하거나 다시 실행하고, 지정된 문자를 검색할 수 있습니다.  `RichTextBox` 컨트롤은 대개 텍스트를 조작하고 Microsoft Word와 같은 워드프로세서 응용 프로그램과 유사한 기능을 표시하는 데 사용됩니다.  <xref:System.Windows.Forms.TextBox> 컨트롤처럼 `RichTextBox` 컨트롤에서도 스크롤 막대를 표시할 수 있습니다. 그러나 <xref:System.Windows.Forms.TextBox> 컨트롤과 달리 이 컨트롤은 기본적으로 가로 스크롤 막대와 세로 스크롤 막대를 모두 표시하며, 추가적인 스크롤 막대 설정을 가지고 있습니다.  
  
## 단원 내용  
 [RichTextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 `RichTextBox` 컨트롤의 일반적인 개념을 소개합니다. 이 컨트롤에서는 사용자가 서식 옵션을 사용하여 텍스트를 입력하고 표시하며 조작할 수 있습니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 `RichTextBox` 컨트롤에서 글꼴 및 단락 서식에 대한 변경 내용을 추적하는 방법에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 `RichTextBox` 컨트롤에서 스크롤 막대에 적용할 수 있는 여러 옵션에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 `RichTextBox` 컨트롤에서 웹 사이트에 연결하는 방법에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 데이터를 `RichTextBox` 컨트롤에 끌어서 놓는 방법에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤에 파일 로드](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 기존 파일을 `RichTextBox` 컨트롤에 로드하는 방법을 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 `RichTextBox` 컨트롤의 내용을 파일에 저장하는 방법에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 `RichTextBox` 컨트롤에서 텍스트의 글꼴 패밀리, 크기, 스타일 및 색을 설정하는 방법에 대해 설명합니다.  
  
 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 `RichTextBox` 컨트롤에서 단락의 서식을 지정하는 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.RichTextBox> 클래스  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크가 포함되어 있습니다.  
  
## 관련 단원  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Windows Forms 컨트롤의 전체 목록을 제공하고 컨트롤 사용 정보에 대한 링크를 포함합니다.  
  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <xref:System.Windows.Forms.TextBox> 컨트롤의 일반적인 개념을 소개합니다. 이 컨트롤에서는 사용자가 여러 줄의 텍스트를 입력하고 편집할 수 있습니다.