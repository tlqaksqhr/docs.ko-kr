---
title: "방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사 | Microsoft Docs"
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
  - "bitblt(bit-block transfer)"
  - "bitblt"
  - "깜빡임"
  - "깜빡임, Windows Forms에서 줄이기"
  - "그래픽, 복사"
  - "그래픽, 깜빡임 줄이기"
  - "픽셀, 복사"
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사
간단한 그래픽에 애니메이션 효과를 줄 때 깜빡임 현상이나 그 외의 예상치 못한 시각적 효과가 발생할 수 있는데,  그래픽에 "bitblt" 프로세스를 사용하면 이 문제를 줄일 수 있습니다.  bitblt는 소스 픽셀 사각형에서 대상 픽셀 사각형으로 색 데이터를 "bit\-block transfer"하는 과정입니다.  
  
 Windows Forms에서는 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용하여 bitblt가 수행됩니다.  메서드의 매개 변수에 소스와 대상\(점\), 복사할 영역의 크기 및 새 도형을 그리는 데 사용되는 그래픽 개체를 지정합니다.  
  
 아래 예제에서는 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에 도형이 그려집니다.  그런 다음 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용하여 도형이 복제됩니다.  
  
> [!NOTE]
>  폼의 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`로 설정하면 이중 버퍼링될 <xref:System.Windows.Forms.Control.Paint> 이벤트에 그래픽 기반 코드가 만들어집니다.  아래 코드를 사용할 때는 이렇게 설정해도 뚜렷한 성능 차이를 느낄 수 없지만 복잡한 그래픽 조작 코드로 작업할 때는 이렇게 설정하는 것이 중요합니다.  
  
## 예제  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## 코드 컴파일  
 폼이 다시 그려질 때 그래픽이 유지되도록 위 코드가 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에서 실행됩니다.  폼의 크기가 조정되거나 다른 폼에 의해 가려질 경우에는 그려진 내용이 다시 그려지지 않으므로, <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 그래픽 관련 메서드를 호출하지 않습니다.  
  
## 참고 항목  
 <xref:System.Drawing.CopyPixelOperation>   
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=fullName>   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)