---
title: "방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8658b51515d8d3934613b40a8d4bec0ab9bf618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기
이 예제에서는 텍스트에 대 한 사용자 지정 그리기를 <xref:System.Windows.Forms.ComboBox> 제어 합니다. 항목이 특정 조건에 부합 하는 경우 더 큰 글꼴로 그려집니다 이며 빨간색으로 설정 합니다.  
  
## <a name="example"></a>예  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows form입니다.  
  
-   A <xref:System.Windows.Forms.ComboBox> 라는 컨트롤 `ListBox1` 의 세 가지 항목으로는 <xref:System.Windows.Forms.ComboBox.Items%2A> 속성입니다. 이 예제에서 세 가지 항목 이름은 `"One", Two", and Three"`합니다. <xref:System.Windows.Forms.ComboBox.DrawMode%2A> 속성 `ComboBox1` 로 설정 해야 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>합니다.  
  
    > [!NOTE]
    >  이 기술은에 적용 됩니다는 <xref:System.Windows.Forms.ListBox> 컨트롤-대신 사용할 수 있습니다는 <xref:System.Windows.Forms.ListBox> 에 대 한는 <xref:System.Windows.Forms.ComboBox>합니다.  
  
-   <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ComboBox.DrawItem>  
 <xref:System.Windows.Forms.DrawItemEventArgs>  
 <xref:System.Windows.Forms.ComboBox.MeasureItem>  
 [소유자 그리기 지원이 기본 제공되는 컨트롤](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)  
 [ListBox 컨트롤](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)  
 [ComboBox 컨트롤](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
