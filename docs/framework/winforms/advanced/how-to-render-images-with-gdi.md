---
title: "방법: GDI+를 사용하여 이미지 렌더링 | Microsoft Docs"
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
  - "GDI+, 기존 이미지 렌더링"
  - "이미지[Windows Forms], 만들기"
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: GDI+를 사용하여 이미지 렌더링
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 응용 프로그램에서 이미지 파일을 렌더링할 수 있습니다.  이를 수행하려면 <xref:System.Drawing.Image> 클래스의 새 개체\(예: <xref:System.Drawing.Bitmap>\) 및 사용할 그리기 화면을 참조하는 <xref:System.Drawing.Graphics> 개체를 만든 다음 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 호출합니다.  그러면 Graphics 클래스에서 표시하는 그리기 화면에 이미지가 그려집니다.  디자인 타임에 이미지 편집기를 사용하여 이미지 파일을 만들고 편집한 다음 런타임에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 이를 렌더링할 수 있습니다.  자세한 내용은 [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md)를 참조하십시오.  
  
### GDI\+를 사용하여 이미지를 렌더링하려면  
  
1.  표시할 이미지를 나타내는 개체를 만듭니다.  이 개체는 <xref:System.Drawing.Bitmap> 또는 <xref:System.Drawing.Imaging.Metafile>과 같이 <xref:System.Drawing.Image>에서 상속되는 클래스의 멤버여야 합니다.  다음 예제를 참조하십시오.  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the   
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2.  사용할 그리기 화면을 나타내는 <xref:System.Drawing.Graphics> 개체를 만듭니다.  자세한 내용은 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하십시오.  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of   
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3.  Graphics 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 호출하여 이미지를 렌더링합니다.  그릴 이미지뿐 아니라 이미지를 그릴 위치에 대한 좌표도 지정해야 합니다.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## 참고 항목  
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [GDI\+의 펜, 선 및 사각형](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)   
 [방법: Windows Form에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Drawing Lines or Closed Figures](../Topic/Drawing%20Lines%20or%20Closed%20Figures%20\(Image%20Editor%20for%20Icons\).md)   
 [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md)