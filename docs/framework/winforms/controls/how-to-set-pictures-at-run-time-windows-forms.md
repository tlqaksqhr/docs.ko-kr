---
title: '방법: 런타임에 그림 설정(Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: fedddf56966c3ab11a1dfb20c1d4cbd8a45fb1a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>방법: 런타임에 그림 설정(Windows Forms)
Windows Forms에 표시 되는 이미지를 프로그래밍 방식으로 설정할 수 있습니다 <xref:System.Windows.Forms.PictureBox> 제어 합니다.  
  
### <a name="to-set-a-picture-programmatically"></a>그림을 프로그래밍 방식으로 설정 하려면  
  
-   설정의 <xref:System.Windows.Forms.PictureBox.Image%2A> 사용 하 여 속성의 <xref:System.Drawing.Image.FromFile%2A> 의 메서드는 <xref:System.Drawing.Image> 클래스입니다.  
  
     아래 예제에서는 내 문서 폴더는 이미지의 위치에 대 한 설정 되었습니다. 이 도구를 실행 하므로 대부분의 Windows 운영 체제 실행 컴퓨터는이 디렉터리를 포함 되어 있습니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 응용 프로그램을 실행할 수 있습니다. 다음 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.PictureBox> 컨트롤이 이미 추가 합니다.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>그래픽을 지우려면  
  
-   첫째, 이미지를 사용 하 고 메모리를 해제 하 고 그래픽 선택을 취소 합니다. 나중에 가비지 수집 됩니다는 메모리를 확보 메모리 관리 문제가 되 면입니다.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  이유에 대 한 자세한 내용은 사용할지는 <xref:System.Drawing.Image.Dispose%2A> 이러한 방식으로 메서드 참조 [관리 되지 않는 리소스를 정리 하는](../../../../docs/standard/garbage-collection/unmanaged.md)합니다.  
  
     이 코드는 그래픽 디자인 타임에 컨트롤을 컨트롤에 로드 하는 경우에 이미지가 삭제 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.PictureBox>  
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>  
 [PictureBox 컨트롤 개요](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [방법: 디자이너를 사용하여 그림 로드](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [방법: 런타임에 그림의 크기 또는 위치 수정](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [PictureBox 컨트롤](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
