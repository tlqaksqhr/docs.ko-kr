---
title: "방법: ColorDialog 구성 요소를 사용하여 색상표 표시 | Microsoft Docs"
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
  - "색 대화 상자, 색상표 표시"
  - "색상표, 대화 상자"
  - "색상표, ColorDialog 구성 요소에서 표시"
  - "Color 속성"
  - "ColorDialog 구성 요소, 색상표 표시"
  - "색, 사용자 선택 허용"
  - "색, 색상표 표시"
  - "색상표, 색 표시"
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: ColorDialog 구성 요소를 사용하여 색상표 표시
[ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) 구성 요소는 색상표를 표시하고 사용자가 선택한 색을 포함하는 속성을 반환합니다.  
  
### ColorDialog 구성 요소를 사용하여 색을 선택하려면  
  
1.  <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시합니다.  
  
2.  <xref:System.Windows.Forms.DialogResult> 속성을 사용하여 대화 상자가 닫힌 방법을 확인합니다.  
  
3.  <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성을 사용하여 선택된 색을 설정합니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용하여 <xref:System.Windows.Forms.ColorDialog> 구성 요소를 엽니다.  색이 선택된 상태에서 사용자가 **확인**을 클릭하면 <xref:System.Windows.Forms.Button> 컨트롤의 배경색이 선택된 색으로 설정됩니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤과 <xref:System.Windows.Forms.ColorDialog> 구성 요소가 있다고 가정합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog 구성 요소](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)