---
title: "방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시 | Microsoft Docs"
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
  - "RichTextBox 컨트롤[Windows Forms], 스크롤 막대 표시"
  - "스크롤 막대, 컨트롤에 표시"
  - "텍스트 상자, 스크롤 막대 표시"
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시
기본적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 필요에 따라 가로 및 세로 스크롤 막대가 표시됩니다.  <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성에는 아래 표에 있는 7개의 값을 지정할 수 있습니다.  
  
### RichTextBox 컨트롤에서 스크롤 막대를 표시하려면  
  
1.  <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `true`으로 설정합니다.  <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `false`로 설정하면 가로 스크롤 막대뿐만 아니라 모든 종류의 스크롤 막대가 표시되지 않습니다.  
  
2.  <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성을 <xref:System.Windows.Forms.RichTextBoxScrollBars> 열거형의 값으로 설정합니다.  
  
    |값|설명|  
    |-------|--------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>\(기본값\)|텍스트가 컨트롤의 너비나 높이보다 긴 경우 가로 스크롤 막대, 세로 스크롤 막대 또는 둘 다 표시됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|스크롤 막대가 표시되지 않습니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|텍스트가 컨트롤의 너비보다 긴 경우 가로 스크롤 막대만 표시됩니다.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정된 경우에만 가능합니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|텍스트가 컨트롤의 높이보다 긴 경우 세로 스크롤 막대만 표시됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정되어 있는 경우에도 가로 스크롤 막대가 표시됩니다.  이 때 텍스트가 컨트롤의 너비보다 길지 않으면 가로 스크롤 막대가 흐리게 표시됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|세로 스크롤 막대가 항상 표시됩니다.  이 때 텍스트가 컨트롤의 높이보다 길지 않으면 세로 스크롤 막대가 흐리게 표시됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|세로 스크롤 막대가 항상 표시되고  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정되어 있는 경우에도 가로 스크롤 막대가 표시됩니다.  이 때 텍스트가 컨트롤의 너비나 높이보다 길지 않으면 스크롤 막대가 흐리게 표시됩니다.|  
  
3.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-------|--------|  
    |`false`|컨트롤의 텍스트가 컨트롤 너비에 맞게 자동으로 조정되지 않으므로 줄 바꿈 문자가 나타날 때까지 오른쪽으로 스크롤됩니다.  이전 단계에서 ScrollBars 속성을 Horizontal 또는 Both로 설정한 경우 이 값을 사용합니다.|  
    |`true`\(기본값\)|컨트롤의 텍스트가 컨트롤 너비에 맞게 자동으로 조정되고  가로 스크롤 막대가 나타나지 않습니다.  이전 단계에서 ScrollBars 속성을 Vertical 또는 None으로 설정하여 하나 이상의 단락을 표시하는 경우 이 값을 사용합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)