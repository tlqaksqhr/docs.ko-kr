---
title: "방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출"
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
f1_keywords: EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db68fba51cd7ef9bad9ba6f7c4ba8d05a31c4371
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="ee66c-102">방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="ee66c-102">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>
<span data-ttu-id="ee66c-103">Windows Forms 응용 프로그램의 성능을 개선하기 위해 다중 스레딩을 사용하는 경우에는 스레드로부터 안전한 방식으로 컨트롤을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-103">If you use multithreading to improve the performance of your Windows Forms applications, you must make sure that you make calls to your controls in a thread-safe way.</span></span>  
  
 <span data-ttu-id="ee66c-104">Windows Forms 컨트롤에 대한 액세스는 기본적으로 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-104">Access to Windows Forms controls is not inherently thread safe.</span></span> <span data-ttu-id="ee66c-105">둘 이상의 스레드가 컨트롤 상태를 조작하는 경우 컨트롤이 불일치하는 상태로 강제 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-105">If you have two or more threads manipulating the state of a control, it is possible to force the control into an inconsistent state.</span></span> <span data-ttu-id="ee66c-106">또한 경합 상태와 교착 상태 등의 기타 스레드 관련 버그도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-106">Other thread-related bugs are possible, such as race conditions and deadlocks.</span></span> <span data-ttu-id="ee66c-107">컨트롤에 액세스할 때는 스레드로부터 안전한 방식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-107">It is important to make sure that access to your controls is performed in a thread-safe way.</span></span>  
  
 <span data-ttu-id="ee66c-108"><xref:System.Windows.Forms.Control.Invoke%2A> 메서드를 사용하지 않고 컨트롤을 만든 스레드가 아닌 다른 스레드에서 컨트롤을 호출하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-108">It is unsafe to call a control from a thread other than the one that created the control without using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span> <span data-ttu-id="ee66c-109">아래에는 스레드로부터 안전하지 않은 호출의 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-109">The following is an example of a call that is not thread safe.</span></span>  
  
```csharp  
// This event handler creates a thread that calls a   
// Windows Forms control in an unsafe way.  
private void setTextUnsafeBtn_Click(  
    object sender,   
    EventArgs e)  
{  
    this.demoThread =   
        new Thread(new ThreadStart(this.ThreadProcUnsafe));  
  
    this.demoThread.Start();  
}  
  
// This method is executed on the worker thread and makes  
// an unsafe call on the TextBox control.  
private void ThreadProcUnsafe()  
{  
    this.textBox1.Text = "This text was set unsafely.";  
}  
```  
  
```vb  
' This event handler creates a thread that calls a   
' Windows Forms control in an unsafe way.  
 Private Sub setTextUnsafeBtn_Click( _  
 ByVal sender As Object, _  
 ByVal e As EventArgs) Handles setTextUnsafeBtn.Click  
  
     Me.demoThread = New Thread( _  
     New ThreadStart(AddressOf Me.ThreadProcUnsafe))  
  
     Me.demoThread.Start()  
 End Sub  
  
' This method is executed on the worker thread and makes  
' an unsafe call on the TextBox control.  
Private Sub ThreadProcUnsafe()  
   Me.textBox1.Text = "This text was set unsafely."  
End Sub  
```  
  
```cpp  
// This event handler creates a thread that calls a  
    // Windows Forms control in an unsafe way.  
private:  
    void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)  
    {  
        this->demoThread =  
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));  
  
        this->demoThread->Start();  
    }  
  
    // This method is executed on the worker thread and makes  
    // an unsafe call on the TextBox control.  
private:  
    void ThreadProcUnsafe()  
    {  
        this->textBox1->Text = "This text was set unsafely.";  
    }  
```  
  
 <span data-ttu-id="ee66c-110">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에서는 스레드로부터 안전하지 않은 방식으로 컨트롤에 액세스하는 경우를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-110">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] helps you detect when you are accessing your controls in a manner that is not thread safe.</span></span> <span data-ttu-id="ee66c-111">디버거에서 응용 프로그램을 실행할 때 컨트롤을 만든 스레드가 아닌 다른 스레드가 해당 컨트롤을 호출하려고 하면 디버거에서 <xref:System.InvalidOperationException> 이 발생하고 " *컨트롤 이름* 컨트롤이 자신이 만들어진 스레드가 아닌 스레드에서 액세스되었습니다." 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-111">When you are running your application in the debugger, and a thread other than the one which created a control tries to call that control, the debugger raises an <xref:System.InvalidOperationException> with the message, "Control *control name* accessed from a thread other than the thread it was created on."</span></span>  
  
 <span data-ttu-id="ee66c-112">이 예외는 안전하지 않은 액세스를 안정적으로 확인할 수 있도록 디버깅 중에 발생하며 가끔 런타임에 발생하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-112">This exception occurs reliably during debugging and, under some circumstances, at run time.</span></span> <span data-ttu-id="ee66c-113">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이전 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 버전을 사용하여 작성한 응용 프로그램을 디버그할 때 이 예외가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-113">You might see this exception when you debug applications that you wrote with the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] prior to the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="ee66c-114">이 문제는 표시되는 경우 해결하는 것이 좋지만 <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> 속성을 `false`로 설정하면 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-114">You are strongly advised to fix this problem when you see it, but you can disable it by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> property to `false`.</span></span> <span data-ttu-id="ee66c-115">이렇게 하면 컨트롤이 Visual Studio.NET 2003 및 [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)]에서 실행되는 것처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-115">This causes your control to run like it would run under Visual Studio .NET 2003 and the [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee66c-116">폼에서 ActiveX 컨트롤을 사용하는 경우 디버거에서 실행 시 크로스 스레드 <xref:System.InvalidOperationException> 이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-116">If you are using ActiveX controls on a form, you may receive the cross-thread <xref:System.InvalidOperationException> when you run under the debugger.</span></span> <span data-ttu-id="ee66c-117">이 예외가 발생하면 ActiveX 컨트롤이 다중 스레딩을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-117">When this occurs, the ActiveX control does not support multithreading.</span></span> <span data-ttu-id="ee66c-118">Windows Forms에서 ActiveX 컨트롤을 사용하는 방법에 대한 자세한 내용은 [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee66c-118">For more information about using ActiveX controls with Windows Forms, see [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md).</span></span> <span data-ttu-id="ee66c-119">Visual Studio를 사용하는 경우 Visual Studio 호스팅 프로세스를 사용하지 않도록 설정하여 이 예외를 방지할 수 있습니다( [How to: Disable the Hosting Process](/visualstudio/ide/how-to-disable-the-hosting-process)참조).</span><span class="sxs-lookup"><span data-stu-id="ee66c-119">If you are using Visual Studio, you can prevent this exception by disabling the Visual Studio hosting process, see [How to: Disable the Hosting Process](/visualstudio/ide/how-to-disable-the-hosting-process).</span></span>  
  
## <a name="making-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="ee66c-120">스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="ee66c-120">Making Thread-Safe Calls to Windows Forms Controls</span></span>  
  
#### <a name="to-make-a-thread-safe-call-to-a-windows-forms-control"></a><span data-ttu-id="ee66c-121">스레드로부터 안전한 방식으로 Windows Forms 컨트롤을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="ee66c-121">To make a thread-safe call to a Windows Forms control</span></span>  
  
1.  <span data-ttu-id="ee66c-122">컨트롤의 <xref:System.Windows.Forms.Control.InvokeRequired%2A> 속성을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-122">Query the control's <xref:System.Windows.Forms.Control.InvokeRequired%2A> property.</span></span>  
  
2.  <span data-ttu-id="ee66c-123"><xref:System.Windows.Forms.Control.InvokeRequired%2A> 가 `true`를 반환하면 실제 컨트롤 호출을 수행하는 대리자를 포함하여 <xref:System.Windows.Forms.Control.Invoke%2A> 를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-123">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, call <xref:System.Windows.Forms.Control.Invoke%2A> with a delegate that makes the actual call to the control.</span></span>  
  
3.  <span data-ttu-id="ee66c-124"><xref:System.Windows.Forms.Control.InvokeRequired%2A> 가 `false`를 반환하면 컨트롤을 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-124">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, call the control directly.</span></span>  
  
 <span data-ttu-id="ee66c-125">다음 코드 예제에서는 백그라운드 스레드를 통해 실행되는 `ThreadProcSafe` 메서드에서 스레드로부터 안전한 호출이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-125">In the following code example, a thread-safe call is implemented in the `ThreadProcSafe` method, which is executed by the background thread.</span></span> <span data-ttu-id="ee66c-126"><xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.InvokeRequired%2A> 가 `true`를 반환하면 `ThreadProcSafe` 메서드는 `StringArgReturningVoidDelegate` 인스턴스를 만들어 폼의 <xref:System.Windows.Forms.Control.Invoke%2A> 메서드로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-126">If the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, the `ThreadProcSafe` method creates an instance of `StringArgReturningVoidDelegate` and passes that to the form's <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span> <span data-ttu-id="ee66c-127">이 경우 `SetText` 컨트롤을 만든 스레드에서 <xref:System.Windows.Forms.TextBox> 메서드가 호출되며 이 스레드 컨텍스트에서 <xref:System.Windows.Forms.Control.Text%2A> 속성이 직접 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-127">This causes the `SetText` method to be called on the thread that created the <xref:System.Windows.Forms.TextBox> control, and in this thread context the <xref:System.Windows.Forms.Control.Text%2A> property is set directly.</span></span>  
  
```csharp  
// This event handler creates a thread that calls a   
// Windows Forms control in a thread-safe way.  
private void setTextSafeBtn_Click(  
    object sender,   
    EventArgs e)  
{  
    this.demoThread =   
        new Thread(new ThreadStart(this.ThreadProcSafe));  
  
    this.demoThread.Start();  
}  
  
// This method is executed on the worker thread and makes  
// a thread-safe call on the TextBox control.  
private void ThreadProcSafe()  
{  
    this.SetText("This text was set safely.");  
}  
```  
  
```vb  
' This event handler creates a thread that calls a   
' Windows Forms control in a thread-safe way.  
 Private Sub setTextSafeBtn_Click( _  
 ByVal sender As Object, _  
 ByVal e As EventArgs) Handles setTextSafeBtn.Click  
  
     Me.demoThread = New Thread( _  
     New ThreadStart(AddressOf Me.ThreadProcSafe))  
  
     Me.demoThread.Start()  
 End Sub  
  
' This method is executed on the worker thread and makes  
' a thread-safe call on the TextBox control.  
Private Sub ThreadProcSafe()  
   Me.SetText("This text was set safely.")  
 End Sub  
```  
  
```cpp  
// This event handler creates a thread that calls a  
    // Windows Forms control in a thread-safe way.  
private:  
    void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)  
    {  
        this->demoThread =  
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));  
  
        this->demoThread->Start();  
    }  
  
    // This method is executed on the worker thread and makes  
    // a thread-safe call on the TextBox control.  
private:  
    void ThreadProcSafe()  
    {  
        this->SetText("This text was set safely.");  
    }  
```  
  
```csharp  
// This delegate enables asynchronous calls for setting  
// the text property on a TextBox control.  
delegate void StringArgReturningVoidDelegate(string text);  
```  
  
```vb  
' This delegate enables asynchronous calls for setting  
' the text property on a TextBox control.  
Delegate Sub StringArgReturningVoidDelegate([text] As String)  
```  
  
```cpp  
// This delegate enables asynchronous calls for setting  
// the text property on a TextBox control.  
delegate void StringArgReturningVoidDelegate(String^ text);  
```  
  
```csharp  
// This method demonstrates a pattern for making thread-safe  
// calls on a Windows Forms control.   
//  
// If the calling thread is different from the thread that  
// created the TextBox control, this method creates a  
// StringArgReturningVoidDelegate and calls itself asynchronously using the  
// Invoke method.  
//  
// If the calling thread is the same as the thread that created  
// the TextBox control, the Text property is set directly.   
  
private void SetText(string text)  
{  
    // InvokeRequired required compares the thread ID of the  
    // calling thread to the thread ID of the creating thread.  
    // If these threads are different, it returns true.  
    if (this.textBox1.InvokeRequired)  
    {     
        StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);  
        this.Invoke(d, new object[] { text });  
    }  
    else  
    {  
        this.textBox1.Text = text;  
    }  
}  
```  
  
```vb  
' This method demonstrates a pattern for making thread-safe  
' calls on a Windows Forms control.   
'  
' If the calling thread is different from the thread that  
' created the TextBox control, this method creates a  
' StringArgReturningVoidDelegate and calls itself asynchronously using the  
' Invoke method.  
'  
' If the calling thread is the same as the thread that created  
 ' the TextBox control, the Text property is set directly.  
  
 Private Sub SetText(ByVal [text] As String)  
  
     ' InvokeRequired required compares the thread ID of the  
     ' calling thread to the thread ID of the creating thread.  
     ' If these threads are different, it returns true.  
     If Me.textBox1.InvokeRequired Then  
         Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)  
         Me.Invoke(d, New Object() {[text]})  
     Else  
         Me.textBox1.Text = [text]  
     End If  
 End Sub  
```  
  
```cpp  
// This method demonstrates a pattern for making thread-safe  
    // calls on a Windows Forms control.  
    //  
    // If the calling thread is different from the thread that  
    // created the TextBox control, this method creates a  
    // StringArgReturningVoidDelegate and calls itself asynchronously using the  
    // Invoke method.  
    //  
    // If the calling thread is the same as the thread that created  
    // the TextBox control, the Text property is set directly.  
  
private:  
    void SetText(String^ text)  
    {  
        // InvokeRequired required compares the thread ID of the  
        // calling thread to the thread ID of the creating thread.  
        // If these threads are different, it returns true.  
        if (this->textBox1->InvokeRequired)  
        {  
            StringArgReturningVoidDelegate^ d =   
                gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);  
            this->Invoke(d, gcnew array<Object^> { text });  
        }  
        else  
        {  
            this->textBox1->Text = text;  
        }  
    }  
```  
  
## <a name="making-thread-safe-calls-by-using-backgroundworker"></a><span data-ttu-id="ee66c-128">BackgroundWorker를 사용하여 스레드로부터 안전한 호출 수행</span><span class="sxs-lookup"><span data-stu-id="ee66c-128">Making Thread-Safe Calls by using BackgroundWorker</span></span>  
 <span data-ttu-id="ee66c-129">응용 프로그램에서 다중 스레딩을 구현하는 기본 방법은 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-129">The preferred way to implement multithreading in your application is to use the <xref:System.ComponentModel.BackgroundWorker> component.</span></span> <span data-ttu-id="ee66c-130"><xref:System.ComponentModel.BackgroundWorker> 구성 요소는 다중 스레딩에 이벤트 구동 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-130">The <xref:System.ComponentModel.BackgroundWorker> component uses an event-driven model for multithreading.</span></span> <span data-ttu-id="ee66c-131">백그라운드 스레드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 실행하며 컨트롤을 만드는 스레드는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-131">The background thread runs your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, and the thread that creates your controls runs your <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handlers.</span></span> <span data-ttu-id="ee66c-132"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 컨트롤을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-132">You can call your controls from your <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handlers.</span></span>  
  
#### <a name="to-make-thread-safe-calls-by-using-backgroundworker"></a><span data-ttu-id="ee66c-133">BackgroundWorker를 사용하여 스레드로부터 안전한 호출을 수행하려면</span><span class="sxs-lookup"><span data-stu-id="ee66c-133">To make thread-safe calls by using BackgroundWorker</span></span>  
  
1.  <span data-ttu-id="ee66c-134">백그라운드 스레드에서 수행하려는 작업을 수행하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-134">Create a method to do the work that you want done in the background thread.</span></span> <span data-ttu-id="ee66c-135">이 메서드에서 Main 메서드가 만든 컨트롤을 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ee66c-135">Do not call controls created by the main thread in this method.</span></span>  
  
2.  <span data-ttu-id="ee66c-136">백그라운드 작업이 완료된 후 해당 작업의 결과를 보고하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-136">Create a method to report the results of your background work after it finishes.</span></span> <span data-ttu-id="ee66c-137">이 메서드에서는 Main 메서드가 만든 컨트롤을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-137">You can call controls created by the main thread in this method.</span></span>  
  
3.  <span data-ttu-id="ee66c-138">1단계에서 만든 메서드를 <xref:System.ComponentModel.BackgroundWorker.DoWork> 인스턴스의 <xref:System.ComponentModel.BackgroundWorker>이벤트에 바인딩하고 2단계에서 만든 메서드를 같은 인스턴스의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-138">Bind the method created in step 1 to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event of an instance of <xref:System.ComponentModel.BackgroundWorker>, and bind the method created in step 2 to the same instance’s <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
4.  <span data-ttu-id="ee66c-139">백그라운드 스레드를 시작하려면 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 인스턴스의 <xref:System.ComponentModel.BackgroundWorker> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-139">To start the background thread, call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of the <xref:System.ComponentModel.BackgroundWorker> instance.</span></span>  
  
 <span data-ttu-id="ee66c-140">다음 코드 예제에서 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 <xref:System.Threading.Thread.Sleep%2A> 를 사용하여 시간이 오래 걸리는 작업을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-140">In the following code example, the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler uses <xref:System.Threading.Thread.Sleep%2A> to simulate work that takes some time.</span></span> <span data-ttu-id="ee66c-141">그러나 폼의 <xref:System.Windows.Forms.TextBox> 컨트롤은 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-141">It does not call the form’s <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="ee66c-142"><xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성은 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 직접 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-142">The <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.Text%2A> property is set directly in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
```csharp  
// This BackgroundWorker is used to demonstrate the   
// preferred way of performing asynchronous operations.  
private BackgroundWorker backgroundWorker1;  
```  
  
```vb  
' This BackgroundWorker is used to demonstrate the   
' preferred way of performing asynchronous operations.  
Private WithEvents backgroundWorker1 As BackgroundWorker  
```  
  
```cpp  
// This BackgroundWorker is used to demonstrate the  
    // preferred way of performing asynchronous operations.  
private:  
    BackgroundWorker^ backgroundWorker1;  
```  
  
```csharp  
// This event handler starts the form's   
// BackgroundWorker by calling RunWorkerAsync.  
//  
// The Text property of the TextBox control is set  
// when the BackgroundWorker raises the RunWorkerCompleted  
// event.  
private void setTextBackgroundWorkerBtn_Click(  
    object sender,   
    EventArgs e)  
{  
    this.backgroundWorker1.RunWorkerAsync();  
}  
  
// This event handler sets the Text property of the TextBox  
// control. It is called on the thread that created the   
// TextBox control, so the call is thread-safe.  
//  
// BackgroundWorker is the preferred way to perform asynchronous  
// operations.  
  
private void backgroundWorker1_RunWorkerCompleted(  
    object sender,   
    RunWorkerCompletedEventArgs e)  
{  
    this.textBox1.Text =   
        "This text was set safely by BackgroundWorker.";  
}  
```  
  
```vb  
' This event handler starts the form's   
' BackgroundWorker by calling RunWorkerAsync.  
'  
' The Text property of the TextBox control is set  
' when the BackgroundWorker raises the RunWorkerCompleted  
' event.  
 Private Sub setTextBackgroundWorkerBtn_Click( _  
 ByVal sender As Object, _  
 ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click  
     Me.backgroundWorker1.RunWorkerAsync()  
 End Sub  
  
' This event handler sets the Text property of the TextBox  
' control. It is called on the thread that created the   
' TextBox control, so the call is thread-safe.  
'  
' BackgroundWorker is the preferred way to perform asynchronous  
' operations.  
 Private Sub backgroundWorker1_RunWorkerCompleted( _  
 ByVal sender As Object, _  
 ByVal e As RunWorkerCompletedEventArgs) _  
 Handles backgroundWorker1.RunWorkerCompleted  
     Me.textBox1.Text = _  
     "This text was set safely by BackgroundWorker."  
 End Sub  
```  
  
```cpp  
// This event handler starts the form's  
    // BackgroundWorker by calling RunWorkerAsync.  
    //  
    // The Text property of the TextBox control is set  
    // when the BackgroundWorker raises the RunWorkerCompleted  
    // event.  
private:  
    void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)  
    {  
        this->backgroundWorker1->RunWorkerAsync();  
    }  
  
    // This event handler sets the Text property of the TextBox  
    // control. It is called on the thread that created the  
    // TextBox control, so the call is thread-safe.  
    //  
    // BackgroundWorker is the preferred way to perform asynchronous  
    // operations.  
  
private:  
    void backgroundWorker1_RunWorkerCompleted(  
        Object^ sender,  
        RunWorkerCompletedEventArgs^ e)  
    {  
        this->textBox1->Text =  
            "This text was set safely by BackgroundWorker.";  
    }  
```  
  
 <span data-ttu-id="ee66c-143"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 사용하여 백그라운드 작업의 진행률을 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-143">You can also report the progress of a background task by using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="ee66c-144">해당 이벤트가 통합되어 있는 예제를 보려면 <xref:System.ComponentModel.BackgroundWorker>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee66c-144">For an example that incorporates that event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee66c-145">예</span><span class="sxs-lookup"><span data-stu-id="ee66c-145">Example</span></span>  
 <span data-ttu-id="ee66c-146">다음 코드 예제는 단추 세 개와 텍스트 상자 하나가 포함된 폼으로 구성되는 완전한 Windows Forms 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-146">The following code example is a complete Windows Forms application that consists of a form with three buttons and one text box.</span></span> <span data-ttu-id="ee66c-147">첫 번째 단추는 안전하지 않은 크로스 스레드 액세스를, 두 번째 단추는 <xref:System.Windows.Forms.Control.Invoke%2A>를 사용하는 안전한 액세스를, 세 번째 단추는 <xref:System.ComponentModel.BackgroundWorker>를 사용하는 안전한 액세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-147">The first button demonstrates unsafe cross-thread access, the second button demonstrates safe access by using <xref:System.Windows.Forms.Control.Invoke%2A>, and the third button demonstrates safe access by using <xref:System.ComponentModel.BackgroundWorker>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee66c-148">예제를 실행하는 방법에 대한 지침은 [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/en-us/cc447f7e-4c3b-4397-9d05-aeba3ca49416)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee66c-148">For instructions on how to run the example, see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/en-us/cc447f7e-4c3b-4397-9d05-aeba3ca49416).</span></span> <span data-ttu-id="ee66c-149">이 예제를 실행하려면 System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-149">This example requires references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
```csharp  
using System;  
using System.ComponentModel;  
using System.Threading;  
using System.Windows.Forms;  
  
namespace CrossThreadDemo  
{  
    public class Form1 : Form  
    {  
        // This delegate enables asynchronous calls for setting  
        // the text property on a TextBox control.  
        delegate void StringArgReturningVoidDelegate(string text);  
  
        // This thread is used to demonstrate both thread-safe and  
        // unsafe ways to call a Windows Forms control.  
        private Thread demoThread = null;  
  
        // This BackgroundWorker is used to demonstrate the   
        // preferred way of performing asynchronous operations.  
        private BackgroundWorker backgroundWorker1;  
  
        private TextBox textBox1;  
        private Button setTextUnsafeBtn;  
        private Button setTextSafeBtn;  
        private Button setTextBackgroundWorkerBtn;  
  
        private System.ComponentModel.IContainer components = null;  
  
        public Form1()  
        {  
            InitializeComponent();  
        }  
  
        protected override void Dispose(bool disposing)  
        {  
            if (disposing && (components != null))  
            {  
                components.Dispose();  
            }  
            base.Dispose(disposing);  
        }  
  
        // This event handler creates a thread that calls a   
        // Windows Forms control in an unsafe way.  
        private void setTextUnsafeBtn_Click(  
            object sender,   
            EventArgs e)  
        {  
            this.demoThread =   
                new Thread(new ThreadStart(this.ThreadProcUnsafe));  
  
            this.demoThread.Start();  
        }  
  
        // This method is executed on the worker thread and makes  
        // an unsafe call on the TextBox control.  
        private void ThreadProcUnsafe()  
        {  
            this.textBox1.Text = "This text was set unsafely.";  
        }  
  
        // This event handler creates a thread that calls a   
        // Windows Forms control in a thread-safe way.  
        private void setTextSafeBtn_Click(  
            object sender,   
            EventArgs e)  
        {  
            this.demoThread =   
                new Thread(new ThreadStart(this.ThreadProcSafe));  
  
            this.demoThread.Start();  
        }  
  
        // This method is executed on the worker thread and makes  
        // a thread-safe call on the TextBox control.  
        private void ThreadProcSafe()  
        {  
            this.SetText("This text was set safely.");  
        }  
  
        // This method demonstrates a pattern for making thread-safe  
        // calls on a Windows Forms control.   
        //  
        // If the calling thread is different from the thread that  
        // created the TextBox control, this method creates a  
        // StringArgReturningVoidDelegate and calls itself asynchronously using the  
        // Invoke method.  
        //  
        // If the calling thread is the same as the thread that created  
        // the TextBox control, the Text property is set directly.   
  
        private void SetText(string text)  
        {  
            // InvokeRequired required compares the thread ID of the  
            // calling thread to the thread ID of the creating thread.  
            // If these threads are different, it returns true.  
            if (this.textBox1.InvokeRequired)  
            {     
                StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);  
                this.Invoke(d, new object[] { text });  
            }  
            else  
            {  
                this.textBox1.Text = text;  
            }  
        }  
  
        // This event handler starts the form's   
        // BackgroundWorker by calling RunWorkerAsync.  
        //  
        // The Text property of the TextBox control is set  
        // when the BackgroundWorker raises the RunWorkerCompleted  
        // event.  
        private void setTextBackgroundWorkerBtn_Click(  
            object sender,   
            EventArgs e)  
        {  
            this.backgroundWorker1.RunWorkerAsync();  
        }  
  
        // This event handler sets the Text property of the TextBox  
        // control. It is called on the thread that created the   
        // TextBox control, so the call is thread-safe.  
        //  
        // BackgroundWorker is the preferred way to perform asynchronous  
        // operations.  
  
        private void backgroundWorker1_RunWorkerCompleted(  
            object sender,   
            RunWorkerCompletedEventArgs e)  
        {  
            this.textBox1.Text =   
                "This text was set safely by BackgroundWorker.";  
        }  
  
        #region Windows Form Designer generated code  
  
        private void InitializeComponent()  
        {  
            this.textBox1 = new System.Windows.Forms.TextBox();  
            this.setTextUnsafeBtn = new System.Windows.Forms.Button();  
            this.setTextSafeBtn = new System.Windows.Forms.Button();  
            this.setTextBackgroundWorkerBtn = new System.Windows.Forms.Button();  
            this.backgroundWorker1 = new System.ComponentModel.BackgroundWorker();  
            this.SuspendLayout();  
            //   
            // textBox1  
            //   
            this.textBox1.Location = new System.Drawing.Point(12, 12);  
            this.textBox1.Name = "textBox1";  
            this.textBox1.Size = new System.Drawing.Size(240, 20);  
            this.textBox1.TabIndex = 0;  
            //   
            // setTextUnsafeBtn  
            //   
            this.setTextUnsafeBtn.Location = new System.Drawing.Point(15, 55);  
            this.setTextUnsafeBtn.Name = "setTextUnsafeBtn";  
            this.setTextUnsafeBtn.TabIndex = 1;  
            this.setTextUnsafeBtn.Text = "Unsafe Call";  
            this.setTextUnsafeBtn.Click += new System.EventHandler(this.setTextUnsafeBtn_Click);  
            //   
            // setTextSafeBtn  
            //   
            this.setTextSafeBtn.Location = new System.Drawing.Point(96, 55);  
            this.setTextSafeBtn.Name = "setTextSafeBtn";  
            this.setTextSafeBtn.TabIndex = 2;  
            this.setTextSafeBtn.Text = "Safe Call";  
            this.setTextSafeBtn.Click += new System.EventHandler(this.setTextSafeBtn_Click);  
            //   
            // setTextBackgroundWorkerBtn  
            //   
            this.setTextBackgroundWorkerBtn.Location = new System.Drawing.Point(177, 55);  
            this.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn";  
            this.setTextBackgroundWorkerBtn.TabIndex = 3;  
            this.setTextBackgroundWorkerBtn.Text = "Safe BW Call";  
            this.setTextBackgroundWorkerBtn.Click += new System.EventHandler(this.setTextBackgroundWorkerBtn_Click);  
            //   
            // backgroundWorker1  
            //   
            this.backgroundWorker1.RunWorkerCompleted += new System.ComponentModel.RunWorkerCompletedEventHandler(this.backgroundWorker1_RunWorkerCompleted);  
            //   
            // Form1  
            //   
            this.ClientSize = new System.Drawing.Size(268, 96);  
            this.Controls.Add(this.setTextBackgroundWorkerBtn);  
            this.Controls.Add(this.setTextSafeBtn);  
            this.Controls.Add(this.setTextUnsafeBtn);  
            this.Controls.Add(this.textBox1);  
            this.Name = "Form1";  
            this.Text = "Form1";  
            this.ResumeLayout(false);  
            this.PerformLayout();  
  
        }  
  
        #endregion  
  
        [STAThread]  
        static void Main()  
        {  
            Application.EnableVisualStyles();  
            Application.Run(new Form1());  
        }  
  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.ComponentModel  
Imports System.Threading  
Imports System.Windows.Forms  
  
Public Class Form1  
   Inherits Form  
  
   ' This delegate enables asynchronous calls for setting  
   ' the text property on a TextBox control.  
   Delegate Sub StringArgReturningVoidDelegate([text] As String)  
  
   ' This thread is used to demonstrate both thread-safe and  
   ' unsafe ways to call a Windows Forms control.  
   Private demoThread As Thread = Nothing  
  
   ' This BackgroundWorker is used to demonstrate the   
   ' preferred way of performing asynchronous operations.  
   Private WithEvents backgroundWorker1 As BackgroundWorker  
  
   Private textBox1 As TextBox  
   Private WithEvents setTextUnsafeBtn As Button  
   Private WithEvents setTextSafeBtn As Button  
   Private WithEvents setTextBackgroundWorkerBtn As Button  
  
   Private components As System.ComponentModel.IContainer = Nothing  
  
   Public Sub New()  
      InitializeComponent()  
    End Sub  
  
   Protected Overrides Sub Dispose(disposing As Boolean)  
      If disposing AndAlso (components IsNot Nothing) Then  
         components.Dispose()  
      End If  
      MyBase.Dispose(disposing)  
    End Sub  
  
   ' This event handler creates a thread that calls a   
   ' Windows Forms control in an unsafe way.  
    Private Sub setTextUnsafeBtn_Click( _  
    ByVal sender As Object, _  
    ByVal e As EventArgs) Handles setTextUnsafeBtn.Click  
  
        Me.demoThread = New Thread( _  
        New ThreadStart(AddressOf Me.ThreadProcUnsafe))  
  
        Me.demoThread.Start()  
    End Sub  
  
   ' This method is executed on the worker thread and makes  
   ' an unsafe call on the TextBox control.  
   Private Sub ThreadProcUnsafe()  
      Me.textBox1.Text = "This text was set unsafely."  
   End Sub   
  
   ' This event handler creates a thread that calls a   
   ' Windows Forms control in a thread-safe way.  
    Private Sub setTextSafeBtn_Click( _  
    ByVal sender As Object, _  
    ByVal e As EventArgs) Handles setTextSafeBtn.Click  
  
        Me.demoThread = New Thread( _  
        New ThreadStart(AddressOf Me.ThreadProcSafe))  
  
        Me.demoThread.Start()  
    End Sub  
  
   ' This method is executed on the worker thread and makes  
   ' a thread-safe call on the TextBox control.  
   Private Sub ThreadProcSafe()  
      Me.SetText("This text was set safely.")  
    End Sub  
  
   ' This method demonstrates a pattern for making thread-safe  
   ' calls on a Windows Forms control.   
   '  
   ' If the calling thread is different from the thread that  
   ' created the TextBox control, this method creates a  
   ' StringArgReturningVoidDelegate and calls itself asynchronously using the  
   ' Invoke method.  
   '  
   ' If the calling thread is the same as the thread that created  
    ' the TextBox control, the Text property is set directly.   
  
    Private Sub SetText(ByVal [text] As String)  
  
        ' InvokeRequired required compares the thread ID of the  
        ' calling thread to the thread ID of the creating thread.  
        ' If these threads are different, it returns true.  
        If Me.textBox1.InvokeRequired Then  
            Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)  
            Me.Invoke(d, New Object() {[text]})  
        Else  
            Me.textBox1.Text = [text]  
        End If  
    End Sub  
  
   ' This event handler starts the form's   
   ' BackgroundWorker by calling RunWorkerAsync.  
   '  
   ' The Text property of the TextBox control is set  
   ' when the BackgroundWorker raises the RunWorkerCompleted  
   ' event.  
    Private Sub setTextBackgroundWorkerBtn_Click( _  
    ByVal sender As Object, _  
    ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click  
        Me.backgroundWorker1.RunWorkerAsync()  
    End Sub  
  
   ' This event handler sets the Text property of the TextBox  
   ' control. It is called on the thread that created the   
   ' TextBox control, so the call is thread-safe.  
   '  
   ' BackgroundWorker is the preferred way to perform asynchronous  
   ' operations.  
    Private Sub backgroundWorker1_RunWorkerCompleted( _  
    ByVal sender As Object, _  
    ByVal e As RunWorkerCompletedEventArgs) _  
    Handles backgroundWorker1.RunWorkerCompleted  
        Me.textBox1.Text = _  
        "This text was set safely by BackgroundWorker."  
    End Sub  
  
   #Region "Windows Form Designer generated code"  
  
   Private Sub InitializeComponent()  
      Me.textBox1 = New System.Windows.Forms.TextBox()  
      Me.setTextUnsafeBtn = New System.Windows.Forms.Button()  
      Me.setTextSafeBtn = New System.Windows.Forms.Button()  
      Me.setTextBackgroundWorkerBtn = New System.Windows.Forms.Button()  
      Me.backgroundWorker1 = New System.ComponentModel.BackgroundWorker()  
      Me.SuspendLayout()  
      '   
      ' textBox1  
      '   
      Me.textBox1.Location = New System.Drawing.Point(12, 12)  
      Me.textBox1.Name = "textBox1"  
      Me.textBox1.Size = New System.Drawing.Size(240, 20)  
      Me.textBox1.TabIndex = 0  
      '   
      ' setTextUnsafeBtn  
      '   
      Me.setTextUnsafeBtn.Location = New System.Drawing.Point(15, 55)  
      Me.setTextUnsafeBtn.Name = "setTextUnsafeBtn"  
      Me.setTextUnsafeBtn.TabIndex = 1  
      Me.setTextUnsafeBtn.Text = "Unsafe Call"  
      '   
      ' setTextSafeBtn  
      '   
      Me.setTextSafeBtn.Location = New System.Drawing.Point(96, 55)  
      Me.setTextSafeBtn.Name = "setTextSafeBtn"  
      Me.setTextSafeBtn.TabIndex = 2  
      Me.setTextSafeBtn.Text = "Safe Call"  
      '   
      ' setTextBackgroundWorkerBtn  
      '   
      Me.setTextBackgroundWorkerBtn.Location = New System.Drawing.Point(177, 55)  
      Me.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn"  
      Me.setTextBackgroundWorkerBtn.TabIndex = 3  
      Me.setTextBackgroundWorkerBtn.Text = "Safe BW Call"  
      '   
      ' backgroundWorker1  
      '   
      '   
      ' Form1  
      '   
      Me.ClientSize = New System.Drawing.Size(268, 96)  
      Me.Controls.Add(setTextBackgroundWorkerBtn)  
      Me.Controls.Add(setTextSafeBtn)  
      Me.Controls.Add(setTextUnsafeBtn)  
      Me.Controls.Add(textBox1)  
      Me.Name = "Form1"  
      Me.Text = "Form1"  
      Me.ResumeLayout(False)  
      Me.PerformLayout()  
   End Sub 'InitializeComponent   
  
   #End Region  
  
   <STAThread()>  _  
   Shared Sub Main()  
      Application.EnableVisualStyles()  
      Application.Run(New Form1())  
    End Sub  
End Class  
```  
  
```cpp  
#using <System.dll>  
#using <System.Windows.Forms.dll>  
#using <System.Drawing.dll>  
  
using namespace System;  
using namespace System::ComponentModel;  
using namespace System::Threading;  
using namespace System::Windows::Forms;  
  
namespace CrossThreadDemo  
{  
    public ref class Form1 : public Form  
    {  
        // This delegate enables asynchronous calls for setting  
        // the text property on a TextBox control.  
        delegate void StringArgReturningVoidDelegate(String^ text);  
  
        // This thread is used to demonstrate both thread-safe and  
        // unsafe ways to call a Windows Forms control.  
    private:  
        Thread^ demoThread;  
  
        // This BackgroundWorker is used to demonstrate the  
        // preferred way of performing asynchronous operations.  
    private:  
        BackgroundWorker^ backgroundWorker1;  
  
    private:  
        TextBox^ textBox1;  
    private:  
        Button^ setTextUnsafeBtn;  
    private:  
        Button^ setTextSafeBtn;  
    private:  
        Button^ setTextBackgroundWorkerBtn;  
  
    private:  
        System::ComponentModel::IContainer^ components;  
  
    public:  
        Form1()  
        {  
            components = nullptr;  
            InitializeComponent();  
        }  
  
    protected:  
        ~Form1()  
        {  
            if (components != nullptr)  
            {  
                delete components;  
            }  
        }  
  
        // This event handler creates a thread that calls a  
        // Windows Forms control in an unsafe way.  
    private:  
        void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)  
        {  
            this->demoThread =  
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));  
  
            this->demoThread->Start();  
        }  
  
        // This method is executed on the worker thread and makes  
        // an unsafe call on the TextBox control.  
    private:  
        void ThreadProcUnsafe()  
        {  
            this->textBox1->Text = "This text was set unsafely.";  
        }  
  
        // This event handler creates a thread that calls a  
        // Windows Forms control in a thread-safe way.  
    private:  
        void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)  
        {  
            this->demoThread =  
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));  
  
            this->demoThread->Start();  
        }  
  
        // This method is executed on the worker thread and makes  
        // a thread-safe call on the TextBox control.  
    private:  
        void ThreadProcSafe()  
        {  
            this->SetText("This text was set safely.");  
        }  
  
        // This method demonstrates a pattern for making thread-safe  
        // calls on a Windows Forms control.  
        //  
        // If the calling thread is different from the thread that  
        // created the TextBox control, this method creates a  
        // StringArgReturningVoidDelegate and calls itself asynchronously using the  
        // Invoke method.  
        //  
        // If the calling thread is the same as the thread that created  
        // the TextBox control, the Text property is set directly.  
  
    private:  
        void SetText(String^ text)  
        {  
            // InvokeRequired required compares the thread ID of the  
            // calling thread to the thread ID of the creating thread.  
            // If these threads are different, it returns true.  
            if (this->textBox1->InvokeRequired)  
            {  
                StringArgReturningVoidDelegate^ d =   
                    gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);  
                this->Invoke(d, gcnew array<Object^> { text });  
            }  
            else  
            {  
                this->textBox1->Text = text;  
            }  
        }  
  
        // This event handler starts the form's  
        // BackgroundWorker by calling RunWorkerAsync.  
        //  
        // The Text property of the TextBox control is set  
        // when the BackgroundWorker raises the RunWorkerCompleted  
        // event.  
    private:  
        void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)  
        {  
            this->backgroundWorker1->RunWorkerAsync();  
        }  
  
        // This event handler sets the Text property of the TextBox  
        // control. It is called on the thread that created the  
        // TextBox control, so the call is thread-safe.  
        //  
        // BackgroundWorker is the preferred way to perform asynchronous  
        // operations.  
  
    private:  
        void backgroundWorker1_RunWorkerCompleted(  
            Object^ sender,  
            RunWorkerCompletedEventArgs^ e)  
        {  
            this->textBox1->Text =  
                "This text was set safely by BackgroundWorker.";  
        }  
  
        #pragma region Windows Form Designer generated code  
  
    private:  
        void InitializeComponent()  
        {  
            this->textBox1 = gcnew System::Windows::Forms::TextBox();  
            this->setTextUnsafeBtn = gcnew System::Windows::Forms::Button();  
            this->setTextSafeBtn = gcnew System::Windows::Forms::Button();  
            this->setTextBackgroundWorkerBtn =   
                gcnew System::Windows::Forms::Button();  
            this->backgroundWorker1 =   
                gcnew System::ComponentModel::BackgroundWorker();  
            this->SuspendLayout();  
            //  
            // textBox1  
            //  
            this->textBox1->Location = System::Drawing::Point(12, 12);  
            this->textBox1->Name = "textBox1";  
            this->textBox1->Size = System::Drawing::Size(240, 20);  
            this->textBox1->TabIndex = 0;  
            //  
            // setTextUnsafeBtn  
            //  
            this->setTextUnsafeBtn->Location = System::Drawing::Point(15, 55);  
            this->setTextUnsafeBtn->Name = "setTextUnsafeBtn";  
            this->setTextUnsafeBtn->TabIndex = 1;  
            this->setTextUnsafeBtn->Text = "Unsafe Call";  
            this->setTextUnsafeBtn->Click +=   
                gcnew System::EventHandler(  
                this,&Form1::setTextUnsafeBtn_Click);  
            //  
            // setTextSafeBtn  
            //  
            this->setTextSafeBtn->Location = System::Drawing::Point(96, 55);  
            this->setTextSafeBtn->Name = "setTextSafeBtn";  
            this->setTextSafeBtn->TabIndex = 2;  
            this->setTextSafeBtn->Text = "Safe Call";  
            this->setTextSafeBtn->Click +=   
                gcnew System::EventHandler(this,&Form1::setTextSafeBtn_Click);  
            //  
            // setTextBackgroundWorkerBtn  
            //  
            this->setTextBackgroundWorkerBtn->Location =   
                System::Drawing::Point(177, 55);  
            this->setTextBackgroundWorkerBtn->Name =   
                "setTextBackgroundWorkerBtn";  
            this->setTextBackgroundWorkerBtn->TabIndex = 3;  
            this->setTextBackgroundWorkerBtn->Text = "Safe BW Call";  
            this->setTextBackgroundWorkerBtn->Click +=   
                gcnew System::EventHandler(  
                this,&Form1::setTextBackgroundWorkerBtn_Click);  
            //  
            // backgroundWorker1  
            //  
            this->backgroundWorker1->RunWorkerCompleted +=   
                gcnew System::ComponentModel::RunWorkerCompletedEventHandler(  
                this,&Form1::backgroundWorker1_RunWorkerCompleted);  
            //  
            // Form1  
            //  
            this->ClientSize = System::Drawing::Size(268, 96);  
            this->Controls->Add(this->setTextBackgroundWorkerBtn);  
            this->Controls->Add(this->setTextSafeBtn);  
            this->Controls->Add(this->setTextUnsafeBtn);  
            this->Controls->Add(this->textBox1);  
            this->Name = "Form1";  
            this->Text = "Form1";  
            this->ResumeLayout(false);  
            this->PerformLayout();  
  
        }  
  
        #pragma endregion  
    };  
}  
  
[STAThread]  
int main()  
{  
    Application::EnableVisualStyles();  
    Application::Run(gcnew CrossThreadDemo::Form1());  
}  
```  
  
 <span data-ttu-id="ee66c-150">응용 프로그램을 실행하고 **Unsafe Call** 단추를 클릭하는 즉시 텍스트 상자에 "Written by the main thread"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-150">When you run the application and click the **Unsafe Call** button, you immediately see "Written by the main thread" in the text box.</span></span> <span data-ttu-id="ee66c-151">그리고 2초 후에 안전하지 않은 호출을 시도하면 Visual Studio 디버거에 예외가 발생했음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-151">Two seconds later, when the unsafe call is attempted, the Visual Studio debugger indicates that an exception occurred.</span></span> <span data-ttu-id="ee66c-152">그러면 디버거가 텍스트 상자에 직접 쓰기를 시도한 백그라운드 스레드의 줄에서 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-152">The debugger stops at the line in the background thread that attempted to write directly to the text box.</span></span> <span data-ttu-id="ee66c-153">나머지 두 단추를 테스트하려면 응용 프로그램을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-153">You will have to restart the application to test the other two buttons.</span></span> <span data-ttu-id="ee66c-154">**Safe Call** 단추를 클릭하면 텍스트 상자에 "Written by the main thread"가 표시되고,</span><span class="sxs-lookup"><span data-stu-id="ee66c-154">When you click the **Safe Call** button, "Written by the main thread" appears in the text box.</span></span> <span data-ttu-id="ee66c-155">2초 후에 텍스트 상자는 <xref:System.Windows.Forms.Control.Invoke%2A> 메서드가 호출되었음을 나타내는 "Written by the background thread (Invoke)"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-155">Two seconds later, the text box is set to "Written by the background thread (Invoke)", which indicates that the <xref:System.Windows.Forms.Control.Invoke%2A> method was called.</span></span> <span data-ttu-id="ee66c-156">**Safe BW Call** 단추를 클릭하면 텍스트 상자에 "Written by the main thread"가 표시되고,</span><span class="sxs-lookup"><span data-stu-id="ee66c-156">When you click the **Safe BW Call** button, "Written by the main thread" appears in the text box.</span></span> <span data-ttu-id="ee66c-157">2초 후에 텍스트 상자는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 의 <xref:System.ComponentModel.BackgroundWorker> 이벤트에 대한 처리기가 호출되었음을 나타내는 "Written by the main thread after the background thread completed"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-157">Two seconds later, the text box is set to "Written by the main thread after the background thread completed", which indicates that the handler for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event of <xref:System.ComponentModel.BackgroundWorker> was called.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ee66c-158">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ee66c-158">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ee66c-159">모든 종류의 다중 스레딩을 사용할 때는 코드에서 매우 심각하고 복잡한 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee66c-159">When you use multithreading of any sort, your code can be exposed to very serious and complex bugs.</span></span> <span data-ttu-id="ee66c-160">자세한 내용은 다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩 모범 사례](../../../../docs/standard/threading/managed-threading-best-practices.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee66c-160">For more information, see [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before you implement any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee66c-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee66c-161">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="ee66c-162">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="ee66c-162">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="ee66c-163">방법: 배경 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="ee66c-163">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="ee66c-164">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="ee66c-164">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="ee66c-165">Windows Forms 및 관리되지 않는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ee66c-165">Windows Forms and Unmanaged Applications</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
