---
title: "방법: OpenFileDialog 구성 요소를 사용하여 파일 열기"
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
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52726a770e33bec4b5ec9b24f33deb44ed6379b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>방법: OpenFileDialog 구성 요소를 사용하여 파일 열기
<xref:System.Windows.Forms.OpenFileDialog> 구성 요소에는 사용자가 자신의 컴퓨터 또는 네트워크에 있는 모든 컴퓨터의 폴더를 탐색 하 고 하나 이상의 파일을 선택 하려면 허용 합니다. 대화 상자에서 사용자가 선택한 파일의 경로와 이름을 반환합니다.  
  
 열려는 파일을 선택한 경우 파일을 여는 메커니즘에 대한 두 가지 방법이 있습니다. 파일 스트림을 사용 하는 것을 선호 하는 경우의 인스턴스를 만들 수 있습니다는 <xref:System.IO.StreamReader> 클래스입니다. 또는 사용할 수는 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드 선택한 파일을 엽니다.  
  
 아래의 첫 번째 예는 <xref:System.Security.Permissions.FileIOPermission> 권한 검사 (하면 "보안 정보" 아래에 설명 된) 하는 대로 하지만 파일 이름에 액세스할 수 있습니다. 이 방법은 로컬 컴퓨터, 인트라넷 및 인터넷 영역에서 사용할 수 있습니다. 두 번째 방법에서는 <xref:System.Security.Permissions.FileIOPermission> 권한 검사 하지만 적합 인트라넷 또는 인터넷 영역에 응용 프로그램입니다.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>OpenFileDialog 구성 요소를 사용하여 파일을 스트림으로 열려면  
  
1.  **파일 열기** 대화 상자를 표시하고, 사용자가 선택한 파일을 여는 메서드를 호출합니다.  
  
     한 가지 방법은 사용 하는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 파일 열기 대화 상자를 표시 하 고 인스턴스를 사용 하는 메서드는 <xref:System.IO.StreamReader> 클래스 파일을 열 수 있습니다.  
  
     사용 하 여 다음 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기의 인스턴스를 열려면는 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소입니다. 파일을 선택하고 사용자가 **확인**을 클릭하면 대화 상자에서 선택한 파일이 열립니다. 이 경우 메시지 상자에 내용을 표시하여 파일 스트림을 읽었음을 보여 줍니다.  
  
    > [!IMPORTANT]
    >  가져오거나 설정할는 <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성, 어셈블리 권한 수준에서 부여 필요는 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스입니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
     이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 제어 및 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소입니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  파일 스트림에서 읽기에 대 한 자세한 내용은 참조 <xref:System.IO.FileStream.BeginRead%2A> 및 <xref:System.IO.FileStream.Read%2A>합니다.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>OpenFileDialog 구성 요소를 사용하여 파일을 파일로 열려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 대화 상자를 표시 하는 메서드 및 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드는 파일을 엽니다.  
  
     <xref:System.Windows.Forms.OpenFileDialog> 구성 요소의 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드는 파일을 구성 하는 바이트를 반환 합니다. 이러한 바이트는 읽을 스트림을 제공합니다. 다음 예제에는 <xref:System.Windows.Forms.OpenFileDialog> 사용자가 파일 이름 확장명의 파일만 선택할 수 있도록을 "cursor"에 대 한 필터와 구성 요소를 인스턴스화할`.cur`합니다. `.cur` 파일을 선택하면 양식의 커서가 선택한 커서로 설정됩니다.  
  
    > [!IMPORTANT]
    >  호출 하 여 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드, 어셈블리 권한 수준에서 부여 필요는 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
     이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog 구성 요소](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
