---
title: RichTextBox 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 53c4cd41cf203886c93291debc7bca4f395f9698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542121"
---
# <a name="richtextbox-control-overview-windows-forms"></a>RichTextBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RichTextBox> 표시, 입력, 및 서식이 지정 된 텍스트를 조작 하기 위한 컨트롤을 사용 합니다. <xref:System.Windows.Forms.RichTextBox> 모든 작업을 수행 하는 컨트롤의 <xref:System.Windows.Forms.TextBox> 컨트롤 포함 하지만 또한 글꼴, 색 및 링크 표시; 파일에서 텍스트 및 포함된 이미지를 로드 및 지정 된 문자를 찾습니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤은 일반적으로 텍스트를 조작 하 고 Microsoft Word와 같은 워드 프로세싱 응용 프로그램과 유사한 기능을 표시 하는 데 사용 됩니다. 와 같은 <xref:System.Windows.Forms.TextBox> 컨트롤은 <xref:System.Windows.Forms.RichTextBox> 컨트롤; 스크롤 막대를 표시할 수 있습니다 하지만 달리는 <xref:System.Windows.Forms.TextBox> 필요에 따라 가로 및 세로 스크롤 막대를 표시 하는 컨트롤을 기본 설정인 것 이며 추가적인 스크롤 막대 설정이 합니다.  
  
## <a name="working-with-the-richtextbox-control"></a>RichTextBox 컨트롤 작업  
 와 마찬가지로 <xref:System.Windows.Forms.TextBox> 컨트롤, 표시 되는 텍스트 설정 된 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성입니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤에 텍스트 서식을 지정 하려면 다양 한 속성이 있습니다. 이러한 속성에 대한 자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) 및 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)을 참조하세요. 파일을 조작 하는 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 및 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드를 표시 하 고 일반 텍스트, 유니코드 일반 텍스트 및 서식 있는 텍스트 형식 (RTF)를 비롯 한 여러 가지 파일 형식을 쓸 수 있습니다. 가능한 파일 형식은 같거나 <xref:System.Windows.Forms.RichTextBoxStreamType>합니다. 사용할 수는 <xref:System.Windows.Forms.RichTextBox.Find%2A> 메서드 특정 문자 또는 텍스트 문자열을 찾으려고 합니다.  
  
 사용할 수도 있습니다는 <xref:System.Windows.Forms.RichTextBox> 설정 하 여 웹 스타일 링크에 대 한 제어는 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성을 `true` 처리 코드를 작성 하 고는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트입니다. 자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)를 참조하세요. 컨트롤에서 텍스트의 일부 또는 전부를 설정 하 여 조작에서 사용자를 방지할 수 있습니다는 <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> 속성을 `true`합니다.  
  
 실행 취소 하 고에서 대부분의 편집 작업을 다시 실행 한 <xref:System.Windows.Forms.RichTextBox> 호출 하 여 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.Undo%2A> 및 <xref:System.Windows.Forms.RichTextBox.Redo%2A> 메서드. <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> 메서드를 사용 하면 컨트롤에는 사용자가 실행 취소 마지막 작업을 다시 적용할 수 있는지 여부를 확인할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
