---
title: "방법: Windows Forms RichTextBox 컨트롤에 파일 로드 | Microsoft Docs"
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
  - "텍스트 상자, 파일 표시"
  - "예제[Windows Forms], 텍스트 상자"
  - ".rtf 파일, RichTextBox 컨트롤에서 열기"
  - "RTF 파일, RichTextBox 컨트롤에서 열기"
  - "텍스트 파일, RichTextBox 컨트롤에 표시"
  - ".rtf 파일, RichTextBox 컨트롤에 표시"
  - "RichTextBox 컨트롤 [Windows Forms], 파일 열기"
  - "RTF 파일, RichTextBox 컨트롤에 표시"
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms RichTextBox 컨트롤에 파일 로드
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 일반 텍스트, 유니코드 일반 텍스트 또는 RTF\(서식 있는 텍스트\) 파일을 표시할 수 있습니다. 이렇게 하려면 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 메서드를 호출합니다. 스트림에서 데이터를 로드하려면 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 메서드를 사용할 수도 있습니다. 자세한 내용은 <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하십시오.  
  
### RichTextBox 컨트롤에 파일을 로드하려면  
  
1.  <xref:System.Windows.Forms.OpenFileDialog> 구성 요소를 사용하여 열 파일의 경로를 확인합니다. 전체적인 개요를 보려면 [OpenFileDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md)를 참조하세요.  
  
2.  <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 메서드를 호출하여 로드할 파일 및 선택적으로 파일 형식을 지정합니다. 아래 예제에서는 로드할 파일을 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소의 <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성에서 가져옵니다. 파일 이름을 유일한 인수로 사용하여 메서드를 호출하면 파일 형식은 RTF로 간주됩니다. 다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.  
  
     다음 예제에서는 단추를 클릭할 때 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 표시됩니다. 선택한 파일은 <xref:System.Windows.Forms.RichTextBox> 컨트롤에서 열리고 표시됩니다. 이 예에서는 폼에 단추\(`btnOpenFile`\)가 있다고 가정합니다.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> 클래스에서 부여한 권한 수준이 필요할 수 있습니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)