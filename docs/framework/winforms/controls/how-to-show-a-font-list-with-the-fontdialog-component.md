---
title: "방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시 | Microsoft Docs"
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
  - "글꼴 대화 상자, 표시"
  - "Font 속성, FontDialog 구성 요소를 사용하여 설정"
  - "FontDialog 구성 요소[Windows Forms]"
  - "글꼴, 특성"
  - "글꼴, 선택"
  - "글꼴, 목록 표시"
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: FontDialog 구성 요소를 사용하여 글꼴 목록 표시
[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) 구성 요소를 사용하면 글꼴을 선택하고 굵기와 크기 같은 글꼴 표시 요소를 변경할 수 있습니다.  
  
 대화 상자에서 선택한 글꼴은 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성에 반환됩니다.  따라서 단순히 속성을 읽기만 하면 사용자가 선택한 글꼴을 사용할 수 있습니다.  
  
### FontDialog 구성 요소를 사용하여 글꼴 속성을 선택하려면  
  
1.  <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시합니다.  
  
2.  <xref:System.Windows.Forms.DialogResult> 속성을 사용하여 대화 상자가 닫힌 방법을 확인합니다.  
  
3.  <xref:System.Windows.Forms.FontDialog.Font%2A> 속성을 사용하여 원하는 글꼴을 설정합니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용하여 <xref:System.Windows.Forms.FontDialog> 구성 요소를 엽니다.  글꼴이 선택된 상태에서 사용자가 **확인**을 클릭하면 해당 폼에 있는 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.FontDialog.Font%2A> 속성이 선택된 글꼴로 설정됩니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤, <xref:System.Windows.Forms.TextBox> 컨트롤 및 <xref:System.Windows.Forms.FontDialog> 구성 요소가 있다고 가정합니다.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog 구성 요소](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)