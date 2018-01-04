---
title: "방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어"
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
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8de64ac28fe57e3c448c671859053fad4aae3b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어
때 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤이 포커스를 먼저 받기, 텍스트 상자 내에서 기본 삽입이 기존 텍스트의 왼쪽에 있습니다. 키보드 또는 마우스 커서를 이동할 수 있습니다. 텍스트 상자에서 손실 되 고 포커스 다시 얻은 후, 삽입 지점을 아무 곳에 나 사용자 마지막 배치 됩니다.  
  
 경우에 따라이 동작을 사용자에 게 혼란을 줄 수 있습니다. 사용자 단어에 처리 응용 프로그램을 새 문자를 모든 기존 텍스트를 표시 하려면를 예상할 수 있습니다. 데이터 입력 응용 프로그램에서 사용자는 기존 엔트리를 대체할 새 문자를 예상할 수 있습니다. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 및 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 사용 하는 목적에 맞게 동작을 수정할 수 있습니다.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>TextBox 컨트롤에 삽입 포인터를 제어 하려면  
  
1.  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 적절한 값으로 설정합니다. 0에는 첫 번째 문자의 왼쪽에 바로 삽입 지점을 넣습니다.  
  
2.  (선택 사항) 설정의 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이입니다.  
  
     아래 코드는 항상 0으로 삽입 포인터를 반환합니다. `TextBox1_Enter` 이벤트 처리기 참조 하십시오; 자세한 내용은 컨트롤에 바인딩할 수 해야 [Windows Forms에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)합니다.  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>삽입 지점이 기본적으로 표시 되도록 설정  
 <xref:System.Windows.Forms.TextBox> 삽입 포인터를 새 폼 경우에만에 기본적으로 표시 됩니다는 <xref:System.Windows.Forms.TextBox> 컨트롤은 탭 순서에서 첫 번째입니다. 그렇지 않은 경우 삽입 지점을 제공 하는 경우에 표시 됩니다는 <xref:System.Windows.Forms.TextBox> 키보드 또는 마우스 포커스 합니다.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>새 폼에는 기본적으로 텍스트 상자 삽입 지점을 표시 하려면  
  
-   설정의 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 `0`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
