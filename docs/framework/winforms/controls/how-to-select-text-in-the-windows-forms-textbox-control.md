---
title: "방법: Windows Forms TextBox 컨트롤에서 텍스트 선택 | Microsoft Docs"
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
  - "텍스트 상자, 프로그래밍 방식으로 텍스트 선택"
  - "텍스트, 프로그래밍 방식으로 텍스트 상자에서 선택"
  - "TextBox 컨트롤[Windows Forms], 프로그래밍 방식으로 텍스트 선택"
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 방법: Windows Forms TextBox 컨트롤에서 텍스트 선택
Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤에서 프로그래밍 방식으로 텍스트를 선택할 수 있습니다.  예를 들어, 텍스트의 특정 문자열을 검색하는 함수를 만드는 경우 텍스트를 선택하여 검색된 문자열의 위치를 시각적으로 알려줄 수 있습니다.  
  
### 프로그래밍 방식으로 텍스트를 선택하려면  
  
1.  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 선택할 텍스트 시작 지점으로 설정합니다.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성은 텍스트 문자열의 삽입 지점을 나타내는 숫자이며 0으로 설정하면 가장 왼쪽이 됩니다.  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성이 텍스트 상자의 문자 개수와 같거나 큰 경우 마지막 문자 뒤에 삽입 지점이 위치합니다.  
  
2.  <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택할 텍스트의 길이로 설정합니다.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성은 삽입 지점의 너비를 설정하는 숫자 값입니다.  <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>를 0보다 큰 값으로 설정하면 현재 삽입 지점부터 해당 값만큼의 문자들이 선택됩니다.  
  
3.  필요에 따라 <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> 속성을 사용하여 선택한 텍스트에 액세스합니다.  
  
     아래 코드에서는 컨트롤의 <xref:System.Windows.Forms.Control.Enter> 이벤트가 발생할 경우 텍스트 상자의 내용을 선택합니다.  이 예제에서는 텍스트 상자에 있는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성의 값이 `null` 또는 빈 문자열이 아닌지 검사합니다.  텍스트 상자가 포커스를 받으면 텍스트 상자의 현재 텍스트가 선택됩니다.  `TextBox1_Enter` 이벤트 처리기는 컨트롤에 바인딩되어야 합니다. 자세한 내용은 [방법: 런타임에 Windows Forms의 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조하십시오.  
  
     이 예제를 테스트하려면 텍스트 상자가 포커스를 받을 때까지 Tab 키를 누릅니다.  텍스트 상자를 클릭하면 텍스트가 선택 취소됩니다.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)