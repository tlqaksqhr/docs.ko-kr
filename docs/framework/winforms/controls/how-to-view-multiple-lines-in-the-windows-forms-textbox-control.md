---
title: "방법: Windows Forms TextBox 컨트롤에 여러 줄 표시 | Microsoft Docs"
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
  - "캐리지 리턴"
  - "CRLF"
  - "줄 끝"
  - "줄 바꿈"
  - "TextBox 컨트롤의 MultiLine 속성"
  - "줄 바꿈"
  - "ScrollBars 속성, TextBox 컨트롤"
  - "TextBox 컨트롤[Windows Forms], 여러 줄 보기"
  - "WordWrap 속성"
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms TextBox 컨트롤에 여러 줄 표시
기본적으로 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤에는 한 줄 텍스트가 표시되고 스크롤 막대가 표시되지 않습니다.  따라서 사용 가능한 공간에 비해 텍스트 길이가 길면 해당 텍스트의 일부만 표시됩니다.  <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 및 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정하여 이러한 기본 동작을 변경할 수 있습니다.  
  
### TextBox 컨트롤에 캐리지 리턴을 표시하려면  
  
-   여러 줄 <xref:System.Windows.Forms.TextBox>에 캐리지 리턴을 표시하려면 <xref:System.Environment.NewLine%2A> 속성을 사용합니다.  
  
     이스케이프 문자\(\\\)를 해석하는 방법은 언어에 따라 다르므로 주의하십시오.  Visual Basic에서는 캐리지 리턴과 줄 바꿈 문자 조합에 `Chr$(13) & Chr$(10)` 문자를 사용합니다.  
  
### TextBox 컨트롤에 여러 줄 텍스트를 표시하려면  
  
1.  <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`으로 설정합니다.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `true`\(기본값\)이면 컨트롤의 텍스트가 하나 이상의 단락으로 표시되고 그렇지 않으면 컨트롤 가장자리에서 일부 텍스트 줄이 잘린 목록으로 표시됩니다.  
  
2.  <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-------|--------|  
    |<xref:System.Windows.Forms.ScrollBars>|대부분의 텍스트 단락이 컨트롤 크기에 맞을 경우 이 값을 사용합니다.  텍스트가 너무 길어 한 번에 모두 표시할 수 없는 경우 마우스 포인터를 사용하여 컨트롤 내부에서 이동할 수 있습니다.|  
    |<xref:System.Windows.Forms.ScrollBars>|일부 텍스트 줄이 <xref:System.Windows.Forms.TextBox> 컨트롤의 너비보다 긴 목록을 표시하려면 이 값을 사용합니다.|  
    |<xref:System.Windows.Forms.ScrollBars>|컨트롤의 높이보다 긴 목록을 표시하려면 이 값을 사용합니다.|  
  
3.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-------|--------|  
    |`false`|컨트롤의 텍스트가 자동으로 줄 바꿈되지 않으므로 줄이 끝날 때까지 오른쪽으로 스크롤됩니다.  이전 단계에서 ScrollBars 속성을 <xref:System.Windows.Forms.ScrollBars> 또는 <xref:System.Windows.Forms.ScrollBars>로 설정한 경우 이 값을 사용합니다.|  
    |`true`\(기본값\)|가로 스크롤 막대가 나타나지 않습니다.  이전 단계에서 ScrollBars 속성을 <xref:System.Windows.Forms.ScrollBars> 또는 <xref:System.Windows.Forms.ScrollBars>으로 설정하여 하나 이상의 단락을 표시하는 경우 이 값을 사용합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)