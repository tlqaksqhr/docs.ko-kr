---
title: "연습: 런타임에 상태 표시줄 정보 업데이트"
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
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c67aa303f375734408201ce15d1c3db3dc32c8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="99c2e-102">연습: 런타임에 상태 표시줄 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="99c2e-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="99c2e-103"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤 교체 및 기능을 추가 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나는 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 버전과 호환성 및 이후 사용에 대 한 컨트롤이 유지 되는 경우 있습니다 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="99c2e-104">보통은, 프로그램이 응용 프로그램 상태나 다른 사용자 상호 작용에 대한 변경 내용을 기반으로, 런타임에 상태 표시줄 패널의 내용을 동적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="99c2e-105">이것은 CAPS LOCK, NUM LOCK 또는 SCROLL LOC과 같은 키가 활성화되어 있음을 사용자에게 알리거나 날짜 또는 시간을 편리한 참조로 제공하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="99c2e-106">다음 예제에서는 사용 하 여의 인스턴스는 <xref:System.Windows.Forms.StatusBarPanel> 클래스 시계를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="99c2e-107">상태 표시줄 업데이트를 준비하려면</span><span class="sxs-lookup"><span data-stu-id="99c2e-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="99c2e-108">새 Windows Form을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="99c2e-109">폼에 <xref:System.Windows.Forms.StatusBar> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="99c2e-110">자세한 내용은 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99c2e-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="99c2e-111">상태 표시줄 패널을 추가 하면 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="99c2e-112">자세한 내용은 [방법: StatusBar 컨트롤에 패널 추가](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99c2e-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="99c2e-113">에 대 한는 <xref:System.Windows.Forms.StatusBar> 컨트롤을 양식에 추가 설정에서 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="99c2e-114">Windows Forms 추가 <xref:System.Windows.Forms.Timer> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99c2e-115">Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 구성 요소는 Windows Forms 환경에 대 한 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="99c2e-116">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99c2e-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="99c2e-117"><xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="99c2e-118">설정의 <xref:System.Windows.Forms.Timer.Interval%2A> 의 속성은 <xref:System.Windows.Forms.Timer> 을 30000 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99c2e-119"><xref:System.Windows.Forms.Timer.Interval%2A> 의 속성은 <xref:System.Windows.Forms.Timer> 구성 요소는 정확한 시간 표시 된 시간에 반영 되어 있는지 확인 하려면 30 초 (30000 밀리초)으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="99c2e-120">상태 표시줄을 업데이트하도록 타이머를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="99c2e-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="99c2e-121">이벤트 처리기에 다음 코드를 삽입는 <xref:System.Windows.Forms.Timer> 의 패널을 업데이트 하는 구성 요소는 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="99c2e-122">이제 응용 프로그램을 실행하고 상태 표시줄 패널에서 시계가 실행되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="99c2e-123">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="99c2e-123">To test the application</span></span>  
  
1.  <span data-ttu-id="99c2e-124">응용 프로그램을 디버깅하고 F5 키를 눌러 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="99c2e-125">디버깅에 대한 자세한 내용은 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99c2e-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99c2e-126">상태 표시줄에 시계가 나타나는 데 약 30초가 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="99c2e-127">가능한 가장 정확한 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="99c2e-128">반대로, 곧 나타납니다 시계를 줄일 수 있습니다의 값은 <xref:System.Windows.Forms.Timer.Interval%2A> 이전 절차의 7 단계에서 설정한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="99c2e-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c2e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99c2e-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="99c2e-130">방법: StatusBar 컨트롤에 패널 추가</span><span class="sxs-lookup"><span data-stu-id="99c2e-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="99c2e-131">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="99c2e-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="99c2e-132">StatusBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="99c2e-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
