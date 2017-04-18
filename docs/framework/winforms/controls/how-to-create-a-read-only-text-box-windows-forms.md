---
title: "방법: 읽기 전용 텍스트 상자 만들기(Windows Forms) | Microsoft Docs"
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
  - "읽기 전용 텍스트 상자"
  - "텍스트 상자, 읽기 전용"
  - "TextBox 컨트롤[Windows Forms], 읽기 전용"
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)
편집 가능한 Windows Forms 텍스트 상자를 읽기 전용 컨트롤로 변환할 수 있습니다.  예를 들어 일반적으로는 편집되지만 응용 프로그램 상태로 인해 현재 편집할 수 없는 값을 텍스트 상자에 표시할 수 있습니다.  
  
### 읽기 전용 텍스트 상자를 만들려면  
  
1.  <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을 `true`로 설정합니다.  이 속성을 `true`로 설정하면 텍스트 상자의 텍스트를 변경할 수는 없지만 스크롤하고 강조 표시할 수 있습니다.  또한 텍스트 상자에서 **복사** 명령은 사용할 수 있지만 **잘라내기**와 **붙여넣기** 명령은 사용할 수 없습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성은 런타임에 사용자 상호 작용에만 영향을 줍니다.  텍스트 상자의 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 변경하면 런타임에 프로그래밍 방식으로 텍스트 상자 내용을 변경할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)