---
title: "연습: MaskedTextBox 컨트롤 사용 | Microsoft Docs"
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
  - "입력, 유효성을 보장하도록 제어"
  - "MaskedTextBox 컨트롤[Windows Forms], 유효성 검사"
  - "MaskedTextBox 컨트롤[Windows Forms], 연습"
  - "텍스트, 입력할 컨트롤"
  - "사용자 입력, 제어"
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 연습: MaskedTextBox 컨트롤 사용
이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.MaskedTextBox> 컨트롤 초기화  
  
-   문자가 마스크에 맞지 않을 경우 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 이벤트 처리기를 사용하여 사용자에게 경고 보내기  
  
-   <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성에 형식을 할당한 다음 커밋하려는 값이 형식에 유효하지 않은 경우 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 이벤트 처리기를 사용하여 사용자에게 경고 보내기  
  
## 프로젝트 만들기 및 컨트롤 추가  
  
#### MaskedTextBox 컨트롤을 폼에 추가하려면  
  
1.  <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 배치할 폼을 엽니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 폼으로 끌어 옵니다.  
  
3.  컨트롤을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  **속성** 창에서 **마스크** 속성을 선택한 다음 속성 이름 옆의 **...**\(줄임표\) 단추를  클릭합니다.  
  
4.  **입력 마스크** 대화 상자에서 **간단한 날짜** 마스크를 선택하고 **확인**을 클릭합니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> 속성을 `true`로 설정합니다.  이 속성은 사용자가 마스크 정의에 위반되는 문자를 입력할 때마다 짧은 경고음을 울립니다.  
  
 Mask 속성이 지원하는 문자에 대한 요약은 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성의 설명 부분을 참조하십시오.  
  
## 사용자에게 입력 오류 알림  
  
#### 거부된 마스크 입력에 대한 풍선 팁 추가  
  
1.  **도구 상자**로 돌아와서 <xref:System.Windows.Forms.ToolTip>을 폼에 추가합니다.  
  
2.  입력 오류가 발생할 때 <xref:System.Windows.Forms.ToolTip>을 발생시키는 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 이벤트 처리기를 만듭니다.  풍선 팁은 5초 동안 또는 사용자가 풍선 팁을 클릭할 때까지 표시됩니다.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
  
    ```  
  
## 사용자에게 유효하지 않은 형식 알림  
  
#### 잘못된 데이터 형식에 대한 풍선 팁 추가  
  
1.  폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.DateTime> 형식을 나타내는 <xref:System.Type> 개체를 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성에 할당합니다.  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.MaskedTextBox>   
 [MaskedTextBox 컨트롤](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)