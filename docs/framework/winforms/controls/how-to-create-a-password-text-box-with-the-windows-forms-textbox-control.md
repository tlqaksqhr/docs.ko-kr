---
title: "방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기 | Microsoft Docs"
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
  - "암호란, 만들기"
  - "텍스트 상자의 PasswordChar 속성"
  - "암호, 입력 마스크"
  - "암호, 암호 입력란"
  - "TextBox 컨트롤[Windows Forms], 암호 입력"
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기
암호 상자는 사용자가 문자열을 입력하는 동안 자리 표시자 문자가 표시되는 Windows Forms 텍스트 상자입니다.  
  
### 암호 텍스트 상자를 만들려면  
  
1.  <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성을 특정 문자로 설정합니다.  
  
     <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성은 텍스트 상자에 표시되는 문자를 지정합니다.  예를 들어 암호 상자에 별표를 표시하려면 속성 창에서 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성에 별표\(\*\)를 지정합니다.  이렇게 하면 텍스트 상자에 입력하는 문자가 모두 별표로 표시됩니다.  
  
2.  \(옵션\) <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> 속성을 설정합니다.  이 속성은 텍스트 상자에 입력할 수 있는 문자 수를 지정합니다.  최대 길이를 초과하면 시스템에서 경고음이 울리고 텍스트 상자에 더 이상 문자를 입력할 수 없습니다.  최대 암호 길이를 지정하면 암호를 추측하려는 해커에게 이용될 수 있으므로 문자 수를 지정하지 않을 수도 있습니다.  
  
     다음 코드 예제에서는 최대 14개의 문자를 입력할 수 있고 입력한 문자열 대신 별표가 표시되도록 텍스트 상자를 초기화하는 방법을 보여 줍니다.  `InitializeMyControl`  프로시저는 자동으로 실행되지 않으므로 직접 호출해야 합니다.  
  
    > [!IMPORTANT]
    >  텍스트 상자에 대해 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성을 사용하면 사용자가 암호를 입력할 때 다른 사람이 보더라도 암호를 알아낼 수 없습니다.  이 보안 방법은 응용 프로그램 논리에 의해 암호가 저장 및 전송되는 경우에는 해결책이 될 수 없습니다.  입력된 텍스트는 어떤 방법으로도 암호화되지 않으므로 다른 기밀 데이터의 경우처럼 처리해야 합니다.  표시되는 모양은 다르지만 추가 보안 방법을 구현하지 않는 이상 암호는 계속 일반 텍스트 문자열처럼 처리됩니다.  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)