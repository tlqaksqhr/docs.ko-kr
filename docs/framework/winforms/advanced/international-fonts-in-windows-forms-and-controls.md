---
title: "Windows Forms과 컨트롤에서 국가별 글꼴 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms의 글꼴 대체"
  - "글꼴, 전역화 고려 사항"
  - "글꼴, 국가별"
  - "전역화[Windows Forms], 문자 집합"
  - "국가별 응용 프로그램[Windows Forms], 문자 표시"
  - "지역화[Windows Forms], 글꼴"
  - "Windows Forms 컨트롤, 레이블"
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Windows Forms과 컨트롤에서 국가별 글꼴
국가별 응용 프로그램에서 글꼴을 선택하는 방법으로 가능하면 글꼴 대체를 사용하는 것이 좋습니다.  글꼴 대체를 사용하면 문자가 속하는 스크립트를 시스템에서 결정합니다.  
  
## 글꼴 대체 사용  
 이 기능을 활용하려면 폼이나 다른 요소에 <xref:System.Drawing.Font> 속성을 설정하지 않아야 합니다.  응용 프로그램에서는 운영 체제의 지역화된 언어에 따라 다른 기본 시스템 글꼴을 자동으로 사용합니다.  응용 프로그램을 실행할 때 시스템은 운영 체제에서 선택된 문화권에 대한 올바른 글꼴을 자동으로 제공합니다.  
  
 글꼴 스타일을 변경하기 위한 경우처럼, 글꼴을 설정하지 말라는 앞서의 규칙이 적용되지 않는 경우도 있습니다.  이는 사용자가 단추를 클릭하여 입력란의 텍스트를 굵게 표시할 수 있는 기능을 가진 응용 프로그램에서 중요할 수 있습니다.  이를 위해서는 폼의 글꼴에 기반하여 입력란의 글꼴 스타일을 굵게 변경하는 함수를 작성합니다.  단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기와 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기 모두에서 이 함수를 호출해야 합니다.  함수를 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서만 호출하면 코드의 다른 부분에서 전체 폼의 글꼴 패밀리를 변경할 때 입력란의 글꼴이 폼의 나머지 부분처럼 바뀌지 않습니다.  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 그러나, 응용 프로그램을 지역화하면 일부 언어에서 굵은 글꼴이 제대로 나타나지 않을 수도 있습니다.  이 문제를 해결하려면 지역화 담당자에게 글꼴을 바꿀 수 있는 옵션을 제공하여 굵은 텍스트를 일반 텍스트로 표시하는 것이 좋습니다.  대개 지역화 담당자는 개발자가 아니어서 소스 코드가 아닌 리소스 파일에만 액세스할 수 있으므로 이 옵션을 리소스 파일에 설정해야 합니다.  이를 위해 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`로 설정합니다.  이렇게 하면 글꼴 설정이 리소스 파일에 작성되고 지역화 담당자가 이 설정을 편집할 수 있습니다.  그런 다음 폼의 글꼴에 관계없이 리소스 파일에 지정된 글꼴 스타일을 사용하여 글꼴을 다시 설정하는 코드를 `InitializeComponent`  메서드 다음 위치에 작성합니다.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## 참고 항목  
 [Windows Forms 전역화](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)