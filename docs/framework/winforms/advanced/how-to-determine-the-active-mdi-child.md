---
title: "방법: 활성 MDI 자식 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "자식 폼"
  - "클립보드, 데이터 복사"
  - "MDI, 폼 활성화"
  - "MDI, 자식 창"
  - "MDI, 포커스 찾기"
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 활성 MDI 자식 확인
경우에 따라 현재 활성화된 자식 폼에 포커스가 있는 컨트롤에서 동작하는 명령을 제공할 수 있습니다.  예를 들어 자식 폼의 텍스트 상자에서 선택한 텍스트를 클립보드에 복사하려면  표준 편집 메뉴에 있는 복사 메뉴 항목의 <xref:System.Windows.Forms.Control.Click> 이벤트를 사용하여 선택된 텍스트를 클립보드에 복사하는 프로시저를 만듭니다.  
  
 MDI 응용 프로그램에는 동일한 자식 폼의 인스턴스가 여러 개 있을 수 있으므로 사용할 폼을 프로시저에 지정해야 합니다.  올바른 폼을 지정하려면 포커스가 있는 자식 폼 또는 가장 최근에 활성화된 자식 폼을 반환하는 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 속성을 사용합니다.  
  
 하나의 폼에 컨트롤이 여러 개 있는 경우에도 활성 컨트롤을 지정해야 합니다.  <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 속성과 마찬가지로 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성도 활성 자식 폼에서 포커스가 있는 컨트롤을 반환합니다.  다음 프로시저는 자식 폼 메뉴, MDI 폼의 메뉴 또는 도구 모음 단추를 통해 호출할 수 있는 복사 프로시저를 보여 줍니다.  
  
### 활성 MDI 자식을 확인하여 해당 텍스트를 클립보드에 복사하려면  
  
1.  메서드에서 활성 자식 폼에 있는 활성 컨트롤의 텍스트를 클립보드에 복사합니다.  
  
    > [!NOTE]
    >  이 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 포함된 MDI 자식 창을 하나 이상 가진 MDI 부모 폼\(`Form1`\)이 있는 경우를 가정합니다.  자세한 내용은 [MDI 부모 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)를 참조하십시오.  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
  
    ```  
  
## 참고 항목  
 [MDI 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [방법: MDI 자식 폼 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)