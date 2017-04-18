---
title: "방법: 활성 MDI 자식으로 데이터 전송 | Microsoft Docs"
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
  - "클립보드, 데이터 가져오기"
  - "클립보드, 붙여넣기"
  - "MDI, 폼으로 데이터 보내기"
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 활성 MDI 자식으로 데이터 전송
[MDI 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md) 컨텍스트 내에서는 사용자가 클립보드의 데이터를 MDI 응용 프로그램에 붙여넣는 것처럼 데이터를 활성 자식 창으로 전송해야 할 경우가 종종 있습니다.  
  
> [!NOTE]
>  포커스가 있는 자식 창을 확인하고 해당 창의 내용을 클립보드로 보내는 데 대한 내용은 [활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)을 참조하십시오.  
  
### 클립보드의 데이터를 활성 MDI 자식 창으로 보내려면  
  
1.  메서드에서 클립보드에 있는 텍스트를 활성 자식 폼의 활성 컨트롤에 복사합니다.  
  
    > [!NOTE]
    >  이 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 포함된 MDI 자식 창을 하나 이상 가진 MDI 부모 폼\(`Form1`\)이 있는 경우를 가정합니다.  자세한 내용은 [MDI 부모 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)를 참조하십시오.  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
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
 [방법: 활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [방법: MDI 자식 폼 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)