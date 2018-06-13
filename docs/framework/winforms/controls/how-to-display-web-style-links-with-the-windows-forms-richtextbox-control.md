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
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="499ca-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시</span><span class="sxs-lookup"><span data-stu-id="499ca-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="499ca-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 색이 지정 된이 및 밑줄 표시 된 웹 링크를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="499ca-104">브라우저 창에 링크를 클릭 하면 링크 텍스트에 지정 된 웹 사이트를 표시 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="499ca-105">RichTextBox 컨트롤에서 웹 페이지에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="499ca-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="499ca-106">설정의 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 올바른 URL을 포함 하는 문자열 (예를 들어 "http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="499ca-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="499ca-107">확인은 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성이로 설정 되어 `true` (기본값).</span><span class="sxs-lookup"><span data-stu-id="499ca-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="499ca-108">새 전역 인스턴스를 만들고는 <xref:System.Diagnostics.Process> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="499ca-109">에 대 한 이벤트 처리기를 작성은 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 브라우저 원하는 텍스트를 전송 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="499ca-110">다음 예제에는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트에 지정 된 URL Internet Explorer의 인스턴스를 열고는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성의는 <xref:System.Windows.Forms.RichTextBox> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="499ca-111">이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="499ca-112">호출에는 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 메서드를 발생 하 게는 <xref:System.Security.SecurityException> 권한이 부족으로 인해 부분 신뢰 컨텍스트에서 코드를 실행 하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="499ca-113">자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="499ca-113">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="499ca-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 프로세스를 초기화 해야 `p`, 폼의 생성자에 다음 문을 포함 하 여 수행할 수 있는:</span><span class="sxs-lookup"><span data-stu-id="499ca-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="499ca-115">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="499ca-116">즉시 사용 하 여 작업을 완료 했으면 만든 프로세스를 중지 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="499ca-117">위에 나와 있는 코드를 참조 하는 프로세스를 중지 하는 코드 다음과 같이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499ca-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="499ca-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="499ca-118">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="499ca-119">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="499ca-119">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="499ca-120">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="499ca-120">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
