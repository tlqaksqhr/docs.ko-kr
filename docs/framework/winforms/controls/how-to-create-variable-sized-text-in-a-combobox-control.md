---
title: "방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기 | Microsoft Docs"
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
  - "콤보 상자, 텍스트 그리기"
  - "ComboBox 컨트롤[Windows Forms], 사용자 지정 텍스트 그리기"
  - "ComboBox 컨트롤[Windows Forms], 예제[C#]"
  - "예제[Windows Forms], ComboBox 컨트롤"
  - "텍스트, 콤보 상자에 그리기"
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기
이 예제에서는 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 사용자 지정으로 텍스트를 그리는 것을 보여 줍니다.  항목이 특정 조건을 만족하면 이 항목은 더 큰 글꼴로 그려지고 빨강으로 바뀝니다.  
  
## 예제  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows 폼  
  
-   <xref:System.Windows.Forms.ComboBox.Items%2A> 속성에 세 항목을 포함하는 `ListBox1`이라는 <xref:System.Windows.Forms.ComboBox> 컨트롤.  이 예제에서 세 항목의 이름은 `"One", Two", and Three"`입니다.   `ComboBox1`의 <xref:System.Windows.Forms.ComboBox.DrawMode%2A> 속성은 <xref:System.Windows.Forms.DrawMode>로 설정해야 합니다.  
  
    > [!NOTE]
    >  이 기술은 <xref:System.Windows.Forms.ListBox> 컨트롤에도 적용할 수도 있습니다. 즉, <xref:System.Windows.Forms.ListBox>를 <xref:System.Windows.Forms.ComboBox> 대신 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Drawing?displayProperty=fullName> 네임스페이스에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox.DrawItem>   
 <xref:System.Windows.Forms.DrawItemEventArgs>   
 <xref:System.Windows.Forms.ComboBox.MeasureItem>   
 [소유자가 그린 기본 제공 컨트롤 지원](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [ListBox 컨트롤](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)   
 [ComboBox 컨트롤](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)