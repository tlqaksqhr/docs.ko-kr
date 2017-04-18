---
title: "방법: 그리는 데 필요한 그래픽 개체 만들기 | Microsoft Docs"
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
  - "GDI+, 이미지 만들기"
  - "그래픽[Windows Forms], 만들기"
  - "Graphics 클래스"
  - "이미지[Windows Forms], 만들기"
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 그리는 데 필요한 그래픽 개체 만들기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 선과 도형을 그리고 텍스트를 렌더링하거나 이미지를 조작하려면 먼저 <xref:System.Drawing.Graphics> 개체를 만들어야 합니다.  <xref:System.Drawing.Graphics> 개체는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 그리기 화면을 나타내며 그래픽 이미지를 만드는 데 사용됩니다.  
  
 그래픽에 대한 작업은 다음과 같은 두 단계로 이루어집니다.  
  
1.  <xref:System.Drawing.Graphics> 개체를 만듭니다.  
  
2.  <xref:System.Drawing.Graphics> 개체를 사용하여 선과 도형을 그리고 텍스트를 렌더링하거나 이미지를 표시 및 조작합니다.  
  
## Graphics 개체 만들기  
 여러 가지 방법을 사용하여 Graphics 개체를 만들 수 있습니다.  
  
#### Graphics 개체를 만들려면  
  
-   폼 또는 컨트롤의 <xref:System.Windows.Forms.Control.Paint> 이벤트에서 <xref:System.Windows.Forms.PaintEventArgs>의 일부로 Graphics 개체에 대한 참조를 받습니다.  이 방법은 대개 컨트롤을 그리는 코드를 작성할 때 Graphics 개체에 대한 참조를 가져오는 데 사용됩니다.  마찬가지로 <xref:System.Drawing.Printing.PrintDocument>에 대한 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리할 때 <xref:System.Drawing.Printing.PrintPageEventArgs>의 속성으로 그래픽 개체를 가져올 수도 있습니다.  
  
     또는  
  
-   폼 또는 컨트롤의 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 메서드를 호출하여 해당 폼이나 컨트롤의 그리기 화면을 나타내는 <xref:System.Drawing.Graphics> 개체에 대한 참조를 가져옵니다.  이미 있는 폼이나 컨트롤에서 그리려는 경우 이 방법을 사용합니다.  
  
     또는  
  
-   <xref:System.Drawing.Image>에서 상속된 개체에서 <xref:System.Drawing.Graphics> 개체를 만듭니다.  이 방법은 기존 이미지를 변경하려는 경우에 유용합니다.  
  
     다음 단원에서는 위에서 제시한 세 가지 방법에 대해 각각 자세하게 설명합니다.  
  
## Paint 이벤트 처리기의 PaintEventArgs  
 컨트롤에 대한 <xref:System.Windows.Forms.PaintEventHandler>나 <xref:System.Drawing.Printing.PrintDocument>에 대한 <xref:System.Drawing.Printing.PrintDocument.PrintPage>를 프로그래밍하는 경우 Graphics 개체가 <xref:System.Windows.Forms.PaintEventArgs>나 <xref:System.Drawing.Printing.PrintPageEventArgs>의 속성 중 하나로 제공됩니다.  
  
#### Paint 이벤트의 PaintEventArgs에서 Graphics 개체에 대한 참조를 가져오려면  
  
1.  <xref:System.Drawing.Graphics> 개체를 선언합니다.  
  
2.  <xref:System.Windows.Forms.PaintEventArgs>의 일부로 전달되는 <xref:System.Drawing.Graphics> 개체를 참조할 변수를 할당합니다.  
  
3.  폼 또는 컨트롤을 그리는 코드를 삽입합니다.  
  
     다음 예제에서는 <xref:System.Windows.Forms.Control.Paint> 이벤트의 <xref:System.Windows.Forms.PaintEventArgs>에서 <xref:System.Drawing.Graphics> 개체를 참조하는 방법을 보여 줍니다.  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## CreateGraphics 메서드  
 폼 또는 컨트롤의 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 메서드를 사용하여 해당 폼이나 컨트롤의 그리기 화면을 나타내는 <xref:System.Drawing.Graphics> 개체에 대한 참조를 가져올 수도 있습니다.  
  
#### CreateGraphics 메서드를 사용하여 Graphics 개체를 만들려면  
  
-   그래픽을 렌더링할 폼 또는 컨트롤의 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 메서드를 호출합니다.  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## Image 개체에서 만들기  
 <xref:System.Drawing.Image> 클래스에서 파생되는 개체를 사용하여 Graphics 개체를 만들 수도 있습니다.  
  
#### Image 개체에서 Graphics 개체를 만들려면  
  
-   <xref:System.Drawing.Graphics> 개체를 만드는 데 사용할 Image 변수의 이름을 지정하여 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
     다음 예제에서는 <xref:System.Drawing.Bitmap> 개체를 사용하는 방법을 보여 줍니다.  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  16비트, 24비트 및 32비트 .bmp 파일 같은 인덱싱되지 않은 .bmp 파일에서만 <xref:System.Drawing.Graphics> 개체를 만들 수 있습니다.  인덱싱된 .bmp 파일의 픽셀에 색상표에 대한 인덱스가 저장되는 것과 달리 인덱싱되지 않은 .bmp 파일의 각 픽셀에는 색이 저장됩니다.  
  
## 모양과 이미지 그리기 및 조작  
 <xref:System.Drawing.Graphics> 개체를 만든 다음에는 이 개체를 사용하여 선과 도형을 그리고 텍스트를 렌더링하거나 이미지를 표시 및 조작할 수 있습니다.  다음은 <xref:System.Drawing.Graphics> 개체와 함께 사용되는 기본 개체입니다.  
  
-   <xref:System.Drawing.Pen> 클래스—선과 도형의 윤곽을 그리거나 기타 기하학적 표현을 렌더링하는 데 사용합니다.  
  
-   <xref:System.Drawing.Brush> 클래스—채워진 도형, 이미지 또는 텍스트와 같이 그래픽의 영역을 채우는 데 사용합니다.  
  
-   <xref:System.Drawing.Font> 클래스—텍스트를 렌더링할 때 사용할 도형에 대한 설명을 제공합니다.  
  
-   <xref:System.Drawing.Color> 구조체—표시할 여러 가지 색을 나타냅니다.  
  
#### 새로 만든 Graphics 개체를 사용하려면  
  
-   위의 목록에서 적절한 개체를 사용하여 필요한 항목을 그립니다.  
  
     자세한 내용은 다음 항목을 참조하십시오.  
  
    |렌더링 대상|참조|  
    |------------|--------|  
    |줄|[방법: Windows Form에 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Shape|[방법: 윤곽선이 있는 도형 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[방법: Windows Form에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |이미지|[방법: GDI\+를 사용하여 이미지 렌더링](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## 참고 항목  
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: GDI\+를 사용하여 이미지 렌더링](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)