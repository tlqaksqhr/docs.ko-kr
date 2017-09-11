---
title: "Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bd7e462b-583b-4395-9c36-45aa9e61072c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 87f089a6de77dc5d4085b12f68b0511ec22b3f63
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="asynchronous-programming-with-async-and-await-visual-basic"></a><span data-ttu-id="fb353-102">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-102">Asynchronous Programming with Async and Await (Visual Basic)</span></span>
<span data-ttu-id="fb353-103">비동기 프로그래밍을 사용하여 성능 병목 현상을 방지하고 응용 프로그램의 전체적인 응답성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-103">You can avoid performance bottlenecks and enhance the overall responsiveness of your application by using asynchronous programming.</span></span> <span data-ttu-id="fb353-104">그러나 비동기 응용 프로그램을 쓰는 일반적인 기술이 복잡하여 해당 응용 프로그램을 쓰고, 디버깅하고, 유지 관리하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-104">However, traditional techniques for writing asynchronous applications can be complicated, making them difficult to write, debug, and maintain.</span></span>  
  
 <span data-ttu-id="fb353-105">Visual Studio 2012에는 Windows 런타임 뿐 아니라 .NET Framework 4.5 이상의 비동기 지원을 활용하는 간단한 비동기 프로그래밍 접근 방법이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-105">Visual Studio 2012 introduced a simplified approach, async programming, that leverages asynchronous support in the .NET Framework 4.5 and higher as well as  in the Windows Runtime.</span></span> <span data-ttu-id="fb353-106">컴파일러는 개발자가 하던 어려운 작업을 수행하고, 응용 프로그램은 동기 코드와 비슷한 논리 구조를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-106">The compiler does the difficult work that the developer used to do, and your application retains a logical structure that resembles synchronous code.</span></span> <span data-ttu-id="fb353-107">따라서 약간의 노력만으로도 비동기 프로그래밍의 모든 장점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-107">As a result, you get all the advantages of asynchronous programming with a fraction of the effort.</span></span>  
  
 <span data-ttu-id="fb353-108">이 항목에서는 비동기 프로그래밍을 사용하는 시기 및 방법에 대한 개요를 제공하고 특정 세부 정보 및 예제가 포함된 지원 항목에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-108">This topic provides an overview of when and how to use async programming and includes links to support topics that contain details and examples.</span></span>  
  
##  <span data-ttu-id="fb353-109"><a name="BKMK_WhentoUseAsynchrony"></a> 반응성을 향상시키는 Async</span><span class="sxs-lookup"><span data-stu-id="fb353-109"><a name="BKMK_WhentoUseAsynchrony"></a> Async Improves Responsiveness</span></span>  
 <span data-ttu-id="fb353-110">비동기는 응용 프로그램이 웹에 액세스하는 경우와 같이 차단 가능성이 있는 작업에 반드시 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-110">Asynchrony is essential for activities that are potentially blocking, such as when your application accesses the web.</span></span> <span data-ttu-id="fb353-111">웹 리소스에 대한 액세스 속도가 느리거나 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-111">Access to a web resource sometimes is slow or delayed.</span></span> <span data-ttu-id="fb353-112">동기 프로세스 안에서 이러한 활동이 차단되면 전체 응용 프로그램이 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-112">If such an activity is blocked within a synchronous process, the entire application must wait.</span></span> <span data-ttu-id="fb353-113">비동기 프로세스에서 응용 프로그램은 잠재적인 차단 작업이 완료될 때까지 웹 리소스에 의존하지 않는 다른 작업을 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-113">In an asynchronous process, the application can continue with other work that doesn't depend on the web resource until the potentially blocking task finishes.</span></span>  
  
 <span data-ttu-id="fb353-114">다음 표에는 비동기 프로그래밍으로 응답성이 향상되는 일반적인 영역이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-114">The following table shows typical areas where asynchronous programming improves responsiveness.</span></span> <span data-ttu-id="fb353-115">.NET Framework 4.5 및 Windows 런타임에서 나열된 API에는 비동기 프로그래밍을 지원하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-115">The listed APIs from the  .NET Framework 4.5 and the Windows Runtime contain methods that support async programming.</span></span>  
  
|<span data-ttu-id="fb353-116">응용 프로그램 영역</span><span class="sxs-lookup"><span data-stu-id="fb353-116">Application area</span></span>|<span data-ttu-id="fb353-117">비동기 메서드를 포함하는 API 지원</span><span class="sxs-lookup"><span data-stu-id="fb353-117">Supporting APIs that contain async methods</span></span>|  
|----------------------|------------------------------------------------|  
|<span data-ttu-id="fb353-118">웹 액세스</span><span class="sxs-lookup"><span data-stu-id="fb353-118">Web access</span></span>|<span data-ttu-id="fb353-119"><xref:System.Net.Http.HttpClient>, [SyndicationClient](http://go.microsoft.com/fwlink/p/?LinkId=259441)</span><span class="sxs-lookup"><span data-stu-id="fb353-119"><xref:System.Net.Http.HttpClient>, [SyndicationClient](http://go.microsoft.com/fwlink/p/?LinkId=259441)</span></span>|  
|<span data-ttu-id="fb353-120">파일 작업</span><span class="sxs-lookup"><span data-stu-id="fb353-120">Working with files</span></span>|<span data-ttu-id="fb353-121">[StorageFile](http://go.microsoft.com/fwlink/p/?LinkId=248220), <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="fb353-121">[StorageFile](http://go.microsoft.com/fwlink/p/?LinkId=248220), <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span></span>|  
|<span data-ttu-id="fb353-122">이미지 작업</span><span class="sxs-lookup"><span data-stu-id="fb353-122">Working with images</span></span>|<span data-ttu-id="fb353-123">[MediaCapture](http://go.microsoft.com/fwlink/p/?LinkId=261839), [BitmapEncoder](http://go.microsoft.com/fwlink/p/?LinkId=261840), [BitmapDecoder](http://go.microsoft.com/fwlink/p/?LinkId=261841)</span><span class="sxs-lookup"><span data-stu-id="fb353-123">[MediaCapture](http://go.microsoft.com/fwlink/p/?LinkId=261839), [BitmapEncoder](http://go.microsoft.com/fwlink/p/?LinkId=261840), [BitmapDecoder](http://go.microsoft.com/fwlink/p/?LinkId=261841)</span></span>|  
|<span data-ttu-id="fb353-124">WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fb353-124">WCF programming</span></span>|[<span data-ttu-id="fb353-125">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="fb353-125">Synchronous and Asynchronous Operations</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=192382)|  
|||  
  
 <span data-ttu-id="fb353-126">모든 UI 관련 작업이 대체로 스레드 한 개를 공유하므로 비동기는 특히 UI 스레드에 액세스하는 응용 프로그램의 변수를 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-126">Asynchrony proves especially valuable for applications that access the UI thread because all UI-related activity usually shares one thread.</span></span> <span data-ttu-id="fb353-127">동기 응용 프로그램에서 임의의 프로세스가 차단되면 모든 프로세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-127">If any process is blocked in a synchronous application, all are blocked.</span></span> <span data-ttu-id="fb353-128">응용 프로그램이 응답을 중지하면 기다리지 않고 응용 프로그램이 실패한 것으로 결론을 내릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-128">Your application stops responding, and you might conclude that it has failed when instead it's just waiting.</span></span>  
  
 <span data-ttu-id="fb353-129">비동기 메서드를 사용하면 응용 프로그램이 UI에 계속 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-129">When you use asynchronous methods, the application continues to respond to the UI.</span></span> <span data-ttu-id="fb353-130">예를 들어 창의 크기를 조정하거나 최소화할 수 있습니다. 또는 응용 프로그램이 완료될 때까지 기다리지 않으려면 응용 프로그램을 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-130">You can resize or minimize a window, for example, or you can close the application if you don't want to wait for it to finish.</span></span>  
  
 <span data-ttu-id="fb353-131">비동기 기반 접근 방식을 사용하면 비동기 작업을 디자인할 때 선택할 수 있는 옵션 목록에 자동 전송과 동일한 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-131">The async-based approach adds the equivalent of an automatic transmission to the list of options that you can choose from when designing asynchronous operations.</span></span> <span data-ttu-id="fb353-132">즉, 기존 비동기 프로그래밍의 이점을 모두 활용할 수 있지만 개발자의 활동이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-132">That is, you get all the benefits of traditional asynchronous programming but with much less effort from the developer.</span></span>  
  
##  <span data-ttu-id="fb353-133"><a name="BKMK_HowtoWriteanAsyncMethod"></a> 작성이 간편한 Async 메서드</span><span class="sxs-lookup"><span data-stu-id="fb353-133"><a name="BKMK_HowtoWriteanAsyncMethod"></a> Async Methods Are Easier to Write</span></span>  
 <span data-ttu-id="fb353-134">Visual Basic의 [Async](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await](../../../../visual-basic/language-reference/modifiers/async.md) 키워드는 비동기 프로그래밍의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-134">The [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await](../../../../visual-basic/language-reference/modifiers/async.md) keywords in Visual Basic are the heart of async programming.</span></span> <span data-ttu-id="fb353-135">이 키워드 두 개를 사용하면 .NET Framework 또는 Windows 런타임의 리소스를 사용하여 동기 메서드를 만드는 것만큼 쉽게 비동기 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-135">By using those two keywords, you can use resources in the .NET Framework or the Windows Runtime to create an asynchronous method almost as easily as you create a synchronous method.</span></span> <span data-ttu-id="fb353-136">`Async` 및 `Await`를 사용하여 정의하는 비동기 메서드를 비동기 메서드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-136">Asynchronous methods that you define by using `Async` and `Await` are referred to as async methods.</span></span>  
  
 <span data-ttu-id="fb353-137">다음 예제에서는 비동기 메서드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-137">The following example shows an async method.</span></span> <span data-ttu-id="fb353-138">코드의 거의 모든 내용이 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-138">Almost everything in the code should look completely familiar to you.</span></span> <span data-ttu-id="fb353-139">주석은 비동기를 만들 때 추가하는 기능을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-139">The comments call out the features that you add to create the asynchrony.</span></span>  
  
 <span data-ttu-id="fb353-140">이 항목의 마지막에 완전한 WPF(Windows Presentation Foundation) 예제 파일이 있으며, [Async 샘플: "Async 및 Await를 사용하는 비동기 프로그래밍"의 예제](http://go.microsoft.com/fwlink/?LinkID=261549)에서 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-140">You can find a complete Windows Presentation Foundation (WPF) example file at the end of this topic, and you can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](http://go.microsoft.com/fwlink/?LinkID=261549).</span></span>  
  
```vb  
' Three things to note in the signature:  
'  - The method has an Async modifier.   
'  - The return type is Task or Task(Of T). (See "Return Types" section.)  
'    Here, it is Task(Of Integer) because the return statement returns an integer.  
'  - The method name ends in "Async."  
Async Function AccessTheWebAsync() As Task(Of Integer)  
  
    ' You need to add a reference to System.Net.Http to declare client.  
    Dim client As HttpClient = New HttpClient()  
  
    ' GetStringAsync returns a Task(Of String). That means that when you await the  
    ' task you'll get a string (urlContents).  
    Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
    ' You can do work here that doesn't rely on the string from GetStringAsync.  
    DoIndependentWork()  
  
    ' The Await operator suspends AccessTheWebAsync.  
    '  - AccessTheWebAsync can't continue until getStringTask is complete.  
    '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
    '  - Control resumes here when getStringTask is complete.   
    '  - The Await operator then retrieves the string result from getStringTask.  
    Dim urlContents As String = Await getStringTask  
  
    ' The return statement specifies an integer result.  
    ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
    Return urlContents.Length  
End Function  
```  
  
 <span data-ttu-id="fb353-141">`AccessTheWebAsync`에 `GetStringAsync` 호출과 해당 완료 대기 사이에 수행할 수 있는 작업이 없는 경우 다음 단일 문을 호출하고 대기하여 코드를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-141">If `AccessTheWebAsync` doesn't have any work that it can do between calling `GetStringAsync` and awaiting its completion, you can simplify your code by calling and awaiting in the following single statement.</span></span>  
  
```vb  
Dim urlContents As String = Await client.GetStringAsync()  
```  
  
 <span data-ttu-id="fb353-142">이전 예제가 비동기 메서드인 이유는 다음과 같은 특성 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-142">The following characteristics summarize what makes the previous example an async method.</span></span>  
  
-   <span data-ttu-id="fb353-143">메서드 시그니처에 `Async` 한정자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-143">The method signature includes an `Async` modifier.</span></span>  
  
-   <span data-ttu-id="fb353-144">비동기 메서드의 이름은 규칙에 따라 "Async" 접미사로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-144">The name of an async method, by convention, ends with an "Async" suffix.</span></span>  
  
-   <span data-ttu-id="fb353-145">반환 형식은 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-145">The return type is one of the following types:</span></span>  
  
    -   <span data-ttu-id="fb353-146">메서드에 연산자 형식이 TResult인 Return 문이 있는 경우 <xref:System.Threading.Tasks.Task%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-146"><xref:System.Threading.Tasks.Task%601> if your method has a return statement in which the operand has type TResult.</span></span>  
  
    -   <span data-ttu-id="fb353-147">메서드에 반환 문이 포함되지 않았거나 피연산자가 없는 반환 문이 포함된 경우 <xref:System.Threading.Tasks.Task>입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-147"><xref:System.Threading.Tasks.Task> if your method has no return statement or has a return statement with no operand.</span></span>  
  
    -   <span data-ttu-id="fb353-148">비동기 이벤트 처리기를 작성하는 경우 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-148">[Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) if you're writing an async event handler.</span></span>  
  
     <span data-ttu-id="fb353-149">자세한 내용은 이 항목 뒷부분의 "반환 형식 및 매개 변수"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-149">For more information, see "Return Types and Parameters" later in this topic.</span></span>  
  
-   <span data-ttu-id="fb353-150">메서드는 일반적으로 비동기 작업이 완료될 때까지 메서드가 계속될 수 없는 지점을 표시하는 하나 이상의 대기 표현을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-150">The method usually includes at least one await expression, which marks a point where the method can't continue until the awaited asynchronous operation is complete.</span></span> <span data-ttu-id="fb353-151">한편, 메서드가 일시 중단되고 컨트롤이 메서드의 호출자로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-151">In the meantime, the method is suspended, and control returns to the method's caller.</span></span> <span data-ttu-id="fb353-152">이 항목의 다음 단원은 일시 중단 지점에서 발생하는 상황을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-152">The next section of this topic illustrates what happens at the suspension point.</span></span>  
  
 <span data-ttu-id="fb353-153">비동기 메서드에서는 제공된 키워드 및 형식을 사용해서 수행하려는 작업을 나타내고, 컴파일러는 일시 중단된 메서드에서 컨트롤이 대기 지점으로 반환될 때 수행되어야 하는 항목을 추적하는 등의 나머지 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-153">In async methods, you use the provided keywords and types to indicate what you want to do, and the compiler does the rest, including keeping track of what must happen when control returns to an await point in a suspended method.</span></span> <span data-ttu-id="fb353-154">루프 및 예외 처리와 같은 일부 루틴 프로세스는 기존의 비동기 코드에서 처리하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-154">Some routine processes, such as loops and exception handling, can be difficult to handle in traditional asynchronous code.</span></span> <span data-ttu-id="fb353-155">비동기 메서드에서는 동기 솔루션에서와 같이 필요한 만큼 이러한 요소를 작성하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-155">In an async method, you write these elements much as you would in a synchronous solution, and the problem is solved.</span></span>  
  
 <span data-ttu-id="fb353-156">이전 버전의 .NET Framework의 비동기에 대한 자세한 내용은 [TPL 및 일반적인 .NET Framework 비동기 프로그래밍](http://msdn.microsoft.com/library/e7b31170-a156-433f-9f26-b1fc7cd1776f)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-156">For more information about asynchrony in previous versions of the .NET Framework, see [TPL and Traditional .NET Framework Asynchronous Programming](http://msdn.microsoft.com/library/e7b31170-a156-433f-9f26-b1fc7cd1776f).</span></span>  
  
##  <span data-ttu-id="fb353-157"><a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Async 메서드에서 수행되는 작업</span><span class="sxs-lookup"><span data-stu-id="fb353-157"><a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> What Happens in an Async Method</span></span>  
 <span data-ttu-id="fb353-158">비동기 프로그래밍을 이해하는 데 있어 가장 중요한 점은 메서드에서 메서드로 제어 흐름을 이동하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-158">The most important thing to understand in asynchronous programming is how the control flow moves from method to method.</span></span> <span data-ttu-id="fb353-159">다음 다이어그램이 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-159">The following diagram leads you through the process.</span></span>  
  
 <span data-ttu-id="fb353-160">![비동기 프로그램 추적](../../../../csharp/programming-guide/concepts/async/media/navigationtrace.png "NavigationTrace")</span><span class="sxs-lookup"><span data-stu-id="fb353-160">![Trace an async program](../../../../csharp/programming-guide/concepts/async/media/navigationtrace.png "NavigationTrace")</span></span>  
  
 <span data-ttu-id="fb353-161">다이어그램의 번호는 다음 단계에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-161">The numbers in the diagram correspond to the following steps.</span></span>  
  
1.  <span data-ttu-id="fb353-162">이벤트 처리기가 호출되어 `AccessTheWebAsync` 비동기 메서드를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-162">An event handler calls and awaits  the  `AccessTheWebAsync` async method.</span></span>  
  
2.  <span data-ttu-id="fb353-163">`AccessTheWebAsync`는 <xref:System.Net.Http.HttpClient> 인스턴스를 만들고 <xref:System.Net.Http.HttpClient.GetStringAsync%2A> 비동기 메서드를 호출하여 웹 사이트의 내용을 문자열로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-163">`AccessTheWebAsync` creates an <xref:System.Net.Http.HttpClient> instance and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2A> asynchronous method to download the contents of a website as a string.</span></span>  
  
3.  <span data-ttu-id="fb353-164">`GetStringAsync`에서 특정 작업이 발생하여 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-164">Something happens in `GetStringAsync` that suspends its progress.</span></span> <span data-ttu-id="fb353-165">웹 사이트에서 다운로드 또는 다른 차단 작업을 수행할 때까지 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-165">Perhaps it must wait for a website to download or some other blocking activity.</span></span> <span data-ttu-id="fb353-166">리소스를 차단하지 않기 위해 `GetStringAsync`는 해당 호출자인 `AccessTheWebAsync`에 제어 권한을 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-166">To avoid blocking resources, `GetStringAsync` yields control to its caller, `AccessTheWebAsync`.</span></span>  
  
     <span data-ttu-id="fb353-167">`GetStringAsync`는 TResult가 문자열인 <xref:System.Threading.Tasks.Task%601>를 반환하고 `AccessTheWebAsync`는 `getStringTask` 변수에 작업을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-167">`GetStringAsync` returns a <xref:System.Threading.Tasks.Task%601> where TResult is a string, and `AccessTheWebAsync` assigns the task to the `getStringTask` variable.</span></span> <span data-ttu-id="fb353-168">이 작업은 작업이 완료될 때 실제 문자열 값을 생성하기 위한 코드와 함께 `GetStringAsync`를 호출하는 지속적인 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-168">The task represents the ongoing process for the call to `GetStringAsync`, with a commitment to produce an actual string value when the work is complete.</span></span>  
  
4.  <span data-ttu-id="fb353-169">`getStringTask`가 아직 대기되지 않았으므로 `AccessTheWebAsync`가 `GetStringAsync`의 최종 결과에 무관한 다른 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-169">Because `getStringTask` hasn't been awaited yet, `AccessTheWebAsync` can continue with other work that doesn't depend on the final result from `GetStringAsync`.</span></span> <span data-ttu-id="fb353-170">이 작업은 동기 메서드 `DoIndependentWork`를 호출하여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-170">That work is represented by a call to the synchronous method `DoIndependentWork`.</span></span>  
  
5.  <span data-ttu-id="fb353-171">`DoIndependentWork`는 작업을 수행하고 호출자에게 반환하는 동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-171">`DoIndependentWork` is a synchronous method that does its work and returns to its caller.</span></span>  
  
6.  <span data-ttu-id="fb353-172">`AccessTheWebAsync`에 `getStringTask` 결과 없이 수행할 수 있는 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-172">`AccessTheWebAsync` has run out of work that it can do without a result from `getStringTask`.</span></span> <span data-ttu-id="fb353-173">다음으로 `AccessTheWebAsync`는 다운로드한 문자열의 길이를 계산하여 반환하려 하지만, 메서드가 문자열을 확인할 때까지 해당 값을 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-173">`AccessTheWebAsync` next wants to calculate and return the length of the downloaded string, but the method can't calculate that value until the method has the string.</span></span>  
  
     <span data-ttu-id="fb353-174">따라서 `AccessTheWebAsync`는 await 연산자를 사용해서 해당 프로세스를 일시 중단하고 `AccessTheWebAsync`를 호출한 메서드에 제어 권한을 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-174">Therefore, `AccessTheWebAsync` uses an await operator to suspend its progress and to yield control to the method that called `AccessTheWebAsync`.</span></span> <span data-ttu-id="fb353-175">`AccessTheWebAsync`는 호출자에게 `Task<int>`(Visual Basic의 `Task(Of Integer)`)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-175">`AccessTheWebAsync` returns a `Task<int>` (`Task(Of Integer)` in Visual Basic) to the caller.</span></span> <span data-ttu-id="fb353-176">작업은 다운로드한 문자열의 길이인 정수 결과를 만든다는 약속을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-176">The task represents a promise to produce an integer result that's the length of the downloaded string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb353-177">`GetStringAsync`가 대기하기 전에 `getStringTask`(및 `AccessTheWebAsync`)가 완료되면 `AccessTheWebAsync`에 컨트롤이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-177">If `GetStringAsync` (and therefore `getStringTask`) is complete before `AccessTheWebAsync` awaits it, control remains in `AccessTheWebAsync`.</span></span> <span data-ttu-id="fb353-178">일시 중단 및 `AccessTheWebAsync`의 반환 비용은 호출된 비동기 프로세스(`getStringTask`)가 이미 완료되었고 AccessTheWebSync가 최종 결과를 기다릴 필요가 없다면 낭비됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-178">The expense of suspending and then returning to `AccessTheWebAsync` would be wasted if the called asynchronous process (`getStringTask`) has already completed and AccessTheWebSync doesn't have to wait for the final result.</span></span>  
  
     <span data-ttu-id="fb353-179">호출자(이 예제의 이벤트 처리기) 내에서 처리 패턴이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-179">Inside the caller (the event handler in this example), the processing pattern continues.</span></span> <span data-ttu-id="fb353-180">호출자가 해당 결과를 기다리거나 즉시 기다리기 전에 `AccessTheWebAsync`에서 결과에 의존하지 않는 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-180">The caller might do other work that doesn't depend on the result from `AccessTheWebAsync` before awaiting that result, or the caller might await immediately.</span></span>   <span data-ttu-id="fb353-181">`AccessTheWebAsync`에 대한 이벤트가 대기 중이며 `AccessTheWebAsync`가 `GetStringAsync`를 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-181">The event handler is waiting for `AccessTheWebAsync`, and `AccessTheWebAsync` is waiting for `GetStringAsync`.</span></span>  
  
7.  <span data-ttu-id="fb353-182">`GetStringAsync`가 완료되고 문자열 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-182">`GetStringAsync` completes and produces a string result.</span></span> <span data-ttu-id="fb353-183">`GetStringAsync`를 호출할 경우 문자열 결과가 예상대로 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-183">The string result isn't returned by the call to `GetStringAsync` in the way that you might expect.</span></span> <span data-ttu-id="fb353-184">(메서드가 이미 3단계에서 작업을 반환했습니다.) 대신 문자열 결과가 메서드 `getStringTask`의 완료를 나타내는 작업에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-184">(Remember that the method already returned a task in step 3.) Instead, the string result is stored in the task that represents the completion of the method, `getStringTask`.</span></span> <span data-ttu-id="fb353-185">await 연산자가 `getStringTask`에서 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-185">The await operator retrieves the result from `getStringTask`.</span></span> <span data-ttu-id="fb353-186">할당 문은 검색된 결과를 `urlContents`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-186">The assignment statement assigns the retrieved result to `urlContents`.</span></span>  
  
8.  <span data-ttu-id="fb353-187">`AccessTheWebAsync`에 문자열 결과가 있는 경우 메서드가 문자열 길이를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-187">When `AccessTheWebAsync` has the string result, the method can calculate the length of the string.</span></span> <span data-ttu-id="fb353-188">그런 다음 `AccessTheWebAsync` 작업도 완료되고 대기 이벤트 처리기를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-188">Then the work of `AccessTheWebAsync` is also complete, and the waiting event handler can resume.</span></span> <span data-ttu-id="fb353-189">이 항목 뒷부분의 전체 예에서는 이벤트 처리기가 길이 결과 값을 검색하고 출력하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-189">In the full example at the end of the topic, you can confirm that the event handler retrieves and prints the value of the length result.</span></span>  
  
 <span data-ttu-id="fb353-190">비동기 프로그래밍을 처음 접하는 사용자인 경우 동기 동작과 비동기 동작의 차이점을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-190">If you are new to asynchronous programming, take a minute to consider the difference between synchronous and asynchronous behavior.</span></span> <span data-ttu-id="fb353-191">비동기 메서드는 작업이 완료될 때 반환되지만(5단계) 비동기 메서드는 작업이 일시 중단될 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-191">A synchronous method returns when its work is complete (step 5), but an async method returns a task value when its work is suspended (steps 3 and 6).</span></span> <span data-ttu-id="fb353-192">비동기 메서드가 해당 작업을 완료하면 작업이 완료된 것으로 표시되고 결과가 있을 경우 작업에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-192">When the async method eventually completes its work, the task is marked as completed and the result, if any, is stored in the task.</span></span>  
  
 <span data-ttu-id="fb353-193">제어 흐름에 대한 자세한 내용은 [비동기 프로그램의 제어 흐름(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-193">For more information about control flow, see [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
##  <span data-ttu-id="fb353-194"><a name="BKMK_APIAsyncMethods"></a> API Async 메서드</span><span class="sxs-lookup"><span data-stu-id="fb353-194"><a name="BKMK_APIAsyncMethods"></a> API Async Methods</span></span>  
 <span data-ttu-id="fb353-195">`GetStringAsync`와 같이 비동기 프로그래밍을 지원하는 메서드를 어디에서 검색해야 할지 궁금했을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-195">You might be wondering where to find methods such as `GetStringAsync` that support async programming.</span></span> <span data-ttu-id="fb353-196">.NET Framework 4.5 이상에는 `Async` 및 `Await`에 작동하는 많은 멤버가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-196">The  .NET Framework 4.5 or higher contains many members that work with `Async` and `Await`.</span></span> <span data-ttu-id="fb353-197">멤버 이름에 붙는 "Async" 접미사로 이러한 멤버와 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>의 반환 형식을 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-197">You can recognize these members by the "Async" suffix that’s attached to the member name and a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fb353-198">예를 들어, `System.IO.Stream` 클래스는 동기 메서드인 <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> 및 <xref:System.IO.Stream.Write%2A>와 함께 <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> 및 <xref:System.IO.Stream.WriteAsync%2A>와 같은 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-198">For example, the `System.IO.Stream` class contains methods such as <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A>, and <xref:System.IO.Stream.WriteAsync%2A> alongside the synchronous methods <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A>, and <xref:System.IO.Stream.Write%2A>.</span></span>  
  
 <span data-ttu-id="fb353-199">Windows 런타임에는 Windows 앱에서 `Async` 및 `Await`와 함께 사용할 수 있는 많은 메서드도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-199">The Windows Runtime also contains many methods that you can use with `Async` and `Await` in Windows apps.</span></span> <span data-ttu-id="fb353-200">자세한 내용 및 예제 메서드를 보려면 [빠른 시작: 비동기 프로그래밍에 await 연산자 사용](http://go.microsoft.com/fwlink/?LinkId=248545), [비동기 프로그래밍(Windows 스토어 앱)](http://go.microsoft.com/fwlink/?LinkId=259592) 및 [WhenAny: .NET Framework와 Windows 런타임 간 브리징](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-200">For more information and example methods, see [Quickstart: using the await operator for asynchronous programming](http://go.microsoft.com/fwlink/?LinkId=248545), [Asynchronous programming (Windows Store apps)](http://go.microsoft.com/fwlink/?LinkId=259592), and [WhenAny: Bridging between the .NET Framework and the Windows Runtime](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx).</span></span>  
  
##  <span data-ttu-id="fb353-201"><a name="BKMK_Threads"></a> 스레드</span><span class="sxs-lookup"><span data-stu-id="fb353-201"><a name="BKMK_Threads"></a> Threads</span></span>  
 <span data-ttu-id="fb353-202">비동기 메서드는 비차단 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-202">Async methods are intended to be non-blocking operations.</span></span> <span data-ttu-id="fb353-203">비동기 메서드의 `Await` 식은 대기한 작업이 실행되는 동안 현재 스레드를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-203">An `Await` expression in an async method doesn’t block the current thread while the awaited task is running.</span></span> <span data-ttu-id="fb353-204">대신에 이 식은 메서드의 나머지를 연속으로 등록하고 제어 기능을 비동기 메서드 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-204">Instead, the expression signs up the rest of the method as a continuation and returns control to the caller of the async method.</span></span>  
  
 <span data-ttu-id="fb353-205">`Async` 및 `Await` 키워드로 인해 추가 스레드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-205">The `Async` and `Await` keywords don't cause additional threads to be created.</span></span> <span data-ttu-id="fb353-206">비동기 메서드는 자체 스레드에서 실행되지 않으므로 다중 스레드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-206">Async methods don't require multithreading because an async method doesn't run on its own thread.</span></span> <span data-ttu-id="fb353-207">메서드는 현재 동기화 컨텍스트에서 실행되고 메서드가 활성화된 경우에만 스레드에서 시간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-207">The method runs on the current synchronization context and uses time on the thread only when the method is active.</span></span> <span data-ttu-id="fb353-208"><xref:System.Threading.Tasks.Task.Run%2A?displayProperty=fullName>을 사용하여 CPU 바인딩 작업을 백그라운드 스레드로 이동할 수 있지만 백그라운드 스레드는 프로세스를 지원하지 않고 결과를 사용할 수 있을 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-208">You can use <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=fullName> to move CPU-bound work to a background thread, but a background thread doesn't help with a process that's just waiting for results to become available.</span></span>  
  
 <span data-ttu-id="fb353-209">비동기 프로그래밍에 대한 비동기 기반 접근 방법은 거의 모든 경우에 기존 방법보다 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-209">The async-based approach to asynchronous programming is preferable to existing approaches in almost every case.</span></span> <span data-ttu-id="fb353-210">특히, 이 접근 방식은 코드가 더 간단하고 경합 조건을 방지할 필요가 없기 때문에 IO 바인딩 작업의 <xref:System.ComponentModel.BackgroundWorker>보다 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-210">In particular, this approach is better than <xref:System.ComponentModel.BackgroundWorker> for IO-bound operations because the code is simpler and you don't have to guard against race conditions.</span></span> <span data-ttu-id="fb353-211">비동기 프로그래밍은 코드 실행에 대한 조합 세부 정보를 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=fullName>이 스레드 풀로 변환하는 작업과 구분하기 때문에 <xref:System.ComponentModel.BackgroundWorker>을 함께 사용하는 비동기 프로그래밍은 CPU 바인딩 작업을 위한 `Task.Run`보다 효과가 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-211">In combination with <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=fullName>, async programming is better than <xref:System.ComponentModel.BackgroundWorker> for CPU-bound operations because async programming separates the coordination details of running your code from the work that `Task.Run` transfers to the threadpool.</span></span>  
  
##  <span data-ttu-id="fb353-212"><a name="BKMK_AsyncandAwait"></a> Async 및 Await</span><span class="sxs-lookup"><span data-stu-id="fb353-212"><a name="BKMK_AsyncandAwait"></a> Async and Await</span></span>  
 <span data-ttu-id="fb353-213">[Async](../../../../visual-basic/language-reference/modifiers/async.md) 한정자를 사용해서 메서드를 비동기 메서드로 지정하면 다음 두 기능이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-213">If you specify that a method is an async method by using an [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier, you enable the following two capabilities.</span></span>  
  
-   <span data-ttu-id="fb353-214">표시된 비동기 메서드는 [Await](../../../../visual-basic/language-reference/operators/await-operator.md)를 사용하여 일시 중단 지점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-214">The marked async method can use [Await](../../../../visual-basic/language-reference/operators/await-operator.md) to designate suspension points.</span></span> <span data-ttu-id="fb353-215">Await 연산자는 비동기 프로세스가 완료될 때까지 비동기 메서드가 해당 지점을 계속할 수 없다고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-215">The await operator tells the compiler that the async method can't continue past that point until the awaited asynchronous process is complete.</span></span> <span data-ttu-id="fb353-216">한편, 컨트롤이 비동기 메서드의 호출자로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-216">In the meantime, control returns to the caller of the async method.</span></span>  
  
     <span data-ttu-id="fb353-217">`Await` 식에서 비동기 메서드를 일시 중단하더라도 메서드가 종료되지는 않으며 `Finally` 블록이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-217">The suspension of an async method at an `Await` expression doesn't constitute an exit from the method, and `Finally` blocks don’t run.</span></span>  
  
-   <span data-ttu-id="fb353-218">표시된 비동기 메서드는 이 메서드를 호출한 다른 메서드에 의해 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-218">The marked async method can itself be awaited by methods that call it.</span></span>  
  
 <span data-ttu-id="fb353-219">비동기 메서드는 일반적으로 `Await` 연산자를 하나 이상 가지고 있지만, `Await` 식이 없을 경우 컴파일러 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-219">An async method typically contains one or more occurrences of an `Await` operator, but the absence of `Await` expressions doesn’t cause a compiler error.</span></span> <span data-ttu-id="fb353-220">비동기 메서드에서 `Await` 연산자를 사용하여 일시 중단 시점을 표시하지 않는 경우 메서드가 `Async` 한정자에 상관없이 동기 메서드가 실행되는 방식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-220">If an async method doesn’t use an `Await` operator to mark a suspension point, the method executes as a synchronous method does, despite the `Async` modifier.</span></span> <span data-ttu-id="fb353-221">컴파일러는 다음 메서드에 대해 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-221">The compiler issues a warning for such methods.</span></span>  
  
 <span data-ttu-id="fb353-222">`Async` 및 `Await`은 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-222">`Async` and `Await` are contextual keywords.</span></span> <span data-ttu-id="fb353-223">자세한 내용과 예제는 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-223">For more information and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="fb353-224">비동기</span><span class="sxs-lookup"><span data-stu-id="fb353-224">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)  
  
-   [<span data-ttu-id="fb353-225">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="fb353-225">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)  
  
##  <span data-ttu-id="fb353-226"><a name="BKMK_ReturnTypesandParameters"></a> 반환 형식 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb353-226"><a name="BKMK_ReturnTypesandParameters"></a> Return Types and Parameters</span></span>  
 <span data-ttu-id="fb353-227">.NET Framework 프로그래밍에서 비동기 메서드는 일반적으로 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-227">In .NET Framework programming, an async method typically returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fb353-228">비동기 메서드 내에서 `Await` 연산자는 호출에서 다른 비동기 메서드로 전환되는 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-228">Inside an async method, an `Await` operator is applied to a task that's returned from a call to another async method.</span></span>  
  
 <span data-ttu-id="fb353-229">메서드에 `TResult` 형식의 피연산자를 지정하는 [Return](../../../../visual-basic/language-reference/statements/return-statement.md) 문이 포함되어 있을 경우 <xref:System.Threading.Tasks.Task%601>를 반환 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-229">You specify <xref:System.Threading.Tasks.Task%601> as the return type if the method contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that specifies an operand of type `TResult`.</span></span>  
  
 <span data-ttu-id="fb353-230">메서드에 return 문이 없거나 피연산자를 반환하지 않는 return 문이 있을 경우 반환 형식으로 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-230">You use `Task` as the return type if the method has no return statement or has a return statement that doesn't return an operand.</span></span>  
  
 <span data-ttu-id="fb353-231">다음 예제는 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>를 반환하는 메서드를 선언하고 호출하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-231">The following example shows how you declare and call a method that returns a <xref:System.Threading.Tasks.Task%601> or a <xref:System.Threading.Tasks.Task>.</span></span>  
  
```vb  
' Signature specifies Task(Of Integer)  
Async Function TaskOfTResult_MethodAsync() As Task(Of Integer)  
  
    Dim hours As Integer  
    ' . . .  
    ' Return statement specifies an integer result.  
    Return hours  
End Function  
  
' Calls to TaskOfTResult_MethodAsync  
Dim returnedTaskTResult As Task(Of Integer) = TaskOfTResult_MethodAsync()  
Dim intResult As Integer = Await returnedTaskTResult  
' or, in a single statement  
Dim intResult As Integer = Await TaskOfTResult_MethodAsync()  
  
' Signature specifies Task  
Async Function Task_MethodAsync() As Task  
  
    ' . . .  
    ' The method has no return statement.  
End Function  
  
' Calls to Task_MethodAsync  
Task returnedTask = Task_MethodAsync()  
Await returnedTask  
' or, in a single statement  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="fb353-232">반환된 각 작업은 진행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-232">Each returned task represents ongoing work.</span></span> <span data-ttu-id="fb353-233">작업은 비동기 프로세스 상태에 대한 정보를 캡슐화하며, 결과적으로 프로세스의 최종 결과 또는 성공하지 못한 경우 프로세스가 발생시키는 예외에 대한 정보를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-233">A task encapsulates information about the state of the asynchronous process and, eventually, either the final result from the process or the exception that the process raises if it doesn't succeed.</span></span>  
  
 <span data-ttu-id="fb353-234">또한 비동기 메서드는 `Sub` 메서드일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-234">An async method can also be a `Sub` method.</span></span> <span data-ttu-id="fb353-235">이 반환 형식은 기본적으로 반환 형식이 필요할 때 이벤트 처리기를 정의하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-235">This return type is used primarily to define event handlers, where a return type is required.</span></span> <span data-ttu-id="fb353-236">비동기 이벤트 처리기는 비동기 프로그램의 시작점 역할을 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-236">Async event handlers often serve as the starting point for async programs.</span></span>  
  
 <span data-ttu-id="fb353-237">`Sub` 프로시저인 비동기 메서드는 대기할 수 없으며 호출자는 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-237">An async method that’s a `Sub` procedure can’t be awaited, and the caller can't catch any exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="fb353-238">비동기 메서드는 모든 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-238">An async method can't declare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parameters, but the method can call methods that have such parameters.</span></span>  
  
 <span data-ttu-id="fb353-239">자세한 내용과 예제는 [비동기 반환 형식(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-239">For more information and examples, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span> <span data-ttu-id="fb353-240">비동기 메서드에서 예외를 catch하는 방법에 대한 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-240">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="fb353-241">Windows 런타임 프로그래밍의 비동기 API에는 작업과 유사한 다음 반환 형식 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-241">Asynchronous APIs in Windows Runtime  programming have one of the following return types, which are similar to tasks:</span></span>  
  
-   <span data-ttu-id="fb353-242"><xref:System.Threading.Tasks.Task%601>에 해당하는 [IAsyncOperation](http://go.microsoft.com/fwlink/p/?LinkId=261896)</span><span class="sxs-lookup"><span data-stu-id="fb353-242">[IAsyncOperation](http://go.microsoft.com/fwlink/p/?LinkId=261896), which corresponds to <xref:System.Threading.Tasks.Task%601></span></span>  
  
-   <span data-ttu-id="fb353-243"><xref:System.Threading.Tasks.Task>에 해당하는 [IAsyncAction](http://go.microsoft.com/fwlink/p/?LinkId=261897)</span><span class="sxs-lookup"><span data-stu-id="fb353-243">[IAsyncAction](http://go.microsoft.com/fwlink/p/?LinkId=261897), which corresponds to <xref:System.Threading.Tasks.Task></span></span>  
  
-   [<span data-ttu-id="fb353-244">IAsyncActionWithProgress</span><span class="sxs-lookup"><span data-stu-id="fb353-244">IAsyncActionWithProgress</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=261898)  
  
-   [<span data-ttu-id="fb353-245">IAsyncOperationWithProgress</span><span class="sxs-lookup"><span data-stu-id="fb353-245">IAsyncOperationWithProgress</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=259454)  
  
 <span data-ttu-id="fb353-246">자세한 내용 및 예제를 보려면 [빠른 시작: 비동기 프로그래밍에 await 연산자 사용](http://go.microsoft.com/fwlink/p/?LinkId=248545)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb353-246">For more information and an example, see [Quickstart: using the await operator for asynchronous programming](http://go.microsoft.com/fwlink/p/?LinkId=248545).</span></span>  
  
##  <span data-ttu-id="fb353-247"><a name="BKMK_NamingConvention"></a> 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="fb353-247"><a name="BKMK_NamingConvention"></a> Naming Convention</span></span>  
 <span data-ttu-id="fb353-248">규칙에 따라 `Async` 한정자가 있는 메서드 이름에 "Async"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-248">By convention, you append "Async" to the names of methods that have an `Async` modifier.</span></span>  
  
 <span data-ttu-id="fb353-249">여기서 이벤트, 기본 클래스 또는 인터페이스 계약으로 다른 이름을 제안하는 규칙을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-249">You can ignore the convention where an event, base class, or interface contract suggests a different name.</span></span> <span data-ttu-id="fb353-250">예를 들어, `Button1_Click`과 같은 공용 이벤트 처리기의 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-250">For example, you shouldn’t rename common event handlers, such as `Button1_Click`.</span></span>  
  
##  <span data-ttu-id="fb353-251"><a name="BKMK_RelatedTopics"></a> 관련 항목 및 샘플(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="fb353-251"><a name="BKMK_RelatedTopics"></a> Related Topics and Samples (Visual Studio)</span></span>  
  
|<span data-ttu-id="fb353-252">제목</span><span class="sxs-lookup"><span data-stu-id="fb353-252">Title</span></span>|<span data-ttu-id="fb353-253">설명</span><span class="sxs-lookup"><span data-stu-id="fb353-253">Description</span></span>|<span data-ttu-id="fb353-254">샘플</span><span class="sxs-lookup"><span data-stu-id="fb353-254">Sample</span></span>|  
|-----------|-----------------|------------|  
|[<span data-ttu-id="fb353-255">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-255">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|<span data-ttu-id="fb353-256">동기 WPF 솔루션을 비동기 WPF 솔루션으로 변환하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-256">Shows how to convert a synchronous WPF solution to an asynchronous WPF solution.</span></span> <span data-ttu-id="fb353-257">이 응용 프로그램은 일련의 웹 사이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-257">The application downloads a series of websites.</span></span>|[<span data-ttu-id="fb353-258">Async 샘플: 웹 연습에 액세스</span><span class="sxs-lookup"><span data-stu-id="fb353-258">Async Sample: Accessing the Web Walkthrough</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=255191&clcid=0x409)|  
|[<span data-ttu-id="fb353-259">방법: Task.WhenAll을 사용하여 비동기 연습 확장(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-259">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|<span data-ttu-id="fb353-260">이전 연습에 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-260">Adds <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> to the previous walkthrough.</span></span> <span data-ttu-id="fb353-261">`WhenAll`을 사용하면 모든 다운로드가 동시에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-261">The use of `WhenAll` starts all the downloads at the same time.</span></span>||  
|[<span data-ttu-id="fb353-262">방법: Async 및 Await를 사용하여 병렬로 여러 웹 요청 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-262">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|<span data-ttu-id="fb353-263">동시에 여러 작업을 시작하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-263">Demonstrates how to start several tasks at the same time.</span></span>|[<span data-ttu-id="fb353-264">Async 샘플: 여러 웹 요청을 병렬로 만들기</span><span class="sxs-lookup"><span data-stu-id="fb353-264">Async Sample: Make Multiple Web Requests in Parallel</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=254906&clcid=0x409)|  
|[<span data-ttu-id="fb353-265">비동기 반환 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-265">Async Return Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)|<span data-ttu-id="fb353-266">비동기 메서드에서 반환할 수 있는 형식을 설명하고 각 형식이 언제 적절한가를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-266">Illustrates the types that async methods can return and explains when each type is appropriate.</span></span>||  
|[<span data-ttu-id="fb353-267">비동기 프로그램의 제어 흐름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-267">Control Flow in Async Programs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)|<span data-ttu-id="fb353-268">비동기 프로그램에서 연속적 await 표현을 통한 컨트롤의 흐름을 자세히 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-268">Traces in detail the flow of control through a succession of await expressions in an asynchronous program.</span></span>|[<span data-ttu-id="fb353-269">Async 샘플: 비동기 프로그램의 제어 흐름</span><span class="sxs-lookup"><span data-stu-id="fb353-269">Async Sample: Control Flow in Async Programs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=255285&clcid=0x409)|  
|[<span data-ttu-id="fb353-270">Async 응용 프로그램 미세 조정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-270">Fine-Tuning Your Async Application (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)|<span data-ttu-id="fb353-271">비동기 솔루션에 다음과 같은 기능을 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-271">Shows how to add the following functionality to your async solution:</span></span><br /><br /> <span data-ttu-id="fb353-272">-   [비동기 작업 또는 작업 목록 취소(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="fb353-272">-   [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span></span><br /><span data-ttu-id="fb353-273">-   [일정 기간 이후 비동기 작업 취소(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span><span class="sxs-lookup"><span data-stu-id="fb353-273">-   [Cancel Async Tasks after a Period of Time (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span></span><br /><span data-ttu-id="fb353-274">-   [비동기 작업 하나가 완료되면 남은 비동기 작업 취소(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span><span class="sxs-lookup"><span data-stu-id="fb353-274">-   [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span></span><br /><span data-ttu-id="fb353-275">-   [비동기 작업을 여러 개 시작하고 완료될 때마다 처리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span><span class="sxs-lookup"><span data-stu-id="fb353-275">-   [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span></span>|[<span data-ttu-id="fb353-276">Async 샘플: 응용 프로그램 미세 조정</span><span class="sxs-lookup"><span data-stu-id="fb353-276">Async Sample: Fine Tuning Your Application</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=255046&clcid=0x409)|  
|[<span data-ttu-id="fb353-277">비동기 응용 프로그램에서 재진입 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-277">Handling Reentrancy in Async Apps (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|<span data-ttu-id="fb353-278">비동기 작업이 실행되는 동안 현재 비동기 작업을 다시 시작하는 경우 처리 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-278">Shows how to handle cases in which an active asynchronous operation is restarted while it’s running.</span></span>||  
|<span data-ttu-id="fb353-279">[WhenAny: .NET Framework와 Windows 런타임 간 브리징](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb353-279">[WhenAny: Bridging between the .NET Framework and the Windows Runtime](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx)</span></span>|<span data-ttu-id="fb353-280">[!INCLUDE[wrt](~/includes/wrt-md.md)] 메서드에 <xref:System.Threading.Tasks.Task.WhenAny%2A>를 사용할 수 있도록 .NET Framework의 작업 형식과 [!INCLUDE[wrt](~/includes/wrt-md.md)]의 IAsyncOperations 사이의 연결 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-280">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.Tasks.Task.WhenAny%2A> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="fb353-281">Async 샘플: .NET 및 Windows 런타임 간 연결(AsTask 및 WhenAny)</span><span class="sxs-lookup"><span data-stu-id="fb353-281">Async Sample: Bridging between .NET and Windows Runtime (AsTask and WhenAny)</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=260638)|  
|<span data-ttu-id="fb353-282">비동기 취소: .NET Framework와 Windows 런타임 간 브리징</span><span class="sxs-lookup"><span data-stu-id="fb353-282">Async Cancellation: Bridging between the .NET Framework and the Windows Runtime</span></span>|<span data-ttu-id="fb353-283">[!INCLUDE[wrt](~/includes/wrt-md.md)] 메서드에 <xref:System.Threading.CancellationTokenSource>를 사용할 수 있도록 .NET Framework의 작업 형식과 [!INCLUDE[wrt](~/includes/wrt-md.md)]의 IAsyncOperations 사이의 연결 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-283">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.CancellationTokenSource> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="fb353-284">Async 샘플: .NET 및 Windows 런타임 간 연결(AsTask & 취소)</span><span class="sxs-lookup"><span data-stu-id="fb353-284">Async Sample: Bridging between .NET and Windows Runtime (AsTask & Cancellation)</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=263004)|  
|[<span data-ttu-id="fb353-285">파일 액세스에 Async 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb353-285">Using Async for File Access (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/using-async-for-file-access.md)|<span data-ttu-id="fb353-286">async 및 await를 사용하여 파일에 액세스하는 이점을 나열하고 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-286">Lists and demonstrates the benefits of using async and await to access files.</span></span>||  
|[<span data-ttu-id="fb353-287">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="fb353-287">Task-based Asynchronous Pattern (TAP)</span></span>](http://msdn.microsoft.com/library/8cef1fcf-6f9f-417c-b21f-3fd8bac75007)|<span data-ttu-id="fb353-288">.NET Framework의 새로운 비동기 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-288">Describes a new pattern for asynchrony in the .NET Framework.</span></span> <span data-ttu-id="fb353-289">패턴은 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-289">The pattern is based on the <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> types.</span></span>||  
|[<span data-ttu-id="fb353-290">비동기 Channel 9 비디오</span><span class="sxs-lookup"><span data-stu-id="fb353-290">Async Videos on Channel 9</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=267466)|<span data-ttu-id="fb353-291">비동기 프로그래밍에 대한 다양한 비디오로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-291">Provides links to a variety of videos about async programming.</span></span>||  
  
##  <span data-ttu-id="fb353-292"><a name="BKMK_CompleteExample"></a> 전체 예제</span><span class="sxs-lookup"><span data-stu-id="fb353-292"><a name="BKMK_CompleteExample"></a> Complete Example</span></span>  
 <span data-ttu-id="fb353-293">다음 코드는 이 항목에서 설명하는 WPF(Windows Presentation Foundation) 응용 프로그램의 MainWindow.xaml.vb 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-293">The following code is the MainWindow.xaml.vb file from the Windows Presentation Foundation (WPF) application that this topic discusses.</span></span> <span data-ttu-id="fb353-294">[Async 샘플: "Async 및 Await를 사용하는 비동기 프로그래밍"의 예제](http://go.microsoft.com/fwlink/p/?LinkID=261549)에서 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb353-294">You can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](http://go.microsoft.com/fwlink/p/?LinkID=261549).</span></span>  
  
```vb  
' Add an Imports statement and a reference for System.Net.Http  
Imports System.Net.Http  
  
Class MainWindow  
  
    ' Mark the event handler with async so you can use Await in it.  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Call and await separately.  
        'Task<int> getLengthTask = AccessTheWebAsync();  
        '' You can do independent work here.  
        'int contentLength = await getLengthTask;  
  
        Dim contentLength As Integer = Await AccessTheWebAsync()  
  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
    End Sub  
  
    ' Three things to note in the signature:  
    '  - The method has an Async modifier.   
    '  - The return type is Task or Task(Of T). (See "Return Types" section.)  
    '    Here, it is Task(Of Integer) because the return statement returns an integer.  
    '  - The method name ends in "Async."  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' You need to add a reference to System.Net.Http to declare client.  
        Dim client As HttpClient = New HttpClient()  
  
        ' GetStringAsync returns a Task(Of String). That means that when you await the  
        ' task you'll get a string (urlContents).  
        Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' You can do work here that doesn't rely on the string from GetStringAsync.  
        DoIndependentWork()  
  
        ' The Await operator suspends AccessTheWebAsync.  
        '  - AccessTheWebAsync can't continue until getStringTask is complete.  
        '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
        '  - Control resumes here when getStringTask is complete.   
        '  - The Await operator then retrieves the string result from getStringTask.  
        Dim urlContents As String = Await getStringTask  
  
        ' The return statement specifies an integer result.  
        ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
        Return urlContents.Length  
    End Function  
  
    Sub DoIndependentWork()  
        ResultsTextBox.Text &= "Working . . . . . . ." & vbCrLf  
    End Sub  
End Class  
  
' Sample Output:  
  
' Working . . . . . . .  
  
' Length of the downloaded string: 41763.  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb353-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb353-295">See Also</span></span>  
 <span data-ttu-id="fb353-296">[Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="fb353-296">[Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
 [<span data-ttu-id="fb353-297">비동기</span><span class="sxs-lookup"><span data-stu-id="fb353-297">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)

