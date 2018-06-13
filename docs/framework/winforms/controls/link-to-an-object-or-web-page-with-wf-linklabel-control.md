---
title: '방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 9957eae7e15c99ec259574b435402420c6bcf5f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539635"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="973d7-102">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="973d7-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="973d7-103">Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤 폼에서 웹 스타일 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="973d7-104">링크를 클릭할 때 링크를 방문한 나타내는 색을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="973d7-105">색 변경에 대 한 자세한 내용은 참조 하십시오. [하는 방법: Windows Forms LinkLabel 컨트롤의 모양을 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>  
  
## <a name="linking-to-another-form"></a><span data-ttu-id="973d7-106">다른 폼에 링크</span><span class="sxs-lookup"><span data-stu-id="973d7-106">Linking to Another Form</span></span>  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="973d7-107">LinkLabel 컨트롤에 다른 폼에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="973d7-107">To link to another form with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="973d7-108">설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="973d7-109">설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="973d7-110">표시 되는 링크 레이블 모양 관련 속성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="973d7-111"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값으로 표시 됩니다는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 두 숫자, 시작 문자 위치와 문자 수가 들어 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="973d7-112"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 또는 다음과 유사한 방식으로 코드를 속성 창에서 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  <span data-ttu-id="973d7-113">에 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기 호출의 <xref:System.Windows.Forms.Form.Show%2A> 다른 폼에서 프로젝트를 열고 설정 하는 메서드는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="973d7-114">인스턴스는 <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> 클래스에 대 한 참조를 전달는 <xref:System.Windows.Forms.LinkLabel> 캐스팅할 필요가 없습니다 이므로 클릭 된 컨트롤의 `sender` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a><span data-ttu-id="973d7-115">웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="973d7-115">Linking to a Web Page</span></span>  
 <span data-ttu-id="973d7-116"><xref:System.Windows.Forms.LinkLabel> 컨트롤 기본 브라우저와 웹 페이지를 표시 하려면 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="973d7-117">LinkLabel 컨트롤을 Internet Explorer와 웹 페이지 링크를 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="973d7-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="973d7-118">설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="973d7-119">설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
3.  <span data-ttu-id="973d7-120"><xref:System.Windows.Forms.LinkLabel.LinkClicked> 예외 처리 블록을 가운데 이벤트 처리기 호출을 설정 하는 두 번째 절차는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true` 사용 하 여는 <xref:System.Diagnostics.Process.Start%2A> 메서드를 URL로 기본 브라우저를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="973d7-121">사용 하는 <xref:System.Diagnostics.Process.Start%2A> 에 대 한 참조를 추가 해야 하는 메서드는 <xref:System.Diagnostics?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="973d7-122">아래 코드는 부분 신뢰 환경에서 실행 된 경우 (같은 공유 드라이브에 있음) 때 JIT 컴파일러가 실패는 `VisitLink` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="973d7-123">`System.Diagnostics.Process.Start` 문을 실행 하면 실패 하는 링크 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="973d7-124">예외를 catch 하 여 때는 `VisitLink` 메서드가 호출 되 면 아래 코드에서 JIT 컴파일러에 오류가 발생 하면 오류는 처리 되도록 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="973d7-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="973d7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="973d7-125">See Also</span></span>  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="973d7-126">LinkLabel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="973d7-126">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [<span data-ttu-id="973d7-127">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="973d7-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)  
 [<span data-ttu-id="973d7-128">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="973d7-128">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
