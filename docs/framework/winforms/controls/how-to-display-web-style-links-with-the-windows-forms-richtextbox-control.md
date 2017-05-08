---
title: "방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시 | Microsoft Docs"
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
  - "예제[Windows Forms], 텍스트 상자"
  - "RichTextBox 컨트롤[Windows Forms], 웹 페이지에 연결"
  - "텍스트 상자, 웹 링크 표시"
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하여 밑줄이 그어진 컬러 웹 링크를 표시할 수 있습니다.  링크를 클릭하면 링크 텍스트에 지정된 웹 사이트가 브라우저 창에 표시되도록 코드를 작성할 수 있습니다.  
  
### RichTextBox 컨트롤을 사용하여 웹 페이지에 연결하려면  
  
1.  <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 올바른 URL\(예: "http:\/\/www.microsoft.com\/korea"\)을 포함하는 문자열로 설정합니다.  
  
2.  <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성이 기본값인 `true`로 설정되어 있는지 확인합니다.  
  
3.  <xref:System.Diagnostics.Process> 개체의 새 전역 인스턴스를 만듭니다.  
  
4.  브라우저에 원하는 텍스트를 보내는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트에 대한 이벤트 처리기를 작성합니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트를 사용하여 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성에 지정된 URL에서 Internet Explorer의 인스턴스를 엽니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 포함되어 있다고 가정합니다.  
  
    > [!IMPORTANT]
    >  <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName> 메서드를 호출할 때 부분 신뢰 컨텍스트에서 코드를 실행하면 권한이 충분하지 않기 때문에 <xref:System.Security.SecurityException> 예외가 발생합니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하십시오.  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 문을 포함하여`p` 프로세스를 초기화해야 합니다.  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     만든 프로세스를 사용하여 작업을 마쳤으면 즉시 프로세스를 중지해야 합니다.  위에 나오는 코드의 경우 프로세스를 중지하는 코드는 다음과 같습니다.  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>   
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)