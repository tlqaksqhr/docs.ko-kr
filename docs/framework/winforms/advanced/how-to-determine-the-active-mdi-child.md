---
title: "방법: 활성 MDI 자식 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c026df631c2ac033594ea86887bb8440a6aa240a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-active-mdi-child"></a>방법: 활성 MDI 자식 확인
경우에 따라 현재 활성 자식 폼에 포커스가 있는 컨트롤에 작동 하는 명령을 제공 합니다. 예를 들어 자식 폼의 텍스트 상자에서 선택한 텍스트를 클립보드에 복사할 한다고 가정 합니다. 선택한 텍스트를 사용 하 여 클립보드에 복사 하는 프로시저를 만들면 됩니다는 <xref:System.Windows.Forms.Control.Click> 표준 편집 메뉴에서 메뉴 항목 복사본의 이벤트입니다.  
  
 MDI 응용 프로그램이 동일한 자식 폼의 여러 인스턴스들이 있을 수 있지만, 때문에 프로시저 사용할 폼을 알아야 합니다. 사용 하 여 올바른 폼을 지정 하려면는 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 포커스가 있는 또는 가장 최근에 활성화 된 자식 폼을 반환 하는 속성입니다.  
  
 폼에 여러 컨트롤을 사용 하는 경우 활성 컨트롤을 지정 해야 하는 또한 합니다. 마찬가지로 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 속성에는 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성 활성 자식 폼의 포커스가 있는 컨트롤을 반환 합니다. 다음 절차를 자식 폼 메뉴의 메뉴 도구 모음 단추 또는 MDI 폼에서 호출할 수 있는 복사본 프로시저를 보여 줍니다.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>(해당 텍스트를 클립보드에 복사)를 활성 MDI 자식 확인 하려면  
  
1.  메서드 내에서 활성 자식 폼의 활성 컨트롤의 텍스트를 클립보드에 복사 합니다.  
  
    > [!NOTE]
    >  이 예제에서는 MDI 부모 폼이 가정 (`Form1`)가 하나 이상의 MDI 자식 창을 포함 하는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 자세한 내용은 참조 [MDI 부모 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [MDI(다중 문서 인터페이스) 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [방법: MDI 자식 양식 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
