---
title: "방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정 | Microsoft Docs"
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
  - ".rtf 파일, RichTextBox 컨트롤에서 형식 지정"
  - "글꼴, RichTextBox 컨트롤의 특성 변경"
  - "서식 지정[Windows Forms]"
  - "RichTextBox 컨트롤[Windows Forms], 글꼴 특성 설정"
  - "RTF 파일, RichTextBox 컨트롤에서 형식 지정"
  - "텍스트[Windows Forms]"
  - "텍스트 상자, 텍스트 서식 지정"
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 표시되는 텍스트의 서식을 지정하기 위한 옵션이 많이 있습니다.  <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성을 사용하면 선택한 문자를 굵게 또는 기울임꼴로 표시하거나 문자에 밑줄을 그을 수 있습니다.  또한 선택한 문자의 크기와 서체도 변경할 수 있습니다.  <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 사용하면 선택한 문자의 색을 변경할 수 있습니다.  
  
### 문자의 모양을 변경하려면  
  
1.  <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 속성을 적절한 글꼴로 설정합니다.  
  
     응용 프로그램에서 사용자가 글꼴 패밀리, 크기 및 서체를 설정할 수 있도록 하려면 대개 <xref:System.Windows.Forms.FontDialog> 구성 요소를 사용합니다.  전체적인 개요를 보려면 [FontDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md)를 참조하십시오.  
  
2.  <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 속성을 적절한 색으로 설정합니다.  
  
     응용 프로그램에서 사용자가 색을 설정할 수 있도록 하려면 대개 <xref:System.Windows.Forms.ColorDialog> 구성 요소를 사용합니다.  전체적인 개요를 보려면 [ColorDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)를 참조하십시오.  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  이러한 속성은 선택된 텍스트에만 적용되고 텍스트를 선택하지 않은 경우에는 현재 삽입 지점이 있는 위치에서 입력하는 텍스트에 적용됩니다.  프로그래밍 방식으로 텍스트를 선택하는 데 대한 내용은 [TextBoxBase.Select 메서드](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)