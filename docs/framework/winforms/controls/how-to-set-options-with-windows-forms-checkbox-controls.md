---
title: "방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정 | Microsoft Docs"
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
  - "checked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "확인란, 옵션 설정에 사용"
  - "CheckBox 컨트롤[Windows Forms], 선택 상태"
  - "CheckBox 컨트롤[Windows Forms], 옵션 설정에 사용"
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 사용자에게 True\/False 또는 Yes\/No 옵션을 제공하기 위해 사용합니다.  옵션을 선택하면 확인란에 확인 표시가 나타납니다.  
  
### CheckBox 컨트롤을 사용하여 옵션을 설정하려면  
  
1.  <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성 값을 검사하여 해당 속성의 상태를 확인한 다음 이 속성 값을 사용하여 옵션을 설정합니다.  
  
     다음 코드 샘플에서는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트가 발생할 때 확인란이 선택된 경우 폼의 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성이 `false`로 설정됩니다.  이 방법은 사용자의 상호 작용을 제한하려는 경우에 유용합니다.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.CheckBox>   
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [방법: Windows Forms CheckBox 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox 컨트롤](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)