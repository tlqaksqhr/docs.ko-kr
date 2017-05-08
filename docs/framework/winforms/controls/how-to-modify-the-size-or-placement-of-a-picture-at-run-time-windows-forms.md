---
title: "방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms) | Microsoft Docs"
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
  - "예제[Windows Forms], PictureBox 컨트롤"
  - "이미지[Windows Forms], PictureBox 컨트롤에서 위치 제어[Windows Forms]"
  - "PictureBox 컨트롤[Windows Forms], 그림 크기 및 정렬"
  - "그림, PictureBox 컨트롤에서 위치 제어[Windows Forms]"
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms)
폼에서 Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용하는 경우 컨트롤에 대해 다음과 같은 작업이 수행되도록 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 속성을 설정할 수 있습니다.  
  
-   그림의 상단 왼쪽 모퉁이를 컨트롤의 상단 왼쪽 모퉁이와 일치하게 배치합니다.  
  
-   그림을 컨트롤 가운데에 배치합니다.  
  
-   컨트롤에 표시된 그림과 일치하도록 컨트롤의 크기를 조정합니다.  
  
-   표시된 그림을 컨트롤에 맞게 확장합니다.  
  
 그림 특히 비트맵 형식의 그림을 확장하면 이미지 품질이 손상될 수도 있습니다.  메타파일은 런타임의 이미지 그리기에 대한 그래픽 지침 목록이며 비트맵보다 확장에 더욱 적합합니다.  
  
### 런타임에 SizeMode 속성을 설정하려면  
  
1.  <xref:System.Windows.Forms.PictureBox.SizeMode%2A>를 <xref:System.Windows.Forms.PictureBoxSizeMode>\(기본값\), <xref:System.Windows.Forms.PictureBoxSizeMode>, <xref:System.Windows.Forms.PictureBoxSizeMode> 또는 <xref:System.Windows.Forms.PictureBoxSizeMode>로 설정합니다.  <xref:System.Windows.Forms.PictureBoxSizeMode>로 설정하면 이미지가 컨트롤의 왼쪽 위 모퉁이에 배치됩니다. 이미지가 컨트롤보다 크면 이미지의 아래쪽과 오른쪽 모퉁이가 잘립니다.  <xref:System.Windows.Forms.PictureBoxSizeMode>로 설정하면 이미지가 컨트롤의 가운데에 배치됩니다. 이미지가 컨트롤보다 크면 이미지의 외곽이 잘립니다.  <xref:System.Windows.Forms.PictureBoxSizeMode>로 설정하면 컨트롤 크기가 이미지 크기에 맞게 조정됩니다.  이와 반대로 <xref:System.Windows.Forms.PictureBoxSizeMode>로 설정하면 이미지 크기가 컨트롤 크기에 맞게 조정됩니다.  
  
     다음 예제에서 이미지의 위치로 설정된 경로는 내 문서 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 이 위치를 선택하면 사용자는 최소한의 시스템 액세스 수준으로 응용 프로그램을 안전하게 실행할 수 있습니다.  아래 예제에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤이 포함된 폼을 이미 추가한 것으로 가정합니다.  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.PictureBox>   
 [How to: Load a Picture Using the Designer](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [PictureBox 컨트롤 개요](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [방법: 런타임에 그림 설정](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox 컨트롤](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)