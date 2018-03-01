---
title: "방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4059e3b4ad4c687234f2bc0c66c680b2c857cfe7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤이 True/False 사용자에 게 부여 하는 데 사용 되 나 예/아니요 옵션입니다. 컨트롤 선택 된 경우 확인 표시가 나타납니다.  
  
### <a name="to-set-options-with-checkbox-controls"></a>확인란 컨트롤을 사용할 옵션을 설정 하려면  
  
1.  값을 검사는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성의 상태를 확인 하는 옵션을 설정 하려면 해당 값을 사용 합니다.  
  
     경우 아래의 코드 예제에는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트는 폼의 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성이로 설정 되어 `false` 는 확인란을 선택 하는 경우. 이 사용자 상호 작용을 제한 하려는 경우에 유용 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.CheckBox>  
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [방법: Windows Forms CheckBox 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox 컨트롤](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
