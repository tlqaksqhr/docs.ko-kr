---
title: "방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어 | Microsoft Docs"
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
  - "삽입 지점, TextBox 컨트롤"
  - "텍스트 상자, 삽입점 제어"
  - "TextBox 컨트롤[Windows Forms], 삽입 위치"
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어
Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤이 처음으로 포커스를 받을 때 텍스트 상자의 기본 삽입 지점은 모든 텍스트의 왼쪽에 있습니다.  사용자는 키보드나 마우스로 삽입 지점을 이동할 수 있습니다.  텍스트 상자가 포커스를 잃은 다음 다시 포커스를 받을 경우 사용자의 이전 삽입 지점에 커서가 위치합니다.  
  
 일부의 경우 이러한 동작은 사용자에게 혼란을 줄 수 있습니다.  워드 프로세서 응용 프로그램의 경우 사용자는 새로 입력하는 문자가 기존 텍스트의 뒤에 표시될 것으로 예상합니다.  데이터 엔트리 응용 프로그램의 경우 사용자는 새로 입력하는 문자가 기존 엔트리를 덮어쓸 것으로 예상합니다.  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 및 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 사용하면 이러한 동작을 용도에 맞게 수정할 수 있습니다.  
  
### TextBox 컨트롤에서 삽입 지점을 제어하려면  
  
1.  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 적절한 값으로 설정합니다.  0으로 설정하면 삽입 지점이 첫 번째 문자의 바로 왼쪽에 나타납니다.  
  
2.  필요에 따라 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택할 텍스트 길이로 설정합니다.  
  
     아래 코드는 항상 삽입 지점으로 0을 반환합니다.  `TextBox1_Enter` 이벤트 처리기는 컨트롤에 바인딩되어야 합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)를 참조하십시오.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## 삽입 지점를 기본적으로 표시하기  
 <xref:System.Windows.Forms.TextBox> 컨트롤이 탭 순서에서 첫 번째 항목인 경우에만 새 폼에 <xref:System.Windows.Forms.TextBox> 삽입 지점이 기본적으로 표시되고,  그렇지 않으면 키보드나 마우스를 사용하여 <xref:System.Windows.Forms.TextBox>에 포커스를 놓아야만 삽입 지점이 표시됩니다.  
  
#### 새 폼에 텍스트 상자 삽입 지점을 기본적으로 표시하려면  
  
-   <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 `0`로 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)