---
title: Windows Forms 및 컨트롤에서 국가별 글꼴
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208602"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows Forms 및 컨트롤에서 국가별 글꼴

국가별 응용 프로그램에서 글꼴을 선택 하는 권장된 방법은 가능 글꼴 대체 (fallback)를 사용 하는 합니다. 글꼴 대체 방법 결정 된다는 문자 스크립트에 속해 있습니다.

## <a name="using-font-fallback"></a>글꼴 대체 (fallback)를 사용 하 여

이 기능을 이용 하려면 설정 하지 않습니다는 <xref:System.Drawing.Font> 속성 폼 이나 다른 요소에 대 한 합니다. 응용 프로그램에는 다른 운영 체제의 한 지역화 된 언어에서 다른 기본 시스템 글꼴을 자동으로 사용 됩니다. 응용 프로그램이 실행 되 면 시스템 운영 체제에서 선택 된 문화권에 대 한 올바른 글꼴을 자동으로 제공 합니다.

글꼴, 글꼴 스타일을 변경 하기 위한 경우를 설정 하지 않는 규칙에 예외가 있습니다. 이는 사용자는 굵은 글꼴 텍스트 상자에 텍스트를 표시 하려면 단추를 클릭 하는 응용 프로그램에 대 한 중요할 수 있습니다. 이렇게 하려면 폼의 글꼴을 굵게, 입력란의 글꼴 스타일을 변경 하는 함수를 작성할 것 있습니다. 두 위치에서이 함수를 호출 해야: 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기입니다. 경우에 함수가 호출 되는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및 코드의 다른 부분에는 전체 폼의 글꼴 패밀리 변경 내용, 텍스트 상자 폼의 나머지 부분과 변경 되지 않습니다.

```vb
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
```

```csharp
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

그러나 응용 프로그램을 지역화할 굵은 글꼴 표시 될 수 있다는 불완전 하 게 특정 언어입니다. 중요 하지 않은 경우 원하는 굵은 글꼴을 일반 텍스트로 전환의 수를 지역화 합니다. 지역화 되지 개발자는 일반적으로 소스 코드에 액세스할 수 없는 이므로 리소스 파일에만이 옵션 설정 해야 리소스 파일에 있습니다. 이 위해 설정한는 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`합니다. 따라서 지역화 담당자 편집할 수 있는 리소스 파일에 작성 되 고 글꼴 설정 됩니다. 다음 뒤에 코드를 작성은 `InitializeComponent` 글꼴 다시 설정 하는 메서드를 폼의 글꼴을 기반으로 하지만 리소스 파일에 지정 된 글꼴 스타일을 사용 하 여 합니다.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>참고자료

[Windows Forms 응용 프로그램 전역화](globalizing-windows-forms.md)  
[글꼴 및 텍스트 사용](using-fonts-and-text.md)