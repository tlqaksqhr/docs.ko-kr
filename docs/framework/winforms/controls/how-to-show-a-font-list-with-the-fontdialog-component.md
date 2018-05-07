---
title: '방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: fe291df1648da5002ce3173a68208bbad659705d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시
[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) 구성 요소에 글꼴을 선택 하 고 가중치와 크기 같은 표시 요소를 변경할 사용자를 허용 합니다.  
  
 대화 상자에서 선택한 글꼴에 반환 되는 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성입니다. 따라서 사용자가 선택한 글꼴을 활용 하기 위해 속성 읽기를 하기만 됩니다.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>FontDialog 구성 요소를 사용 하 여 글꼴 속성을 선택 하려면  
  
1.  사용 하 여 대화 상자 표시는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.  
  
2.  사용 하 여는 <xref:System.Windows.Forms.DialogResult> 대화 상자를 닫은 방법을 결정 하는 속성입니다.  
  
3.  사용 하 여는 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성을 원하는 글꼴을 설정 합니다.  
  
     다음 예제에는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 열립니다는 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다. 경우 글꼴 선택 하 고 사용자가 **확인**, <xref:System.Windows.Forms.FontDialog.Font%2A> 속성은 <xref:System.Windows.Forms.TextBox> 폼에 컨트롤에 선택 된 글꼴로 설정 됩니다. 이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤 및 <xref:System.Windows.Forms.FontDialog> 구성 요소입니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FontDialog>  
 [FontDialog 구성 요소](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
