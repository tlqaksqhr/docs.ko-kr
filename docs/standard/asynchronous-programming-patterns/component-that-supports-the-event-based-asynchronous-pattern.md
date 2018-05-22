---
title: '연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
ms.openlocfilehash: 9156a538e306fb8657855a840dd8185cef8794b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a><span data-ttu-id="8024b-102">연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-102">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="8024b-103">상당한 지연을 일으킬 수 있는 몇 가지 작업을 사용하여 클래스를 작성하는 경우 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 구현하여 비동기 기능을 부여하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
 <span data-ttu-id="8024b-104">이 연습에서는 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-104">This walkthrough illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="8024b-105">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 콘솔 응용 프로그램 및 Windows Forms 응용 프로그램을 포함한 모든 응용 프로그램 모델에서 구성 요소가 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-105">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model, including [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Console applications and Windows Forms applications.</span></span> <span data-ttu-id="8024b-106">이 구성 요소도 <xref:System.Windows.Forms.PropertyGrid> 컨트롤과 고유한 사용자 지정 디자이너를 사용하여 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-106">This component is also designable with a <xref:System.Windows.Forms.PropertyGrid> control and your own custom designers.</span></span>  
  
 <span data-ttu-id="8024b-107">완료하면 소수를 비동기적으로 계산하는 응용 프로그램이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-107">When you are through, you will have an application that computes prime numbers asynchronously.</span></span> <span data-ttu-id="8024b-108">응용 프로그램에는 기본 UI(사용자 인터페이스) 스레드 및 각 소수는 계산을 위한 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-108">Your application will have a main user interface (UI) thread and a thread for each prime number calculation.</span></span> <span data-ttu-id="8024b-109">큰 숫자가 소수인지 테스트하는 데는 상당한 시간이 걸릴 수도 있지만 이 지연으로 기본 UI 스레드가 중단되지 않으며 계산 중에도 폼이 빠르게 응답하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-109">Although testing whether a large number is prime can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculations.</span></span> <span data-ttu-id="8024b-110">원하는 계산 수만큼 동시에 또는 선택적으로 취소 보류 계산을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-110">You will be able to run as many calculations as you like concurrently and selectively cancel pending calculations.</span></span>  
  
 <span data-ttu-id="8024b-111">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="8024b-112">구성 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="8024b-112">Creating the Component</span></span>  
  
-   <span data-ttu-id="8024b-113">공용 비동기 이벤트 및 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="8024b-113">Defining Public Asynchronous Events and Delegates</span></span>  
  
-   <span data-ttu-id="8024b-114">전용 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="8024b-114">Defining Private Delegates</span></span>  
  
-   <span data-ttu-id="8024b-115">공용 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-115">Implementing Public Events</span></span>  
  
-   <span data-ttu-id="8024b-116">완료 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-116">Implementing the Completion Method</span></span>  
  
-   <span data-ttu-id="8024b-117">작업자 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-117">Implementing the Worker Methods</span></span>  
  
-   <span data-ttu-id="8024b-118">시작 및 취소 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-118">Implementing Start and Cancel Methods</span></span>  
  
 <span data-ttu-id="8024b-119">이 항목의 코드를 단일 목록으로 복사하려면 [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)(방법: 이벤트 기반 비동기 패턴의 클라이언트 구현)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8024b-119">To copy the code in this topic as a single listing, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="creating-the-component"></a><span data-ttu-id="8024b-120">구성 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="8024b-120">Creating the Component</span></span>  
 <span data-ttu-id="8024b-121">첫 번째 단계는 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-121">The first step is to create the component that will implement the Event-based Asynchronous Pattern.</span></span>  
  
#### <a name="to-create-the-component"></a><span data-ttu-id="8024b-122">구성 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8024b-122">To create the component</span></span>  
  
-   <span data-ttu-id="8024b-123"><xref:System.ComponentModel.Component>에서 상속되는 `PrimeNumberCalculator`라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-123">Create a class called `PrimeNumberCalculator` that inherits from <xref:System.ComponentModel.Component>.</span></span>  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a><span data-ttu-id="8024b-124">공용 비동기 이벤트 및 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="8024b-124">Defining Public Asynchronous Events and Delegates</span></span>  
 <span data-ttu-id="8024b-125">구성 요소는 이벤트를 사용하는 클라이언트와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-125">Your component communicates to clients using events.</span></span> <span data-ttu-id="8024b-126">*MethodName***Completed** 이벤트는 클라이언트에 비동기 작업의 완료를 알리고 *MethodName***ProgressChanged** 이벤트는 클라이언트에 비동기 작업의 진행률을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-126">The *MethodName***Completed** event alerts clients to the completion of an asynchronous task, and the *MethodName***ProgressChanged** event informs clients of the progress of an asynchronous task.</span></span>  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a><span data-ttu-id="8024b-127">구성 요소의 클라이언트에 대한 비동기 이벤트를 정의하려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-127">To define asynchronous events for clients of your component:</span></span>  
  
1.  <span data-ttu-id="8024b-128"><xref:System.Threading?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized?displayProperty=nameWithType> 네임스페이스를 파일 맨 위로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-128">Import the <xref:System.Threading?displayProperty=nameWithType> and <xref:System.Collections.Specialized?displayProperty=nameWithType> namespaces at the top of your file.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  <span data-ttu-id="8024b-129">`PrimeNumberCalculator` 클래스 정의 전에 진행률 및 완료 이벤트에 대한 대리자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-129">Before the `PrimeNumberCalculator` class definition, declare delegates for progress and completion events.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  <span data-ttu-id="8024b-130">`PrimeNumberCalculator` 클래스 정의에서 클라이언트에 진행률 및 완료를 보고하는 이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-130">In the `PrimeNumberCalculator` class definition, declare events for reporting progress and completion to clients.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  <span data-ttu-id="8024b-131">`PrimeNumberCalculator` 클래스 정의 후 각 계산의 결과를 `CalculatePrimeCompleted`.event에 대한 클라이언트 이벤트 처리기에 보고하기 위해 `CalculatePrimeCompletedEventArgs` 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-131">After the `PrimeNumberCalculator` class definition, derive the `CalculatePrimeCompletedEventArgs` class for reporting the outcome of each calculation to the client's event handler for the `CalculatePrimeCompleted`.event.</span></span> <span data-ttu-id="8024b-132">`AsyncCompletedEventArgs` 속성 외에도 이 클래스를 사용하면 클라이언트가 테스트된 숫자, 숫자가 소수인지 여부 및 소수가 아닌 경우 첫 번째 제수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-132">In addition to the `AsyncCompletedEventArgs` properties, this class enables the client to determine what number was tested, whether it is prime, and what the first divisor is if it is not prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a><span data-ttu-id="8024b-133">검사점</span><span class="sxs-lookup"><span data-stu-id="8024b-133">Checkpoint</span></span>  
 <span data-ttu-id="8024b-134">이때 구성 요소를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-134">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="8024b-135">구성 요소를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8024b-135">To test your component</span></span>  
  
-   <span data-ttu-id="8024b-136">구성 요소를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-136">Compile the component.</span></span>  
  
     <span data-ttu-id="8024b-137">두 개의 컴파일러 경고를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-137">You will receive two compiler warnings:</span></span>  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     <span data-ttu-id="8024b-138">이러한 경고는 다음 섹션에서 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-138">These warnings will be cleared in the next section.</span></span>  
  
## <a name="defining-private-delegates"></a><span data-ttu-id="8024b-139">전용 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="8024b-139">Defining Private Delegates</span></span>  
 <span data-ttu-id="8024b-140">`PrimeNumberCalculator` 구성 요소의 비동기 측면은 <xref:System.Threading.SendOrPostCallback>으로 알려진 특수 대리자를 사용하여 내부적으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-140">The asynchronous aspects of the `PrimeNumberCalculator` component are implemented internally with a special delegate known as a <xref:System.Threading.SendOrPostCallback>.</span></span> <span data-ttu-id="8024b-141"><xref:System.Threading.SendOrPostCallback>은 <xref:System.Threading.ThreadPool> 스레드에서 실행되는 콜백 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-141">A <xref:System.Threading.SendOrPostCallback> represents a callback method that executes on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="8024b-142">콜백 메서드에는 <xref:System.Object> 형식의 단일 매개 변수를 사용하는 시그니처가 있어야 합니다. 즉, 래퍼 클래스의 대리자 간에 상태를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-142">The callback method must have a signature that takes a single parameter of type <xref:System.Object>, which means you will need to pass state among delegates in a wrapper class.</span></span> <span data-ttu-id="8024b-143">자세한 내용은 <xref:System.Threading.SendOrPostCallback>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8024b-143">For more information, see <xref:System.Threading.SendOrPostCallback>.</span></span>  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a><span data-ttu-id="8024b-144">구성 요소의 내부 비동기 동작을 구현하려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-144">To implement your component's internal asynchronous behavior:</span></span>  
  
1.  <span data-ttu-id="8024b-145">`PrimeNumberCalculator` 클래스에 <xref:System.Threading.SendOrPostCallback> 대리자를 선언하고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-145">Declare and create the <xref:System.Threading.SendOrPostCallback> delegates in the `PrimeNumberCalculator` class.</span></span> <span data-ttu-id="8024b-146">`InitializeDelegates`라는 유틸리티 메서드에서 <xref:System.Threading.SendOrPostCallback> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-146">Create the <xref:System.Threading.SendOrPostCallback> objects in a utility method called `InitializeDelegates`.</span></span>  
  
     <span data-ttu-id="8024b-147">각각 클라이언트에 진행률 및 완료를 보고하는 두 개의 대리자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-147">You will need two delegates: one for reporting progress to the client, and one for reporting completion to the client.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  <span data-ttu-id="8024b-148">구성 요소의 생성자에서 `InitializeDelegates` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-148">Call the `InitializeDelegates` method in your component's constructor.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  <span data-ttu-id="8024b-149">`PrimeNumberCalculator` 클래스에서 실제 작업이 비동기적으로 수행되도록 처리하는 대리자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-149">Declare a delegate in the `PrimeNumberCalculator` class that handles the actual work to be done asynchronously.</span></span> <span data-ttu-id="8024b-150">이 대리자는 숫자가 소수인지 테스트하는 작업자 메서드를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-150">This delegate wraps the worker method that tests whether a number is prime.</span></span> <span data-ttu-id="8024b-151">대리자는 비동기 작업의 수명을 추적하는 데 사용되는 <xref:System.ComponentModel.AsyncOperation> 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-151">The delegate takes an <xref:System.ComponentModel.AsyncOperation> parameter, which will be used to track the lifetime of the asynchronous operation.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  <span data-ttu-id="8024b-152">보류 중인 비동기 작업의 수명을 관리하기 위한 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-152">Create a collection for managing lifetimes of pending asynchronous operations.</span></span> <span data-ttu-id="8024b-153">클라이언트에는 실행 및 완료 시 작업을 추적하는 방법이 필요하며, 이 추적을 수행하려면 클라이언트가 비동기 메서드를 호출할 때 고유한 토큰 또는 작업 ID를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-153">The client needs a way to track operations as they are executed and completed, and this tracking is done by requiring the client to pass a unique token, or task ID, when the client makes the call to the asynchronous method.</span></span> <span data-ttu-id="8024b-154">`PrimeNumberCalculator` 구성 요소는 작업 ID를 해당 호출과 연결하여 각 호출을 추적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-154">The `PrimeNumberCalculator` component must keep track of each call by associating the task ID with its corresponding invocation.</span></span> <span data-ttu-id="8024b-155">클라이언트가 고유하지 않은 작업 ID를 전달하면 `PrimeNumberCalculator` 구성 요소가 예외를 발생시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-155">If the client passes a task ID that is not unique, the `PrimeNumberCalculator` component must raise an exception.</span></span>  
  
     <span data-ttu-id="8024b-156">`PrimeNumberCalculator` 구성 요소는 <xref:System.Collections.Specialized.HybridDictionary>라는 특수 컬렉션 클래스를 사용하여 작업 ID를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-156">The `PrimeNumberCalculator` component keeps track of task ID by using a special collection class called a <xref:System.Collections.Specialized.HybridDictionary>.</span></span> <span data-ttu-id="8024b-157">클래스 정의에서 `userTokenToLifetime`이라는 <xref:System.Collections.Specialized.HybridDictionary>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-157">In the class definition, create a <xref:System.Collections.Specialized.HybridDictionary> called `userTokenToLifetime`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a><span data-ttu-id="8024b-158">공용 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-158">Implementing Public Events</span></span>  
 <span data-ttu-id="8024b-159">이벤트 기반 비동기 패턴을 구현하는 구성 요소는 이벤트를 사용하는 클라이언트와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-159">Components that implement the Event-based Asynchronous Pattern communicate to clients using events.</span></span> <span data-ttu-id="8024b-160">이러한 이벤트는 <xref:System.ComponentModel.AsyncOperation> 클래스를 통해 적절한 스레드에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-160">These events are invoked on the proper thread with the help of the <xref:System.ComponentModel.AsyncOperation> class.</span></span>  
  
#### <a name="to-raise-events-to-your-components-clients"></a><span data-ttu-id="8024b-161">구성 요소의 클라이언트에 이벤트를 발생시키려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-161">To raise events to your component's clients:</span></span>  
  
1.  <span data-ttu-id="8024b-162">클라이언트에 보고할 공용 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-162">Implement public events for reporting to clients.</span></span> <span data-ttu-id="8024b-163">각각 진행률 및 완료를 보고하기 위한 두 개의 이벤트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-163">You will need an event for reporting progress and one for reporting completion.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a><span data-ttu-id="8024b-164">완료 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-164">Implementing the Completion Method</span></span>  
 <span data-ttu-id="8024b-165">완료 대리자는 비동기 작업이 성공적인 완료, 오류 또는 취소로 종료될 경우 기본적인 자유 스레드 비동기 동작이 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-165">The completion delegate is the method that the underlying, free-threaded asynchronous behavior will invoke when the asynchronous operation ends by successful completion, error, or cancellation.</span></span> <span data-ttu-id="8024b-166">이 호출은 임의 스레드에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-166">This invocation happens on an arbitrary thread.</span></span>  
  
 <span data-ttu-id="8024b-167">이 메서드는 클라이언트의 작업 ID가 고유한 클라이언트 토큰의 내부 컬렉션에서 제거되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-167">This method is where the client's task ID is removed from the internal collection of unique client tokens.</span></span> <span data-ttu-id="8024b-168">또한 이 메서드는 해당 <xref:System.ComponentModel.AsyncOperation>에서 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드를 호출하여 특정 비동기 작업의 수명을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-168">This method also ends the lifetime of a particular asynchronous operation by calling the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method on the corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="8024b-169">이 호출은 응용 프로그램 모델에 적절한 스레드에서 완료 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-169">This call raises the completion event on the thread that is appropriate for the application model.</span></span> <span data-ttu-id="8024b-170"><xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드를 호출한 후에는 <xref:System.ComponentModel.AsyncOperation>의 이 인스턴스를 더 이상 사용할 수 없고 이후에 이를 사용하려고 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-170">After the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method is called, this instance of <xref:System.ComponentModel.AsyncOperation> can no longer be used, and any subsequent attempts to use it will throw an exception.</span></span>  
  
 <span data-ttu-id="8024b-171">`CompletionMethod` 시그니처는 비동기 작업의 결과를 설명하는 데 필요한 모든 상태를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-171">The `CompletionMethod` signature must hold all state necessary to describe the outcome of the asynchronous operation.</span></span> <span data-ttu-id="8024b-172">이 시그니처는 이 특정 비동기 작업으로 테스트된 숫자의 상태, 숫자가 소수인지 여부 및 소수가 아닌 경우 첫 번째 제수의 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-172">It holds state for the number that was tested by this particular asynchronous operation, whether the number is prime, and the value of its first divisor if it is not a prime number.</span></span> <span data-ttu-id="8024b-173">또한 발생한 예외를 설명하는 상태 및 이 특정 작업에 해당하는 <xref:System.ComponentModel.AsyncOperation>을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-173">It also holds state describing any exception that occurred, and the <xref:System.ComponentModel.AsyncOperation> corresponding to this particular task.</span></span>  
  
#### <a name="to-complete-an-asynchronous-operation"></a><span data-ttu-id="8024b-174">비동기 작업을 완료하려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-174">To complete an asynchronous operation:</span></span>  
  
-   <span data-ttu-id="8024b-175">완료 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-175">Implement the completion method.</span></span> <span data-ttu-id="8024b-176">이 메서드는 클라이언트의 `CalculatePrimeCompletedEventHandler`를 통해 클라이언트로 반환되는 `CalculatePrimeCompletedEventArgs`를 채우는 데 사용할 6개의 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-176">It takes six parameters, which it uses to populate a `CalculatePrimeCompletedEventArgs` that is returned to the client through the client's `CalculatePrimeCompletedEventHandler`.</span></span> <span data-ttu-id="8024b-177">이 메서드는 내부 컬렉션에서 클라이언트의 작업 ID 토큰을 제거하고 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 호출을 통해 비동기 작업 수명을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-177">It removes the client's task ID token from the internal collection, and it ends the asynchronous operation's lifetime with a call to <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>.</span></span> <span data-ttu-id="8024b-178"><xref:System.ComponentModel.AsyncOperation>은 응용 프로그램 모델에 적합한 스레드 또는 컨텍스트에 대한 호출을 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-178">The <xref:System.ComponentModel.AsyncOperation> marshals the call to the thread or context that is appropriate for the application model.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a><span data-ttu-id="8024b-179">검사점</span><span class="sxs-lookup"><span data-stu-id="8024b-179">Checkpoint</span></span>  
 <span data-ttu-id="8024b-180">이때 구성 요소를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-180">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="8024b-181">구성 요소를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8024b-181">To test your component</span></span>  
  
-   <span data-ttu-id="8024b-182">구성 요소를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-182">Compile the component.</span></span>  
  
     <span data-ttu-id="8024b-183">하나의 컴파일러 경고를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-183">You will receive one compiler warning:</span></span>  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     <span data-ttu-id="8024b-184">이 경고는 다음 섹션에서 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-184">This warning will be resolved in the next section.</span></span>  
  
## <a name="implementing-the-worker-methods"></a><span data-ttu-id="8024b-185">작업자 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-185">Implementing the Worker Methods</span></span>  
 <span data-ttu-id="8024b-186">지금까지 `PrimeNumberCalculator` 구성 요소에 대해 지원되는 비동기 코드를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-186">So far, you have implemented the supporting asynchronous code for the `PrimeNumberCalculator` component.</span></span> <span data-ttu-id="8024b-187">이제 실제 작업을 수행하는 코드를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-187">Now you can implement the code that does the actual work.</span></span> <span data-ttu-id="8024b-188">세 가지 메서드 `CalculateWorker` , `BuildPrimeNumberList` 및 `IsPrime`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-188">You will implement three methods: `CalculateWorker`, `BuildPrimeNumberList`, and `IsPrime`.</span></span> <span data-ttu-id="8024b-189">`BuildPrimeNumberList` 및 `IsPrime`은 함께 테스트 숫자의 제곱근까지 모든 소수를 찾아서 숫자가 소수인지 확인하는 에라토스테네스의 체라는 잘 알려진 알고리즘을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-189">Together, `BuildPrimeNumberList` and `IsPrime` comprise a well-known algorithm called the Sieve of Eratosthenes, which determines if a number is prime by finding all the prime numbers up to the square root of the test number.</span></span> <span data-ttu-id="8024b-190">해당 지점에서 제수를 찾을 수 없으면 테스트 숫자는 소수입니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-190">If no divisors are found by that point, the test number is prime.</span></span>  
  
 <span data-ttu-id="8024b-191">효율성 최대화를 위해 이 구성 요소를 작성한 경우 이 구성 요소는 여러 테스트 숫자에 대한 다양한 호출을 통해 검색된 모든 소수를 기억합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-191">If this component were written for maximum efficiency, it would remember all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="8024b-192">2, 3, 5와 같은 사소한 제수도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-192">It would also check for trivial divisors like 2, 3, and 5.</span></span> <span data-ttu-id="8024b-193">그러나 이 예제의 목적은 시간이 오래 걸리는 작업을 비동기적으로 실행하는 방법을 보여주는 것이므로 이러한 최적화는 연습용으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-193">The intent of this example is to demonstrate how time-consuming operations can be executed asynchronously, however, so these optimizations are left as an exercise for you.</span></span>  
  
 <span data-ttu-id="8024b-194">`CalculateWorker` 메서드는 대리자로 래핑되고 `BeginInvoke` 호출을 통해 비동기적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-194">The `CalculateWorker` method is wrapped in a delegate and is invoked asynchronously with a call to `BeginInvoke`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8024b-195">진행률 보고는 `BuildPrimeNumberList` 메서드에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-195">Progress reporting is implemented in the `BuildPrimeNumberList` method.</span></span> <span data-ttu-id="8024b-196">빠른 컴퓨터에서는 `ProgressChanged` 이벤트가 연속적으로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-196">On fast computers, `ProgressChanged` events can be raised in rapid succession.</span></span> <span data-ttu-id="8024b-197">이러한 이벤트가 발생하는 클라이언트 스레드에서 이 상황을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-197">The client thread, on which these events are raised, must be able to handle this situation.</span></span> <span data-ttu-id="8024b-198">사용자 인터페이스 코드가 메시지로 넘치는데 유지할 수 없어서 동작이 멈출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-198">User interface code may be flooded with messages and unable to keep up, resulting in hanging behavior.</span></span> <span data-ttu-id="8024b-199">이 상황을 처리하는 예제 사용자 인터페이스는 [방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8024b-199">For an example user interface that handles this situation, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a><span data-ttu-id="8024b-200">소수 계산을 비동기적으로 실행하려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-200">To execute the prime number calculation asynchronously:</span></span>  
  
1.  <span data-ttu-id="8024b-201">`TaskCanceled` 유틸리티 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-201">Implement the `TaskCanceled` utility method.</span></span> <span data-ttu-id="8024b-202">이 메서드는 지정된 작업 ID의 작업 수명 컬렉션을 확인하고 작업 ID를 찾을 수 없는 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-202">This checks the task lifetime collection for the given task ID, and returns `true` if the task ID is not found.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  <span data-ttu-id="8024b-203">`CalculateWorker` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-203">Implement the `CalculateWorker` method.</span></span> <span data-ttu-id="8024b-204">이 메서드는 두 개의 매개 변수인 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-204">It takes two parameters: a number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  <span data-ttu-id="8024b-205">`BuildPrimeNumberList`를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-205">Implement `BuildPrimeNumberList`.</span></span> <span data-ttu-id="8024b-206">이 메서드는 두 개의 매개 변수인 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-206">It takes two parameters: the number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="8024b-207"><xref:System.ComponentModel.AsyncOperation>을 사용하여 진행률 및 증분 결과를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-207">It uses the <xref:System.ComponentModel.AsyncOperation> to report progress and incremental results.</span></span> <span data-ttu-id="8024b-208">이 메서드를 사용하면 클라이언트의 이벤트 처리기가 응용 프로그램 모델에 대한 적절한 스레드 또는 컨텍스트에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-208">This assures that the client's event handlers are called on the proper thread or context for the application model.</span></span> <span data-ttu-id="8024b-209">`BuildPrimeNumberList`는 소수를 찾을 경우 `ProgressChanged` 이벤트에 대한 클라이언트 이벤트 처리기에 이 소수를 증분 결과로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-209">When `BuildPrimeNumberList` finds a prime number, it reports this as an incremental result to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="8024b-210">이 작업에는 `LatestPrimeNumber`라는 하나의 추가된 속성을 포함하는 `CalculatePrimeProgressChangedEventArgs`라는 <xref:System.ComponentModel.ProgressChangedEventArgs>에서 파생된 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-210">This requires a class derived from <xref:System.ComponentModel.ProgressChangedEventArgs>, called `CalculatePrimeProgressChangedEventArgs`, which has one added property called `LatestPrimeNumber`.</span></span>  
  
     <span data-ttu-id="8024b-211">또한 `BuildPrimeNumberList` 메서드는 `TaskCanceled` 메서드를 정기적으로 호출하고 메서드가 `true`를 반환하는 경우 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-211">The `BuildPrimeNumberList` method also periodically calls the `TaskCanceled` method and exits if the method returns `true`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  <span data-ttu-id="8024b-212">`IsPrime`를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-212">Implement `IsPrime`.</span></span> <span data-ttu-id="8024b-213">이 메서드는 세 개의 매개 변수인 알려진 소수 목록, 테스트할 숫자 및 발견된 첫 번째 제수의 출력 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-213">It takes three parameters: a list of known prime numbers, the number to test, and an output parameter for the first divisor found.</span></span> <span data-ttu-id="8024b-214">소수 목록이 제공된 경우 테스트 숫자가 소수인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-214">Given the list of prime numbers, it determines if the test number is prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  <span data-ttu-id="8024b-215"><xref:System.ComponentModel.ProgressChangedEventArgs>에서 `CalculatePrimeProgressChangedEventArgs`를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-215">Derive `CalculatePrimeProgressChangedEventArgs` from <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span> <span data-ttu-id="8024b-216">이 클래스는 `ProgressChanged` 이벤트에 대한 클라이언트 이벤트 처리기에 증분 결과를 보고하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-216">This class is necessary for reporting incremental results to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="8024b-217">`LatestPrimeNumber`라는 하나의 추가된 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-217">It has one added property called `LatestPrimeNumber`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a><span data-ttu-id="8024b-218">검사점</span><span class="sxs-lookup"><span data-stu-id="8024b-218">Checkpoint</span></span>  
 <span data-ttu-id="8024b-219">이때 구성 요소를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-219">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="8024b-220">구성 요소를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8024b-220">To test your component</span></span>  
  
-   <span data-ttu-id="8024b-221">구성 요소를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-221">Compile the component.</span></span>  
  
     <span data-ttu-id="8024b-222">계속해서 비동기 작업을 시작 및 취소하는 `CalculatePrimeAsync` 및 `CancelAsync` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-222">All that remains to be written are the methods to start and cancel asynchronous operations, `CalculatePrimeAsync` and `CancelAsync`.</span></span>  
  
## <a name="implementing-the-start-and-cancel-methods"></a><span data-ttu-id="8024b-223">시작 및 취소 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-223">Implementing the Start and Cancel Methods</span></span>  
 <span data-ttu-id="8024b-224">메서드를 래핑하는 대리자에서 `BeginInvoke`를 호출하여 자체 스레드에서 작업자 메서드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-224">You start the worker method on its own thread by calling `BeginInvoke` on the delegate that wraps it.</span></span> <span data-ttu-id="8024b-225">특정 비동기 작업의 수명을 관리하려면 <xref:System.ComponentModel.AsyncOperationManager> 도우미 클래스에서 <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-225">To manage the lifetime of a particular asynchronous operation, you call the <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> method on the <xref:System.ComponentModel.AsyncOperationManager> helper class.</span></span> <span data-ttu-id="8024b-226">이렇게 하면 클라이언트의 이벤트 처리기에 대한 호출을 올바른 스레드 또는 컨텍스트로 마샬링하는 <xref:System.ComponentModel.AsyncOperation>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-226">This returns an <xref:System.ComponentModel.AsyncOperation>, which marshals calls on the client's event handlers to the proper thread or context.</span></span>  
  
 <span data-ttu-id="8024b-227">해당 <xref:System.ComponentModel.AsyncOperation>에서 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>를 호출하여 특정 보류 작업을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-227">You cancel a particular pending operation by calling <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> on its corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="8024b-228">이렇게 하면 해당 작업이 종료되고 이후에 <xref:System.ComponentModel.AsyncOperation>을 호출하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-228">This ends that operation, and any subsequent calls to its <xref:System.ComponentModel.AsyncOperation> will throw an exception.</span></span>  
  
#### <a name="to-implement-start-and-cancel-functionality"></a><span data-ttu-id="8024b-229">시작 및 취소 기능을 구현하려면:</span><span class="sxs-lookup"><span data-stu-id="8024b-229">To implement Start and Cancel functionality:</span></span>  
  
1.  <span data-ttu-id="8024b-230">`CalculatePrimeAsync` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-230">Implement the `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="8024b-231">클라이언트 제공 토큰(작업 ID)이 현재 보류 중인 작업을 나타내는 모든 토큰에 관련해서 고유한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-231">Make sure the client-supplied token (task ID) is unique with respect to all the tokens representing currently pending tasks.</span></span> <span data-ttu-id="8024b-232">클라이언트가 고유하지 않은 토큰으로 전달되면 `CalculatePrimeAsync`가 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-232">If the client passes in a non-unique token, `CalculatePrimeAsync` raises an exception.</span></span> <span data-ttu-id="8024b-233">그렇지 않으면 토큰이 작업 ID 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-233">Otherwise, the token is added to the task ID collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  <span data-ttu-id="8024b-234">`CancelAsync` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-234">Implement the `CancelAsync` method.</span></span> <span data-ttu-id="8024b-235">`taskId` 매개 변수가 토큰 컬렉션에 있는 경우 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-235">If the `taskId` parameter exists in the token collection, it is removed.</span></span> <span data-ttu-id="8024b-236">이렇게 하면 취소된 작업의 실행이 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-236">This prevents canceled tasks that have not started from running.</span></span> <span data-ttu-id="8024b-237">작업이 실행 중인 경우 `BuildPrimeNumberList` 메서드는 해당 작업 ID가 수명 컬렉션에서 제거되었음을 감지할 때 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-237">If the task is running, the `BuildPrimeNumberList` method exits when it detects that the task ID has been removed from the lifetime collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a><span data-ttu-id="8024b-238">검사점</span><span class="sxs-lookup"><span data-stu-id="8024b-238">Checkpoint</span></span>  
 <span data-ttu-id="8024b-239">이때 구성 요소를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-239">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="8024b-240">구성 요소를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8024b-240">To test your component</span></span>  
  
-   <span data-ttu-id="8024b-241">구성 요소를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-241">Compile the component.</span></span>  
  
 <span data-ttu-id="8024b-242">이제 `PrimeNumberCalculator` 구성 요소가 완료되고 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-242">The `PrimeNumberCalculator` component is now complete and ready to use.</span></span>  
  
 <span data-ttu-id="8024b-243">`PrimeNumberCalculator` 구성 요소를 사용하는 예제 클라이언트는 [방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8024b-243">For an example client that uses the `PrimeNumberCalculator` component, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8024b-244">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8024b-244">Next Steps</span></span>  
 <span data-ttu-id="8024b-245">`CalculatePrimeAsync` 메서드의 동기 메서드인 `CalculatePrime`을 작성하여 이 예제를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-245">You can fill out this example by writing `CalculatePrime`, the synchronous equivalent of `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="8024b-246">이렇게 하면 `PrimeNumberCalculator` 구성 요소가 이벤트 기반 비동기 패턴을 완전히 준수하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-246">This will make the `PrimeNumberCalculator` component fully compliant with the Event-based Asynchronous Pattern.</span></span>  
  
 <span data-ttu-id="8024b-247">여러 테스트 숫자에 대한 다양한 호출을 통해 검색된 모든 소수 목록을 유지하면 이 예제를 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-247">You can improve this example by retaining the list of all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="8024b-248">이 방법을 사용하면 각 작업이 이전 작업에서 수행된 작업을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-248">Using this approach, each task will benefit from the work done by previous tasks.</span></span> <span data-ttu-id="8024b-249">이 목록을 `lock` 영역으로 보호하면 여러 스레드에 의한 목록 액세스가 직렬화되므로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-249">Be careful to protect this list with `lock` regions, so access to the list by different threads is serialized.</span></span>  
  
 <span data-ttu-id="8024b-250">2, 3, 5와 같은 사소한 제수를 테스트하여 이 예제를 향상할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8024b-250">You can also improve this example by testing for trivial divisors, like 2, 3, and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8024b-251">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8024b-251">See Also</span></span>  
 [<span data-ttu-id="8024b-252">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="8024b-252">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="8024b-253">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="8024b-253">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="8024b-254">빌드에 없음: Visual Basic의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="8024b-254">NOT IN BUILD: Multithreading in Visual Basic</span></span>](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="8024b-255">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="8024b-255">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="8024b-256">이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8024b-256">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
