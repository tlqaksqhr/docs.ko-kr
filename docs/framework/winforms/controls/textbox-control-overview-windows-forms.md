---
title: "TextBox 컨트롤 개요(Windows Forms)"
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
f1_keywords: TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d7312246c43157ca9cd6c7b41d2b110586721c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-overview-windows-forms"></a>TextBox 컨트롤 개요(Windows Forms)
Windows Forms 텍스트 상자의 텍스트를 표시 하는 사용자 로부터 입력을 사용 됩니다. <xref:System.Windows.Forms.TextBox> 컨트롤은 일반적으로 편집 가능한 텍스트에 사용 것도 만들 수 있지만 읽기 전용입니다. 텍스트 상자는 여러 줄을 표시 하 고 텍스트는 컨트롤의 크기를 줄 바꿈할 기본 서식을 추가할 수 있습니다. <xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤에 표시 되거나 입력 텍스트에 대 한 단일 서식 스타일을 제공 합니다. 여러 종류의 서식 있는 텍스트를 표시 하려면 사용 된 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 자세한 내용은 참조 [RichTextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)합니다.  
  
## <a name="working-with-the-textbox-control"></a>TextBox 컨트롤  
 컨트롤에 의해 표시 되는 텍스트에 포함 되어는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다. 기본적으로 텍스트 상자에 2048 자까지 입력할 수 있습니다. 설정 하는 경우는 <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`, 최대 32KB의 텍스트를 입력할 수 있습니다. <xref:System.Windows.Forms.TextBox.Text%2A> 런타임 시 사용자 입력에 따라 또는 코드에서 런타임 시을 속성 창에서 디자인 타임에 속성을 설정할 수 있습니다. 입력란의 현재 내용을 참조 하 여 런타임 시 검색할 수는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.  
  
 다음 코드 예제에서는 런타임에 컨트롤에서 텍스트를 설정합니다. `InitializeMyControl` 프로시저는 자동으로 실행 되지 않으면 호출 해야 합니다.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
