---
title: "방법: Windows Forms CheckBox 클릭에 응답 | Microsoft Docs"
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
  - "확인란, 이벤트에 응답"
  - "CheckBox 컨트롤[Windows Forms], Click 이벤트"
  - "Click 이벤트, CheckBox 컨트롤"
  - "두 번 클릭"
  - "이벤트[Windows Forms], Click 이벤트"
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms CheckBox 클릭에 응답
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤을 클릭할 때마다 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생합니다.  확인란의 상태에 따라 어떤 동작을 수행하는 응용 프로그램을 프로그래밍할 수 있습니다.  
  
### CheckBox 클릭에 응답하려면  
  
1.  <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 사용하여 해당 컨트롤의 상태를 결정한 다음 필요한 동작을 수행합니다.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.CheckBox> 컨트롤을 두 번 클릭하는 경우 각 클릭은 별도로 처리됩니다. 즉, <xref:System.Windows.Forms.CheckBox> 컨트롤은 두 번 클릭 이벤트를 지원하지 않습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> 속성이 `true`\(기본값\)인 경우 <xref:System.Windows.Forms.CheckBox>를 클릭하면 이 확인란이 자동으로 선택되거나 선택 취소됩니다.  그렇지 않으면 <xref:System.Windows.Forms.Control.Click> 이벤트 발생 시 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 수동으로 설정해야 합니다.  
  
     <xref:System.Windows.Forms.CheckBox> 컨트롤을 사용하여 동작 과정을 결정할 수도 있습니다.  
  
### 확인란 클릭 시 동작 과정을 결정하려면  
  
1.  case 문으로 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성 값을 쿼리하여 동작 과정을 결정합니다.  <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정되어 있는 경우 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성은 각각 확인 표시된 상자, 확인 표시가 해제된 상자, 결정되지 않은 상태의 상자를 나타내는 3가지 값을 반환할 수 있습니다. 이 중 결정되지 않는 상태의 상자는 흐릿한 모양으로 표시되어 해당 옵션을 사용할 수 없음을 나타냅니다.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정되면 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성은 <xref:System.Windows.Forms.CheckState> 및 <xref:System.Windows.Forms.CheckState> 모두에 대해 `true`를 반환합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.CheckBox>   
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [CheckBox 컨트롤](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)