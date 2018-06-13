---
title: '방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530148"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)
읽기 전용 컨트롤에 있는 편집 가능한 Windows Forms의 텍스트 상자를 변형할 수 있습니다. 예를 들어 텍스트 상자는 일반적으로 편집 되지만 아닐 현재 응용 프로그램의 상태로 인해 하는 값을 표시할 수 있습니다.  
  
### <a name="to-create-a-read-only-text-box"></a>읽기 전용 텍스트 상자를 만들려면  
  
1.  설정의 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을 `true`합니다. 속성 설정 하 여 `true`, 사용자가 여전히 스크롤 및 변경을 허용 하지 않고 텍스트 상자에 텍스트를 강조 표시 합니다. A **복사** 명령은 사용할 텍스트 상자에 있지만 **잘라내기** 및 **붙여넣기** 명령을 가져오지 않습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성이 런타임 시 사용자 상호 작용에만 영향을 줍니다. 변경할 수 있습니다 여전히 텍스트 상자의 내용을 프로그래밍 방식으로 런타임에 변경 하 여는 <xref:System.Windows.Forms.TextBox.Text%2A> 입력란의 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
