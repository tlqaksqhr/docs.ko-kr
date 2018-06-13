---
title: '방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: 41bfb2bc1a1ead5bb289264c44145b88721efe49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534302"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기
암호 상자에는 사용자가 문자열을 입력 하는 동안에 자리 표시자 문자를 표시 하는 Windows Forms 텍스트 상자가입니다.  
  
### <a name="to-create-a-password-text-box"></a>암호 텍스트 상자를 만들려면  
  
1.  설정의 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 의 속성은 <xref:System.Windows.Forms.TextBox> 특정 문자를 제어 합니다.  
  
     <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성 텍스트 상자에 표시 되는 문자를 지정 합니다. 암호 상자에 별표를 표시 하려는 경우 지정 하는 예를 들어 *에 대 한는 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성 창에서 속성입니다. 그런 다음 텍스트 상자에 입력 문자가, 별표가 표시 됩니다.  
  
2.  (선택 사항) 설정의 <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> 속성입니다. 속성은 텍스트 상자에는 문자 수를 입력할 수 있습니다를 결정 합니다. 최대 길이 초과 하는 경우 시스템에서 경고음 및 텍스트 상자에 더 이상 문자를 입력할 수 없습니다. 암호의 최대 길이로이 작업을 수행 하지 않으려는 해커에 게 암호를 추측 하려고 하는 데 사용 될 수 있습니다.  
  
     다음 코드 예제에서는 최대 14 자 문자열을 허용 되 고 문자열 대신 별표를 표시 하는 텍스트 상자가 초기화 하는 방법을 보여 줍니다. `InitializeMyControl` 프로시저는 자동으로 실행 되지 않으면 호출 해야 합니다.  
  
    > [!IMPORTANT]
    >  사용 하는 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> 속성 텍스트 상자에 다른 사람이 사용자 입력을 관찰 하는 경우 사용자의 암호를 확인할 수 수 있도록 하는 데 도움이 수 있습니다. 이 보안 조치에는 모든 종류의 저장 및 전송 응용 프로그램 논리로 인해 발생할 수 있는 암호 적용 되지 않습니다. 입력 한 텍스트는 전혀 암호화 되지 않으므로, 다른 기밀 데이터와 마찬가지로 처리 해야 합니다. 따라서 표시 되지 않는 경우에 암호는 여전히 되 고로 간주 일반 텍스트 문자열 (없는 경우 추가 보안 방법을 구현한).  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
