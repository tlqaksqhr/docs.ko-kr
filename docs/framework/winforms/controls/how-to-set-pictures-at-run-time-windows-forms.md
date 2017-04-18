---
title: "방법: 런타임에 그림 설정(Windows Forms) | Microsoft Docs"
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
  - "비트맵[Windows Forms], PictureBox 컨트롤에 표시[Windows Forms]"
  - "예제[Windows Forms], PictureBox 컨트롤"
  - "이미지[Windows Forms], PictureBox 컨트롤을 사용하여 추가[Windows Forms]"
  - "PictureBox 컨트롤[Windows Forms], 이미지 추가"
  - "PictureBox 컨트롤[Windows Forms], 그림 추가"
  - "그림, 표시 설정"
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 런타임에 그림 설정(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤에서 표시하는 이미지를 프로그래밍 방식으로 설정할 수 있습니다.  
  
### 프로그래밍 방식으로 그림을 설정하려면  
  
-   <xref:System.Drawing.Image> 클래스의 <xref:System.Drawing.Image.FromFile%2A> 메서드를 사용하여 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 설정합니다.  
  
     다음 예제에서 이미지의 위치로 설정된 경로는 내 문서 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 이 위치를 선택하면 사용자는 최소한의 시스템 액세스 수준으로 응용 프로그램을 안전하게 실행할 수 있습니다.  아래 예제에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤이 포함된 폼을 이미 추가한 것으로 가정합니다.  
  
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
  
### 그래픽을 지우려면  
  
-   먼저 이미지에 사용되는 메모리를 해제한 다음 그래픽을 지웁니다.  나중에 메모리를 관리하는 데 문제가 생기면 가비지 수집을 통해 메모리가 확보됩니다.  
  
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
    >  이런 방법으로 <xref:System.Drawing.Image.Dispose%2A> 메서드를 사용해야 하는 이유에 대한 자세한 내용은 [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md)를 참조하십시오.  
  
     이 코드는 디자인 타임에 그래픽을 컨트롤에 로드했더라도 이미지를 지웁니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.PictureBox>   
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>   
 [PictureBox 컨트롤 개요](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [How to: Load a Picture Using the Designer](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [방법: 런타임에 그림의 크기 또는 위치 수정](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [PictureBox 컨트롤](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)