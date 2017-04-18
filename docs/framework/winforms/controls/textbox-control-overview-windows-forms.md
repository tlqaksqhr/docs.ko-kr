---
title: "TextBox 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "텍스트 상자, 추가"
  - "TextBox 컨트롤[Windows Forms], TextBox 컨트롤 정보"
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# TextBox 컨트롤 개요(Windows Forms)
Windows Forms 텍스트 상자는 사용자의 입력을 받거나 텍스트를 표시하는 데 사용됩니다.  일반적으로 <xref:System.Windows.Forms.TextBox> 컨트롤은 편집할 수 있는 텍스트에 사용되지만 읽기 전용으로 만들 수도 있습니다.  텍스트 상자는 여러 줄의 텍스트를 표시하고 컨트롤의 크기에 맞게 텍스트를 줄 바꿈할 수 있으며 기본 서식을 추가할 수 있습니다.  <xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤에 표시되거나 입력되는 텍스트에 단일 서식 스타일을 제공합니다.  여러 종류의 서식 있는 텍스트를 표시하려면 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용합니다.  자세한 내용은 [RichTextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)를 참조하십시오.  
  
## TextBox 컨트롤 사용  
 컨트롤에 표시되는 텍스트는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성에 지정되어 있습니다.  텍스트 상자에는 기본적으로 2048자까지 입력할 수 있지만  <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`로 설정하면 텍스트를 최대 32KB까지 입력할 수 있습니다.  <xref:System.Windows.Forms.TextBox.Text%2A> 속성은 디자인 타임에 속성 창을 사용하여 설정하거나, 런타임에 코드에서 설정하거나, 런타임에 사용자 입력을 통해 설정할 수 있습니다.  텍스트 상자의 현재 내용은 런타임에서 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 읽어 검색할 수 있습니다.  
  
 다음 코드 예제에서는 런타임에 컨트롤의 텍스트를 설정합니다.  `InitializeMyControl`  프로시저는 자동으로 실행되지 않으므로 직접 호출해야 합니다.  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)