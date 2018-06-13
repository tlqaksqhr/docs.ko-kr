---
title: '방법: Windows Forms LinkLabel 컨트롤의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: e1bb0ecba6fd8ddf66c6debb90ef4dd94641a97e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531488"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="89981-102">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="89981-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="89981-103">표시 되는 텍스트를 변경할 수는 <xref:System.Windows.Forms.LinkLabel> 다양 한 목적에 맞게 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="89981-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="89981-104">예를 들어 것이 일반적 텍스트에 밑줄 특정 색에 표시할 텍스트를 설정 하 여 클릭 수 있는 사용자에 게 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89981-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="89981-105">텍스트를 클릭 한 후 다른 색으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="89981-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="89981-106">이러한 동작을 제어 하려면 5 개의 서로 다른 속성을 설정할 수 있습니다:는 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, 및 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89981-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="89981-107">LinkLabel 컨트롤의 모양을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="89981-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="89981-108">설정의 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성을 원하는 색입니다.</span><span class="sxs-lookup"><span data-stu-id="89981-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="89981-109">이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="89981-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2.  <span data-ttu-id="89981-110">설정의 <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션입니다.</span><span class="sxs-lookup"><span data-stu-id="89981-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="89981-111">이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="89981-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="89981-112">설정의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 어느 부분이 캡션 링크로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89981-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="89981-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 표시는 <xref:System.Windows.Forms.LinkArea> 두 개의 번호, 시작 문자 위치 및 문자 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="89981-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="89981-114">이렇게 중 하나에서 프로그래밍 방식으로 또는 디자인 타임에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="89981-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="89981-115">설정의 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, 또는 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>합니다.</span><span class="sxs-lookup"><span data-stu-id="89981-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="89981-116">로 설정 되어 있으면 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, 부분에 의해 결정 캡션 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 포인터 위에 있을 때만 밑줄이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89981-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="89981-117">에 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 설정 하는 이벤트 처리기는 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="89981-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="89981-118">링크를 방문 했을 때 어떤 방식으로든에서 모양을 일반적으로 색으로 변경 하려면 일반적으로 되었기입니다.</span><span class="sxs-lookup"><span data-stu-id="89981-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="89981-119">텍스트로 지정 된 색으로 변경 됩니다는 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89981-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="89981-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89981-120">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [<span data-ttu-id="89981-121">LinkLabel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="89981-121">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [<span data-ttu-id="89981-122">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="89981-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="89981-123">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="89981-123">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
