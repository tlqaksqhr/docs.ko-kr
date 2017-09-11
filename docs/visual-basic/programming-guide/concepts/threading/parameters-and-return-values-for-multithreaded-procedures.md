---
title: "매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic) | Microsoft 문서"
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
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6d1eb53454b6e0d964be15df2e320ce189e7d875
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="02bdd-102">매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02bdd-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="02bdd-103">다중 스레드 응용 프로그램에서 값을 반환 하 고은 thread 클래스의 생성자에 인수를 사용 하지 아무 값도 반환 하는 프로시저에 대 한 참조를 전달 해야 하기 때문에 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="02bdd-104">다음 단원에서는 매개 변수를 제공 하 고 별도 스레드에서 프로시저에서 값을 반환 하려면 몇 가지 간단한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="02bdd-105">다중 스레드 프로시저의 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="02bdd-106">다중 스레드 메서드 호출에 대 한 매개 변수를 제공할 클래스에서 대상 메서드를 래핑하고 새 스레드에 대 한 매개 변수로 사용할 해당 클래스에 대 한 필드를 정의 하는 가장 좋은 방법은 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="02bdd-107">이 방식의 장점은 될 때마다 새 스레드를 시작 하려면 자체 매개 변수를 사용 하는 클래스의 새 인스턴스를을 만들 수는 한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="02bdd-108">예를 들어 다음 코드 에서처럼 삼각형의 영역을 계산 하는 함수를 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="02bdd-109">래핑하는 클래스를 작성할 수는 `CalcArea` 함수를 다음과 같이 입력된 매개 변수를 저장 하는 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="02bdd-110">사용 하는 `AreaClass`를 만들 수는 `AreaClass` 개체를 설정는 `Base` 및 `Height` 속성을 다음 코드와 같이:</span><span class="sxs-lookup"><span data-stu-id="02bdd-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="02bdd-111">다음에 유의 `TestArea` 프로시저의 값을 확인 하지 않습니다는 `Area` 호출한 후 필드는 `CalcArea` 메서드.</span><span class="sxs-lookup"><span data-stu-id="02bdd-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="02bdd-112">때문에 `CalcArea` 별도 스레드에서 실행 되는 `Area` 필드를 호출한 후 바로 확인 하는 경우 설정할 보장이 없습니다 `Thread.Start`합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="02bdd-113">다음 섹션에서는 다중 스레드 프로시저에서 값을 반환 하는 더 나은 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="02bdd-114">다중 스레드 프로시저에서 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="02bdd-115">절차 함수 일 수 있으며 사용할 수 없습니다 때문에 복잡는 별도 스레드에서 실행 되는 프로시저에서 값을 반환 `ByRef` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="02bdd-116">값을 반환 하는 가장 쉬운 방법은 사용 하는 것은 <xref:System.ComponentModel.BackgroundWorker>구성 하 여 스레드를 관리 하 고 작업이 완료 되 면 이벤트를 발생 한 이벤트 처리기로 결과 처리 합니다.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="02bdd-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="02bdd-117">다음 예제에서는 별도 스레드에서 실행 되는 프로시저에서 이벤트 발생 하 여 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="02bdd-118">매개 변수를 제공 하 고 반환 값 옵션을 사용 하 여 스레드 풀의 스레드 `ByVal` 의 개체 상태 변수는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>메서드.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="02bdd-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="02bdd-119">스레드 타이머 스레드는 또한이 목적을 위해 상태 개체를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="02bdd-120">스레드 풀링 및 스레드 타이머에 대 한 자세한 내용은 참조 [스레드 풀링 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[스레드 풀링](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) 및 [스레드 타이머 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02bdd-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02bdd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02bdd-121">See Also</span></span>  
 <span data-ttu-id="02bdd-122">[연습: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-122">[Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span></span>  
<span data-ttu-id="02bdd-123"> [스레드 풀링 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-123"> [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
<span data-ttu-id="02bdd-124"> [스레드 동기화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-124"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="02bdd-125"> [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-125"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="02bdd-126"> [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-126"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="02bdd-127"> [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="02bdd-127"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="02bdd-128"> [구성 요소에서 다중 스레딩](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span><span class="sxs-lookup"><span data-stu-id="02bdd-128"> [Multithreading in Components](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span></span>
