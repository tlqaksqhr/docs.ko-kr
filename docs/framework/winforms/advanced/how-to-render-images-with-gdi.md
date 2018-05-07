---
title: '방법: GDI+를 사용하여 이미지 렌더링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: 6f5b139c6831a065c85e9d9889c259c859a649cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-render-images-with-gdi"></a>방법: GDI+를 사용하여 이미지 렌더링
응용 프로그램에서 파일로 존재하는 이미지를 렌더링하는 데 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]을 사용할 수 있습니다. 새 개체를 만들어이 작업을 수행는 <xref:System.Drawing.Image> 클래스 (같은 <xref:System.Drawing.Bitmap>) 만들기는 <xref:System.Drawing.Graphics> 참조 하는 그리기 화면을 사용 하려면 개체를 호출 하는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드는 <xref:System.Drawing.Graphics> 개체입니다. 이미지는 그래픽 클래스에서 표시하는 그리기 화면에 그려집니다. 이미지 편집기를 사용하여 디자인 타임에 이미지 파일을 만들고 편집하고 런타임 시 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]을 사용하여 렌더링합니다. 자세한 내용은 [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)를 참조하세요.  
  
### <a name="to-render-an-image-with-gdi"></a>GDI+를 사용하여 이미지를 렌더링하려면  
  
1.  표시하려는 이미지를 나타내는 개체를 만듭니다. 이 개체에서 상속 되는 클래스의 멤버 여야 합니다. <xref:System.Drawing.Image>와 같은 <xref:System.Drawing.Bitmap> 또는 <xref:System.Drawing.Imaging.Metafile>합니다. 예제를 다음과 같이 보여 줍니다.  
  
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
  
2.  만들기는 <xref:System.Drawing.Graphics> 사용 하려는 그리기 화면을 나타내는 개체입니다. 자세한 내용은 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하세요.  
  
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
  
3.  호출 된 <xref:System.Drawing.Graphics.DrawImage%2A> 이미지를 렌더링 하 여 그래픽 개체의 합니다. 가져올 이미지 및 이미지를 가져올 좌표를 지정해야 합니다.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [GDI+의 펜, 선 및 사각형](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [방법: Windows Form에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [선 또는 닫힌된 그림 그리기](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)
