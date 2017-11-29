---
title: "매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 071e0aa916e4b3464c7c0cbff6596cabc6b67906
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="028c2-102">매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="028c2-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="028c2-103">스레드 클래스의 생성자에 인수를 사용하지 않고 값을 반환하지 않는 프로시저에 대한 참조를 전달해야 하기 때문에 다중 스레드 응용 프로그램에서 값을 제공하고 반환하는 작업은 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="028c2-104">다음 섹션에서는 매개 변수를 제공하고 별도 스레드의 프로시저에서 값을 반환하는 몇 가지 간단한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="028c2-105">다중 스레드 프로시저에 대한 매개 변수 제공</span><span class="sxs-lookup"><span data-stu-id="028c2-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="028c2-106">다중 스레드 메서드 호출에 대한 매개 변수를 제공하는 최상의 방법은 대상 메서드를 클래스에 래핑하고 새 스레드에 대한 매개 변수로 사용할 해당 클래스의 필드를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="028c2-107">이 방법의 장점은 새 스레드를 시작할 때마다 해당 매개 변수를 사용하여 클래스의 새 인스턴스를 만들 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="028c2-108">예를 들어 다음 코드와 같이 삼각형의 면적을 계산하는 함수가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="028c2-109">다음과 같이 `CalcArea` 함수를 래핑하고 입력 매개 변수를 저장할 필드를 만드는 클래스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="028c2-110">`AreaClass`를 사용하려면 `AreaClass` 개체를 만들고 `Base` 및 `Height` 속성을 다음 코드와 같이 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 <span data-ttu-id="028c2-111">`TestArea` 프로시저는 `CalcArea` 메서드를 호출한 후 `Area` 필드의 값을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="028c2-112">`CalcArea`는 별도 스레드에서 실행되기 때문에 `Thread.Start`를 호출한 후 즉시 확인하는 경우 `Area` 필드가 설정되어 있지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="028c2-113">다음 섹션에서는 다중 스레드 프로시저에서 값을 반환하는 더 나은 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="028c2-114">다중 스레드 프로시저에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="028c2-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="028c2-115">프로시저는 함수일 수 없고 `ByRef` 인수를 사용할 수 없다는 사실 때문에 별도 스레드에서 실행되는 프로시저에서 값을 반환하는 작업은 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="028c2-116">값을 반환하는 가장 쉬운 방법은 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 스레드를 관리하고 작업이 완료되면 이벤트를 발생시킨 다음 이벤트 처리기에서 결과를 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="028c2-117">다음 예제에서는 별도 스레드에서 실행 중인 프로시저에서 이벤트를 발생시켜 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 <span data-ttu-id="028c2-118">매개 변수를 제공하고 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드의 선택적 `ByVal` 상태 개체 변수를 사용하여 스레드 풀 스레드에 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="028c2-119">스레드 타이머 스레드도 이 용도의 상태 개체를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="028c2-120">스레드 풀링 및 스레드 타이머에 대 한 정보를 참조 하십시오. [스레드 풀링 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[스레드 풀링](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) 및 [스레드 타이머 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="028c2-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="028c2-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="028c2-121">See Also</span></span>  
 [<span data-ttu-id="028c2-122">연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="028c2-122">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="028c2-123">스레드 풀링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="028c2-123">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="028c2-124">스레드 동기화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="028c2-124">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="028c2-125">이벤트</span><span class="sxs-lookup"><span data-stu-id="028c2-125">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="028c2-126">다중 스레드 응용 프로그램(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="028c2-126">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="028c2-127">대리자</span><span class="sxs-lookup"><span data-stu-id="028c2-127">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="028c2-128">구성 요소에서 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="028c2-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
