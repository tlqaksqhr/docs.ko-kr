---
title: '방법: Windows Forms Timer 구성 요소를 사용하여 설정된 간격마다 프로시저 실행'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b0b25f2ea86e58b7fe644f84412d1923fa761b82
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="c6a8e-102">방법: Windows Forms Timer 구성 요소를 사용하여 설정된 간격마다 프로시저 실행</span><span class="sxs-lookup"><span data-stu-id="c6a8e-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="c6a8e-103">루프가 완료될 때까지 특정 시간 간격으로 실행되거나 설정된 시간 간격이 경과할 때 실행되는 프로시저를 만들려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="c6a8e-104"><xref:System.Windows.Forms.Timer> 구성 요소는 이러한 프로시저를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="c6a8e-105">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="c6a8e-106">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6a8e-107"><xref:System.Windows.Forms.Timer> 구성 요소를 사용하는 경우 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="c6a8e-108">자세한 내용은 참조 [Windows Forms Timer 구성 요소의 Interval 속성 제한 사항](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md).</span></span>  
  
### <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="c6a8e-109">Timer 구성 요소를 사용하여 설정된 간격마다 프로시저를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c6a8e-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1.  <span data-ttu-id="c6a8e-110">폼에 <xref:System.Windows.Forms.Timer>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="c6a8e-111">이 작업을 프로그래밍 방식으로 수행하는 방법은 다음 예제 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="c6a8e-112">Visual Studio에는 구성 요소를 폼에 추가 하는 것에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="c6a8e-113">또한 참조 [하는 방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가](http://msdn.microsoft.com/library/becyw7bz\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](http://msdn.microsoft.com/library/becyw7bz\(v=vs.110\)).</span></span>  
  
2.  <span data-ttu-id="c6a8e-114">타이머에 대한 <xref:System.Windows.Forms.Timer.Interval%2A> 속성(밀리초)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="c6a8e-115">이 속성은 프로시저가 다시 실행되기까지 남은 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6a8e-116">타이머 이벤트가 자주 발생할수록 이벤트에 응답하는 데 더 많은 프로세서 시간이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="c6a8e-117">이 경우 전반적인 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-117">This can slow down overall performance.</span></span> <span data-ttu-id="c6a8e-118">필요 이상으로 작은 간격을 설정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-118">Do not set a smaller interval than you need.</span></span>  
  
3.  <span data-ttu-id="c6a8e-119"><xref:System.Windows.Forms.Timer.Tick> 이벤트 처리기에서 적절한 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="c6a8e-120">이 이벤트에서 작성하는 코드는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에 지정된 간격마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4.  <span data-ttu-id="c6a8e-121"><xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `true`로 설정하여 타이머를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="c6a8e-122"><xref:System.Windows.Forms.Timer.Tick> 이벤트 발생이 시작되고 설정된 간격마다 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5.  <span data-ttu-id="c6a8e-123">적절한 시간에 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `false`로 설정하여 프로시저가 다시 실행되지 않도록 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="c6a8e-124">간격을 설정 `0` 타이머가 중지를 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6a8e-125">예제</span><span class="sxs-lookup"><span data-stu-id="c6a8e-125">Example</span></span>  
 <span data-ttu-id="c6a8e-126">이 첫 번째 코드 예제에서는 1초 증분으로 시간을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="c6a8e-127">폼의 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> 및 <xref:System.Windows.Forms.Timer> 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="c6a8e-128"><xref:System.Windows.Forms.Timer.Interval%2A> 속성은 1000(1초와 같음)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="c6a8e-129"><xref:System.Windows.Forms.Timer.Tick> 이벤트에서 레이블의 캡션은 현재 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="c6a8e-130">단추를 클릭하면 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성이 `false`로 설정되어 타이머가 레이블 캡션 업데이트를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="c6a8e-131">다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.Button> 라는 컨트롤 `Button1`, <xref:System.Windows.Forms.Timer> 라는 컨트롤 `Timer1`, 및 <xref:System.Windows.Forms.Label> 라는 컨트롤 `Label1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="c6a8e-132">예제</span><span class="sxs-lookup"><span data-stu-id="c6a8e-132">Example</span></span>  
 <span data-ttu-id="c6a8e-133">이 두 번째 코드 예제는 루프가 완료될 때까지 600밀리초마다 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="c6a8e-134">다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.Button> 라는 컨트롤 `Button1`, <xref:System.Windows.Forms.Timer> 라는 컨트롤 `Timer1`, 및 <xref:System.Windows.Forms.Label> 라는 컨트롤 `Label1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a8e-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6a8e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6a8e-135">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="c6a8e-136">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c6a8e-136">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="c6a8e-137">Timer 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="c6a8e-137">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
