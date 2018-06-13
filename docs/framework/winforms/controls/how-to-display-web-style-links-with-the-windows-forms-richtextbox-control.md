---
title: '방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: bd813d479cd4dfb61a08d9a8c4a4e7612084e878
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532609"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 색이 지정 된이 및 밑줄 표시 된 웹 링크를 표시할 수 있습니다. 브라우저 창에 링크를 클릭 하면 링크 텍스트에 지정 된 웹 사이트를 표시 하는 코드를 작성할 수 있습니다.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>RichTextBox 컨트롤에서 웹 페이지에 연결 하려면  
  
1.  설정의 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 올바른 URL을 포함 하는 문자열 (예를 들어 "http://www.microsoft.com/").  
  
2.  확인은 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성이로 설정 되어 `true` (기본값).  
  
3.  새 전역 인스턴스를 만들고는 <xref:System.Diagnostics.Process> 개체입니다.  
  
4.  에 대 한 이벤트 처리기를 작성은 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 브라우저 원하는 텍스트를 전송 하는 이벤트입니다.  
  
     다음 예제에는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트에 지정 된 URL Internet Explorer의 인스턴스를 열고는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성의는 <xref:System.Windows.Forms.RichTextBox> 컨트롤입니다. 이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.  
  
    > [!IMPORTANT]
    >  호출에는 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 메서드를 발생 하 게는 <xref:System.Security.SecurityException> 권한이 부족으로 인해 부분 신뢰 컨텍스트에서 코드를 실행 하는 경우는 예외입니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
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
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 프로세스를 초기화 해야 `p`, 폼의 생성자에 다음 문을 포함 하 여 수행할 수 있는:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
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
  
     즉시 사용 하 여 작업을 완료 했으면 만든 프로세스를 중지 하는 것이 유용 합니다. 위에 나와 있는 코드를 참조 하는 프로세스를 중지 하는 코드 다음과 같이 표시 될 수 있습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
