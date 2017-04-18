---
title: "방법: SaveFileDialog 구성 요소를 사용하여 파일 저장 | Microsoft Docs"
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
  - "파일, 저장"
  - "OpenFile 메서드, SaveFileDialog 구성 요소를 사용하여 파일 저장"
  - "SaveFileDialog 구성 요소, 파일 저장"
  - "파일 저장"
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: SaveFileDialog 구성 요소를 사용하여 파일 저장
<xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용하면 사용자가 파일 시스템을 검색하여 저장할 파일을 선택할 수 있습니다.  이 때 사용자가 대화 상자에서 선택한 파일의 이름과 경로가 대화 상자에 반환됩니다.  그러나 실제로 파일을 디스크에 쓰는 코드를 작성해야 합니다.  
  
### SaveFileDialog 구성 요소를 사용하여 파일을 저장하려면  
  
-   **파일 저장** 대화 상자를 표시하고 메서드를 호출하여 사용자가 선택한 파일을 저장합니다.  
  
     <xref:System.Windows.Forms.SaveFileDialog> 구성 요소의 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드를 사용하여 파일을 저장합니다.  이 메서드를 사용하면 <xref:System.IO.Stream> 개체를 통해 파일을 쓸 수 있습니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.DialogResult> 속성을 사용하여 파일 이름을 가져오고 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용하여 파일을 저장합니다.  <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드를 사용하면 스트림에 파일을 쓸 수 있습니다.  
  
     아래 예제에는 이미지가 할당된 <xref:System.Windows.Forms.Button> 컨트롤이 있습니다.  이 단추를 클릭하면 .gif, .jpeg 및 .bmp 형식의 파일을 허용하는 필터와 함께 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소가 인스턴스화됩니다.  파일 저장 대화 상자에서 이 형식의 파일을 선택하면 단추의 이미지가 저장됩니다.  
  
    > [!IMPORTANT]
    >  <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성을 가져오거나 설정하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> 클래스에서 부여하는 권한 수준이 필요합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하십시오.  
  
     이 예제에서는 <xref:System.Windows.Forms.ButtonBase.Image%2A> 속성이 .gif, .jpeg 또는 .bmp 형식의 파일로 설정된 <xref:System.Windows.Forms.Button> 컨트롤이 폼에 있다고 가정합니다.  
  
    > [!NOTE]
    >  상속으로 인해 <xref:System.Windows.Forms.SaveFileDialog> 클래스의 일부가 된 <xref:System.Windows.Forms.FileDialog> 클래스의 <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> 속성은 1부터 시작하는 인덱스를 사용합니다.  파일을 일반 텍스트나 이진 형식으로 저장하는 것과 같이 데이터를 특정 형식으로 저장하는 코드를 작성하는 경우 인덱스의 시작 번호가 중요합니다.  아래 예제에서 이 속성에 대해 자세히 볼 수 있습니다.  
  
    ```vb  
    Private Sub Button2_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button2.Click  
       ' Displays a SaveFileDialog so the user can save the Image  
       ' assigned to Button2.  
       Dim saveFileDialog1 As New SaveFileDialog()  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"  
       saveFileDialog1.Title = "Save an Image File"  
       saveFileDialog1.ShowDialog()  
  
       ' If the file name is not an empty string open it for saving.  
       If saveFileDialog1.FileName <> "" Then  
          ' Saves the Image via a FileStream created by the OpenFile method.  
          Dim fs As System.IO.FileStream = Ctype _  
             (saveFileDialog1.OpenFile(), System.IO.FileStream)  
          ' Saves the Image in the appropriate ImageFormat based upon the  
          ' file type selected in the dialog box.  
          ' NOTE that the FilterIndex property is one-based.  
          Select Case saveFileDialog1.FilterIndex  
             Case 1  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Jpeg)  
  
             Case 2  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Bmp)  
  
             Case 3  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Gif)  
           End Select  
  
           fs.Close()  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button2_Click(object sender, System.EventArgs e)  
    {  
       // Displays a SaveFileDialog so the user can save the Image  
       // assigned to Button2.  
       SaveFileDialog saveFileDialog1 = new SaveFileDialog();  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
       saveFileDialog1.Title = "Save an Image File";  
       saveFileDialog1.ShowDialog();  
  
       // If the file name is not an empty string open it for saving.  
       if(saveFileDialog1.FileName != "")  
       {  
          // Saves the Image via a FileStream created by the OpenFile method.  
          System.IO.FileStream fs =   
             (System.IO.FileStream)saveFileDialog1.OpenFile();  
          // Saves the Image in the appropriate ImageFormat based upon the  
          // File type selected in the dialog box.  
          // NOTE that the FilterIndex property is one-based.  
          switch(saveFileDialog1.FilterIndex)  
          {  
             case 1 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Jpeg);  
             break;  
  
             case 2 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Bmp);  
             break;  
  
             case 3 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Gif);  
             break;  
          }  
  
       fs.Close();  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void button2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays a SaveFileDialog so the user can save the Image  
          // assigned to Button2.  
          SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();  
          saveFileDialog1->Filter =   
             "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
          saveFileDialog1->Title = "Save an Image File";  
          saveFileDialog1->ShowDialog();  
          // If the file name is not an empty string, open it for saving.  
          if(saveFileDialog1->FileName != "")  
          {  
             // Saves the Image through a FileStream created by  
             // the OpenFile method.  
             System::IO::FileStream ^ fs =   
                safe_cast<System::IO::FileStream*>(  
                saveFileDialog1->OpenFile());  
             // Saves the Image in the appropriate ImageFormat based on  
             // the file type selected in the dialog box.  
             // Note that the FilterIndex property is one based.  
             switch(saveFileDialog1->FilterIndex)  
             {  
                case 1 :  
                   this->button2->Image->Save(fs,  
                      System::Drawing::Imaging::ImageFormat::Jpeg);  
                   break;  
                case 2 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Bmp);  
                   break;  
                case 3 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Gif);  
                   break;  
             }  
          fs->Close();  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     파일 스트림 쓰기에 대한 자세한 내용은 [FileStream.BeginWrite 메서드](frlrfSystemIOFileStreamClassBeginWriteTopic) 및 [FileStream.Write 메서드](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx)를 참조하십시오.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.RichTextBox> 컨트롤 같은 특정 컨트롤에는 파일 저장 기능이 있습니다.  자세한 내용은 MSDN Online Library 기술 기사 [Essential Code for Windows Forms Dialog Boxes](http://go.microsoft.com/fwlink/?LinkID=102575)의 "SaveFileDialog Component" 단원을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog 구성 요소](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)