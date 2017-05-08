---
title: "방법: 탭 페이지 사용 안 함 | Microsoft Docs"
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
  - "탭 페이지, 폼에서 숨기기"
  - "TabControl 컨트롤[Windows Forms], 페이지 비활성화"
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 탭 페이지 사용 안 함
경우에 따라 Windows Forms 응용 프로그램에서 사용할 수 있는 데이터에 대한 액세스를 제한해야 할 수 있습니다.  예를 들어 데이터가 탭 컨트롤의 탭 페이지에 표시된 경우가 여기에 해당합니다. 즉, 관리자가 탭 페이지에 표시한 정보를 게스트 또는 하위 수준 사용자가 액세스할 수 없도록 제한할 수 있습니다.  
  
### 프로그래밍 방식으로 탭 페이지를 비활성화하려면  
  
1.  탭 컨트롤의 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트를 처리하는 코드를 작성합니다.  이 이벤트는 사용자가 한 탭에서 다음 탭으로 전환할 때 발생합니다.  
  
2.  자격 증명을 확인합니다.  제공된 정보에 따라 로그인한 사용자의 이름 또는 다른 형식의 자격 증명을 확인한 다음 사용자에게 탭을 볼 수 있는 권한을 허용합니다.  
  
3.  사용자가 올바른 자격 증명을 갖고 있는 경우 클릭된 탭을 표시하고  사용자의 자격 증명이 올바르지 않으면 액세스 권한이 없다는 메시지 상자 또는 다른 사용자 인터페이스를 표시한 다음 초기 탭으로 돌아갑니다.  
  
    > [!NOTE]
    >  프로덕션 응용 프로그램에서 이 기능을 구현할 경우에는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트를 실행하는 동안 자격 증명을 확인할 수 있습니다.  이렇게 하면 사용자 인터페이스가 표시되기 전에 탭을 숨길 수 있습니다. 이 방식이 프로그래밍하기에 훨씬 명확합니다.  아래 예제에서는 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트를 실행하는 동안 자격 증명을 확인하고 탭을 비활성화하는 방법을 사용했는데 이는 설명을 하기 위한 목적이며 유용한 방법은 아닙니다.  
  
4.  \(옵션\) 탭 페이지가 세 개 이상 있는 경우에는 원래 탭 페이지와 다른 탭 페이지를 표시합니다.  
  
     응용 프로그램에 따라 탭에 액세스하기 위한 조건이 다르므로 아래 예제에서는 자격 증명을 확인하는 대신 <xref:System.Windows.Forms.CheckBox> 컨트롤이 사용됩니다.  <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트가 발생하는 경우 자격 증명 확인이 true\(확인란이 선택된 상태\)이고 선택한 탭이 `TabPage2`\(이 예제에서는 기밀 정보가 포함된 탭\)이면 `TabPage2`가 표시됩니다.  그렇지 않으면 `TabPage3`가 표시되고 액세스 권한이 없음을 나타내는 메시지 상자가 표시됩니다.  아래 코드에서는 폼에 세 개의 탭 페이지가 포함된 <xref:System.Windows.Forms.TabControl> 컨트롤과 <xref:System.Windows.Forms.CheckBox> 컨트롤\(`CredentialCheck`\)이 있다고 가정합니다.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     \(Visual C\#, Visual C\+\+\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## 참고 항목  
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [방법: 탭 페이지에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)   
 [방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)