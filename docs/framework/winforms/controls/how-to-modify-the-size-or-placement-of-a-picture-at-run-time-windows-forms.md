---
title: "방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df67871b0b133297a6f53ff9e4a42c7630a5f56d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms)
Windows Forms를 사용 하는 경우 <xref:System.Windows.Forms.PictureBox> 컨트롤을 폼에 설정할 수 있습니다는 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 시키기 위해 속성:  
  
-   그림의 왼쪽된 위 모퉁이와 컨트롤의 왼쪽된 위 모퉁이 정렬 합니다.  
  
-   컨트롤 내에서 가운데  
  
-   그림 표시에 맞게 컨트롤 크기 조정  
  
-   컨트롤에 맞게 표시 사진을 늘이기  
  
 그림 (특히 비트맵 형식으로 하나) 스트레치할 이미지 품질에서 손실이 발생할 수 있습니다. 메타 파일은 실행 시 이미지를 그리기 위한 그래픽 지침 목록이는 비트맵 보다 스트레치에 적합 한 더 합니다.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>런타임 시 SizeMode 속성을 설정 하려면  
  
1.  설정 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 를 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (기본값) 이면 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, 또는 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>합니다. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>컨트롤의 왼쪽 위 구석에;에 이미지를 배치 하는 방법 이미지 컨트롤 보다 큰 경우 아래쪽과 오른쪽 가장자리 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>이미지 컨트롤에서 가운데 정렬 되어 있음을 의미 합니다. 이미지 컨트롤 보다 큰 경우 그림의 바깥쪽 가장자리 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>컨트롤의 크기를 이미지의 크기를 조정할 수 있다는 것을 의미 합니다. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>와 반대 및 이미지의 크기를 컨트롤의 크기를 조정할 수 있다는 것을 의미 합니다.  
  
     아래 예제에서는 내 문서 폴더는 이미지의 위치에 대 한 설정 되었습니다. 이 도구를 실행 하므로 대부분의 Windows 운영 체제 실행 컴퓨터는이 디렉터리를 포함 되어 있습니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 응용 프로그램을 실행할 수 있습니다. 다음 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.PictureBox> 컨트롤이 이미 추가 합니다.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.PictureBox>  
 [방법: 디자이너를 사용하여 그림 로드](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [PictureBox 컨트롤 개요](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [방법: 런타임에 그림 설정](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox 컨트롤](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
