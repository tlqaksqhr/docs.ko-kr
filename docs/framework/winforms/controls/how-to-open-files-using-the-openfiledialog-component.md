---
title: "방법: OpenFileDialog 구성 요소를 사용하여 파일 열기 | Microsoft Docs"
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
  - "파일, OpenFileDialog 구성 요소를 사용하여 열기"
  - "OpenFile 메서드"
  - "OpenFile 메서드, OpenFileDialog 구성 요소"
  - "OpenFileDialog 구성 요소, 파일 열기"
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: OpenFileDialog 구성 요소를 사용하여 파일 열기
<xref:System.Windows.Forms.OpenFileDialog> 구성 요소를 사용하면 사용자 컴퓨터 또는 네트워크로 연결된 모든 컴퓨터에서 폴더를 찾아보고 이 중에서 열려는 파일을 하나 이상 선택할 수 있습니다.  이 때 사용자가 대화 상자에서 선택한 파일의 이름과 경로가 대화 상자에 반환됩니다.  
  
 대상 파일을 선택한 후에는 두 가지 방법을 사용하여 파일을 열 수 있습니다.  파일 스트림을 사용하려면 <xref:System.IO.StreamReader> 클래스의 인스턴스를 만듭니다.  또는 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용하여 선택된 파일을 열 수도 있습니다.  
  
 아래의 첫 번째 예제에서는 "보안 참고 사항"에 설명되어 있는 것처럼 <xref:System.Security.Permissions.FileIOPermission> 권한 검사를 수행하지만 파일 이름에 액세스할 수 있습니다.  이 방법은 로컬 컴퓨터, 인트라넷 및 인터넷 영역에서 사용할 수 있습니다.  두 번째 방법도 <xref:System.Security.Permissions.FileIOPermission> 권한 검사를 수행하지만 인트라넷 또는 인터넷 영역의 응용 프로그램에 더 적합합니다.  
  
### OpenFileDialog 구성 요소를 사용하여 파일을 스트림으로 열려면  
  
1.  **파일 열기** 대화 상자를 표시하고 메서드를 호출하여 사용자가 선택한 파일을 엽니다.  
  
     <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 파일 열기 대화 상자를 표시하고 <xref:System.IO.StreamReader> 클래스의 인스턴스를 사용하여 파일을 열 수 있습니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용하여 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소의 인스턴스를 엽니다.  파일이 선택된 상태에서 사용자가 **확인**을 클릭하면 대화 상자에서 선택된 파일이 열립니다.  이런 경우 파일 스트림을 읽었다는 것을 나타내기 위해 내용이 메시지 상자에 표시됩니다.  
  
    > [!IMPORTANT]
    >  <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성을 가져오거나 설정하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> 클래스에서 부여하는 권한 수준이 필요합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하십시오.  
  
     이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤과 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 있다고 가정합니다.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  파일 스트림에서 읽는 데 대한 자세한 내용은 [FileStream.BeginRead 메서드](frlrfSystemIOFileStreamClassBeginReadTopic) 및 [FileStream.Read 메서드](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)를 참조하십시오.  
  
### OpenFileDialog 구성 요소를 사용하여 파일을 파일로 열려면  
  
1.  <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용하여 파일을 엽니다.  
  
     <xref:System.Windows.Forms.OpenFileDialog> 구성 요소의 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드는 파일을 구성하는 바이트를 반환합니다.  이러한 바이트는 읽을 스트림을 제공합니다.  아래 예제에서는 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 "cursor" 필터와 함께 인스턴스화되므로 사용자는 파일 확장명이 `.cur`인 파일만 선택할 수 있습니다.  `.cur`  파일이 선택되면 폼의 커서가 선택된 커서로 설정됩니다.  
  
    > [!IMPORTANT]
    >  <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 호출하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> 클래스에서 부여하는 권한 수준이 필요합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하십시오.  
  
     이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤이 있다고 가정합니다.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog 구성 요소](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)