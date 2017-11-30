---
title: "연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a><span data-ttu-id="6fefc-102">연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-102">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="6fefc-103">구현 하 여 비동기 기능을 제공할 상당한 지연을 일으킬 수 있는 일부 작업을 사용 하 여 클래스를 작성 하는 경우 고려는 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
 <span data-ttu-id="6fefc-104">이 연습에서는 이벤트 기반 비동기 패턴을 구현 하는 구성 요소를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-104">This walkthrough illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="6fefc-105">도우미 클래스를 사용 하는 것의 <xref:System.ComponentModel?displayProperty=nameWithType> 구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동 하도록 보장을 하는 네임 스페이스를 포함 하 여 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 콘솔 응용 프로그램 및 Windows Forms 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-105">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model, including [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Console applications and Windows Forms applications.</span></span> <span data-ttu-id="6fefc-106">이 구성 요소를 디자인할 수 이기도 한 <xref:System.Windows.Forms.PropertyGrid> 제어 및 사용자 고유의 사용자 지정 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-106">This component is also designable with a <xref:System.Windows.Forms.PropertyGrid> control and your own custom designers.</span></span>  
  
 <span data-ttu-id="6fefc-107">을 통해 때 비동기적으로 소수를 계산 하는 응용 프로그램을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-107">When you are through, you will have an application that computes prime numbers asynchronously.</span></span> <span data-ttu-id="6fefc-108">응용 프로그램은 각 소수 계산에 대 한 스레드 및 기본 사용자 인터페이스 (UI) 스레드를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-108">Your application will have a main user interface (UI) thread and a thread for each prime number calculation.</span></span> <span data-ttu-id="6fefc-109">많은 수 인지를 테스트 하지만 prime 상당한 시간이 걸릴 수 있습니다, 이러한 지연에 의해 주 UI 스레드를 중단 되지 않습니다 하 고 계산 하는 동안 폼 응답 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-109">Although testing whether a large number is prime can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculations.</span></span> <span data-ttu-id="6fefc-110">보류 중인 계산 취소 하 고 선택적으로 동시에 원하는 만큼 많은 계산을 실행할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-110">You will be able to run as many calculations as you like concurrently and selectively cancel pending calculations.</span></span>  
  
 <span data-ttu-id="6fefc-111">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="6fefc-112">구성 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="6fefc-112">Creating the Component</span></span>  
  
-   <span data-ttu-id="6fefc-113">공용 비동기 이벤트 및 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="6fefc-113">Defining Public Asynchronous Events and Delegates</span></span>  
  
-   <span data-ttu-id="6fefc-114">전용 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="6fefc-114">Defining Private Delegates</span></span>  
  
-   <span data-ttu-id="6fefc-115">Public 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-115">Implementing Public Events</span></span>  
  
-   <span data-ttu-id="6fefc-116">완료 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-116">Implementing the Completion Method</span></span>  
  
-   <span data-ttu-id="6fefc-117">작업자 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-117">Implementing the Worker Methods</span></span>  
  
-   <span data-ttu-id="6fefc-118">시작 및 취소 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-118">Implementing Start and Cancel Methods</span></span>  
  
 <span data-ttu-id="6fefc-119">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소를 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-119">To copy the code in this topic as a single listing, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="creating-the-component"></a><span data-ttu-id="6fefc-120">구성 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="6fefc-120">Creating the Component</span></span>  
 <span data-ttu-id="6fefc-121">첫 번째 단계는 이벤트 기반 비동기 패턴을 구현 하는 구성 요소를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-121">The first step is to create the component that will implement the Event-based Asynchronous Pattern.</span></span>  
  
#### <a name="to-create-the-component"></a><span data-ttu-id="6fefc-122">구성 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6fefc-122">To create the component</span></span>  
  
-   <span data-ttu-id="6fefc-123">라는 클래스를 만들고 `PrimeNumberCalculator` 에서 상속 되는 <xref:System.ComponentModel.Component>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-123">Create a class called `PrimeNumberCalculator` that inherits from <xref:System.ComponentModel.Component>.</span></span>  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a><span data-ttu-id="6fefc-124">공용 비동기 이벤트 및 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="6fefc-124">Defining Public Asynchronous Events and Delegates</span></span>  
 <span data-ttu-id="6fefc-125">구성 요소 이벤트를 사용 하는 클라이언트와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-125">Your component communicates to clients using events.</span></span> <span data-ttu-id="6fefc-126">*MethodName* `Completed` 이벤트 경고는 비동기 작업을 완료 하는 클라이언트 및 *MethodName* `ProgressChanged` 이벤트는 비동기 작업의 진행률에 대 한 클라이언트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-126">The *MethodName*`Completed` event alerts clients to the completion of an asynchronous task, and the *MethodName*`ProgressChanged` event informs clients of the progress of an asynchronous task.</span></span>  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a><span data-ttu-id="6fefc-127">클라이언트 구성 요소에 대 한 비동기 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-127">To define asynchronous events for clients of your component:</span></span>  
  
1.  <span data-ttu-id="6fefc-128">가져오기는 <xref:System.Threading?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized?displayProperty=nameWithType> 파일의 위쪽에서 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-128">Import the <xref:System.Threading?displayProperty=nameWithType> and <xref:System.Collections.Specialized?displayProperty=nameWithType> namespaces at the top of your file.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  <span data-ttu-id="6fefc-129">전에 `PrimeNumberCalculator` 클래스 정의 진행률 및 완료 이벤트에 대 한 대리자를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-129">Before the `PrimeNumberCalculator` class definition, declare delegates for progress and completion events.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  <span data-ttu-id="6fefc-130">에 `PrimeNumberCalculator` 클래스 정의 보고 진행률 및 완료를 클라이언트에 대 한 이벤트를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-130">In the `PrimeNumberCalculator` class definition, declare events for reporting progress and completion to clients.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  <span data-ttu-id="6fefc-131">후의 `PrimeNumberCalculator` 클래스 정의 파생 시킵니다는 `CalculatePrimeCompletedEventArgs` 보고에 대 한 클라이언트의 이벤트 처리기에 각 계산의 결과 대 한 클래스는 `CalculatePrimeCompleted`시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-131">After the `PrimeNumberCalculator` class definition, derive the `CalculatePrimeCompletedEventArgs` class for reporting the outcome of each calculation to the client's event handler for the `CalculatePrimeCompleted`.event.</span></span> <span data-ttu-id="6fefc-132">이외에 `AsyncCompletedEventArgs` 속성을이 클래스를 통해 클라이언트가 어떤 번호 테스트 됨, 소수 인지 여부 및 첫 번째 제 수 란 주요 하지 않은 경우를 결정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-132">In addition to the `AsyncCompletedEventArgs` properties, this class enables the client to determine what number was tested, whether it is prime, and what the first divisor is if it is not prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a><span data-ttu-id="6fefc-133">검사점</span><span class="sxs-lookup"><span data-stu-id="6fefc-133">Checkpoint</span></span>  
 <span data-ttu-id="6fefc-134">이 시점에서 구성 요소를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-134">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="6fefc-135">구성 요소를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="6fefc-135">To test your component</span></span>  
  
-   <span data-ttu-id="6fefc-136">구성 요소를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fefc-136">Compile the component.</span></span>  
  
     <span data-ttu-id="6fefc-137">두 개의 컴파일러 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-137">You will receive two compiler warnings:</span></span>  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     <span data-ttu-id="6fefc-138">다음 섹션에서 이러한 경고를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-138">These warnings will be cleared in the next section.</span></span>  
  
## <a name="defining-private-delegates"></a><span data-ttu-id="6fefc-139">전용 대리자 정의</span><span class="sxs-lookup"><span data-stu-id="6fefc-139">Defining Private Delegates</span></span>  
 <span data-ttu-id="6fefc-140">비동기 측면에서 `PrimeNumberCalculator` 이라는 특별 한 대리자와 내부적으로 구현 되며 구성 요소는 <xref:System.Threading.SendOrPostCallback>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-140">The asynchronous aspects of the `PrimeNumberCalculator` component are implemented internally with a special delegate known as a <xref:System.Threading.SendOrPostCallback>.</span></span> <span data-ttu-id="6fefc-141">A <xref:System.Threading.SendOrPostCallback> 에서 실행 되는 콜백 메서드를 나타내는 <xref:System.Threading.ThreadPool> 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-141">A <xref:System.Threading.SendOrPostCallback> represents a callback method that executes on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="6fefc-142">콜백 메서드에 형식의 단일 매개 변수를 사용 하는 서명이 있어야 합니다. <xref:System.Object>, 대리자에는 래퍼 클래스 간에 상태를 전달 해야 합니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-142">The callback method must have a signature that takes a single parameter of type <xref:System.Object>, which means you will need to pass state among delegates in a wrapper class.</span></span> <span data-ttu-id="6fefc-143">자세한 내용은 <xref:System.Threading.SendOrPostCallback>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fefc-143">For more information, see <xref:System.Threading.SendOrPostCallback>.</span></span>  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a><span data-ttu-id="6fefc-144">구성 요소의 내부 비동기 동작을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-144">To implement your component's internal asynchronous behavior:</span></span>  
  
1.  <span data-ttu-id="6fefc-145">선언 하 고 생성 된 <xref:System.Threading.SendOrPostCallback> 에서 대리자는 `PrimeNumberCalculator` 클래스.</span><span class="sxs-lookup"><span data-stu-id="6fefc-145">Declare and create the <xref:System.Threading.SendOrPostCallback> delegates in the `PrimeNumberCalculator` class.</span></span> <span data-ttu-id="6fefc-146">만들기는 <xref:System.Threading.SendOrPostCallback> 유틸리티 메서드에서 개체 라고 `InitializeDelegates`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-146">Create the <xref:System.Threading.SendOrPostCallback> objects in a utility method called `InitializeDelegates`.</span></span>  
  
     <span data-ttu-id="6fefc-147">두 명의 대리자 필요 합니다: 클라이언트에 진행률을 보고 및 클라이언트에 대 한 완료를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-147">You will need two delegates: one for reporting progress to the client, and one for reporting completion to the client.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  <span data-ttu-id="6fefc-148">호출 된 `InitializeDelegates` 구성 요소의 생성자에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="6fefc-148">Call the `InitializeDelegates` method in your component's constructor.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  <span data-ttu-id="6fefc-149">대리자를 선언에서 `PrimeNumberCalculator` 비동기적으로 수행 해야 하는 실제 작업을 처리 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-149">Declare a delegate in the `PrimeNumberCalculator` class that handles the actual work to be done asynchronously.</span></span> <span data-ttu-id="6fefc-150">이 대리자에는 숫자가 소수 인지 여부를 테스트 하는 작업자 메서드로를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-150">This delegate wraps the worker method that tests whether a number is prime.</span></span> <span data-ttu-id="6fefc-151">대리자를 사용는 <xref:System.ComponentModel.AsyncOperation> 매개 변수는 비동기 작업의 수명을 추적 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-151">The delegate takes an <xref:System.ComponentModel.AsyncOperation> parameter, which will be used to track the lifetime of the asynchronous operation.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  <span data-ttu-id="6fefc-152">보류 중인 비동기 작업의 수명을 관리 하기 위한 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-152">Create a collection for managing lifetimes of pending asynchronous operations.</span></span> <span data-ttu-id="6fefc-153">클라이언트가 실행 되 고 완료 되 면 클라이언트에서 비동기 메서드를 호출할 때 고유한 토큰 또는 작업 ID를 전달 하는 클라이언트를 요구 하 여 수행 됩니다이 추적으로 작업을 추적 하는 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-153">The client needs a way to track operations as they are executed and completed, and this tracking is done by requiring the client to pass a unique token, or task ID, when the client makes the call to the asynchronous method.</span></span> <span data-ttu-id="6fefc-154">`PrimeNumberCalculator` 구성 요소 해야 한 추적 호출할 때마다 해당 호출을 작업 ID를 연결 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-154">The `PrimeNumberCalculator` component must keep track of each call by associating the task ID with its corresponding invocation.</span></span> <span data-ttu-id="6fefc-155">클라이언트에서는 고유 하지 않으면 작업 ID를 전달 하는 경우는 `PrimeNumberCalculator` 구성 요소에서 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-155">If the client passes a task ID that is not unique, the `PrimeNumberCalculator` component must raise an exception.</span></span>  
  
     <span data-ttu-id="6fefc-156">`PrimeNumberCalculator` 구성 요소는 추적 작업 ID 라는 특수 한 컬렉션 클래스를 사용 하 여는 <xref:System.Collections.Specialized.HybridDictionary>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-156">The `PrimeNumberCalculator` component keeps track of task ID by using a special collection class called a <xref:System.Collections.Specialized.HybridDictionary>.</span></span> <span data-ttu-id="6fefc-157">만들 클래스 정의에 <xref:System.Collections.Specialized.HybridDictionary> 호출 `userTokenToLifetime`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-157">In the class definition, create a <xref:System.Collections.Specialized.HybridDictionary> called `userTokenToLifetime`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a><span data-ttu-id="6fefc-158">Public 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-158">Implementing Public Events</span></span>  
 <span data-ttu-id="6fefc-159">이벤트 기반 비동기 패턴을 구현 하는 구성 요소 이벤트를 사용 하는 클라이언트에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-159">Components that implement the Event-based Asynchronous Pattern communicate to clients using events.</span></span> <span data-ttu-id="6fefc-160">이러한 이벤트에 사용 하 여 적절 한 스레드에서 호출 되는 <xref:System.ComponentModel.AsyncOperation> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-160">These events are invoked on the proper thread with the help of the <xref:System.ComponentModel.AsyncOperation> class.</span></span>  
  
#### <a name="to-raise-events-to-your-components-clients"></a><span data-ttu-id="6fefc-161">이벤트를 발생 시키는 구성 요소의 클라이언트:</span><span class="sxs-lookup"><span data-stu-id="6fefc-161">To raise events to your component's clients:</span></span>  
  
1.  <span data-ttu-id="6fefc-162">클라이언트에 대 한 보고에 대 한 공용 이벤트를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-162">Implement public events for reporting to clients.</span></span> <span data-ttu-id="6fefc-163">진행률 및 완료를 보고에 대 한 보고에 대 한 이벤트에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-163">You will need an event for reporting progress and one for reporting completion.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a><span data-ttu-id="6fefc-164">완료 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-164">Implementing the Completion Method</span></span>  
 <span data-ttu-id="6fefc-165">완료 대리자는 성공적으로 완료, 오류 또는 취소 하 여 비동기 작업이 종료 될 때 원본으로 사용, 자유 스레드 비동기 동작에서 실행할 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-165">The completion delegate is the method that the underlying, free-threaded asynchronous behavior will invoke when the asynchronous operation ends by successful completion, error, or cancellation.</span></span> <span data-ttu-id="6fefc-166">이 호출 임의의 스레드에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-166">This invocation happens on an arbitrary thread.</span></span>  
  
 <span data-ttu-id="6fefc-167">이 메서드는 클라이언트의 작업 ID 고유한 클라이언트 토큰의 내부 컬렉션에서 제거 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-167">This method is where the client's task ID is removed from the internal collection of unique client tokens.</span></span> <span data-ttu-id="6fefc-168">이 메서드를 호출 하 여 특정 비동기 작업의 수명을 끝납니다는 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드 해당 <xref:System.ComponentModel.AsyncOperation>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-168">This method also ends the lifetime of a particular asynchronous operation by calling the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method on the corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="6fefc-169">이 호출 되는 응용 프로그램 모델에 대 한 적합 한 스레드에서 완료 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-169">This call raises the completion event on the thread that is appropriate for the application model.</span></span> <span data-ttu-id="6fefc-170">이후에 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드가 호출 되 면이 인스턴스의 <xref:System.ComponentModel.AsyncOperation> 더 이상 사용할 수 및 모든 후속 사용 하려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-170">After the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method is called, this instance of <xref:System.ComponentModel.AsyncOperation> can no longer be used, and any subsequent attempts to use it will throw an exception.</span></span>  
  
 <span data-ttu-id="6fefc-171">`CompletionMethod` 서명 비동기 작업의 결과 설명 하는 데 필요한 모든 상태를 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-171">The `CompletionMethod` signature must hold all state necessary to describe the outcome of the asynchronous operation.</span></span> <span data-ttu-id="6fefc-172">인지 수 및 해당 첫 번째 제 수 값 prime 숫자가 아닌 경우이 특정 비동기 작업에서 테스트 한 수에 대 한 상태를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-172">It holds state for the number that was tested by this particular asynchronous operation, whether the number is prime, and the value of its first divisor if it is not a prime number.</span></span> <span data-ttu-id="6fefc-173">발생 한 모든 예외를 설명 하는 상태 저장 및 <xref:System.ComponentModel.AsyncOperation> 이 특정 작업에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-173">It also holds state describing any exception that occurred, and the <xref:System.ComponentModel.AsyncOperation> corresponding to this particular task.</span></span>  
  
#### <a name="to-complete-an-asynchronous-operation"></a><span data-ttu-id="6fefc-174">에 비동기 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-174">To complete an asynchronous operation:</span></span>  
  
-   <span data-ttu-id="6fefc-175">완료 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-175">Implement the completion method.</span></span> <span data-ttu-id="6fefc-176">걸리는 채우는 데 사용 하 여 6 개의 매개 변수는 `CalculatePrimeCompletedEventArgs` 클라이언트의를 통해 클라이언트에 반환 되는 `CalculatePrimeCompletedEventHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-176">It takes six parameters, which it uses to populate a `CalculatePrimeCompletedEventArgs` that is returned to the client through the client's `CalculatePrimeCompletedEventHandler`.</span></span> <span data-ttu-id="6fefc-177">내부 컬렉션에서 클라이언트의 작업 ID 토큰을 제거 하 고 호출 하 여 비동기 작업의 수명을 종료 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-177">It removes the client's task ID token from the internal collection, and it ends the asynchronous operation's lifetime with a call to <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>.</span></span> <span data-ttu-id="6fefc-178"><xref:System.ComponentModel.AsyncOperation> 스레드나 응용 프로그램 모델에 적합 한 컨텍스트에서에 대 한 호출을 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-178">The <xref:System.ComponentModel.AsyncOperation> marshals the call to the thread or context that is appropriate for the application model.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a><span data-ttu-id="6fefc-179">검사점</span><span class="sxs-lookup"><span data-stu-id="6fefc-179">Checkpoint</span></span>  
 <span data-ttu-id="6fefc-180">이 시점에서 구성 요소를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-180">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="6fefc-181">구성 요소를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="6fefc-181">To test your component</span></span>  
  
-   <span data-ttu-id="6fefc-182">구성 요소를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fefc-182">Compile the component.</span></span>  
  
     <span data-ttu-id="6fefc-183">컴파일러 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-183">You will receive one compiler warning:</span></span>  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     <span data-ttu-id="6fefc-184">다음 섹션에서이 경고가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-184">This warning will be resolved in the next section.</span></span>  
  
## <a name="implementing-the-worker-methods"></a><span data-ttu-id="6fefc-185">작업자 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-185">Implementing the Worker Methods</span></span>  
 <span data-ttu-id="6fefc-186">지금까지 지 원하는 비동기 코드에 대 한 구현한는 `PrimeNumberCalculator` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-186">So far, you have implemented the supporting asynchronous code for the `PrimeNumberCalculator` component.</span></span> <span data-ttu-id="6fefc-187">이제 실제 작업을 수행 하는 코드를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-187">Now you can implement the code that does the actual work.</span></span> <span data-ttu-id="6fefc-188">세 가지 메서드를 구현 합니다. `CalculateWorker`, `BuildPrimeNumberList`, 및 `IsPrime`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-188">You will implement three methods: `CalculateWorker`, `BuildPrimeNumberList`, and `IsPrime`.</span></span> <span data-ttu-id="6fefc-189">함께 `BuildPrimeNumberList` 및 `IsPrime` 는 에라토스테네스의 체 테스트 숫자의 제곱근까지 모든 소수를 검색 하 여 숫자 소수 인지를 결정 하는 호출 하는 잘 알려진 알고리즘을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-189">Together, `BuildPrimeNumberList` and `IsPrime` comprise a well-known algorithm called the Sieve of Eratosthenes, which determines if a number is prime by finding all the prime numbers up to the square root of the test number.</span></span> <span data-ttu-id="6fefc-190">자신과 없는에서 발견 되 면 숫자는 소수입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-190">If no divisors are found by that point, the test number is prime.</span></span>  
  
 <span data-ttu-id="6fefc-191">이 구성 요소는 최대 효율성을 위해 작성 된 것을 다른 테스트 숫자에 대 한 다양 한 호출에서 검색 된 모든 주요 번호를 기억 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-191">If this component were written for maximum efficiency, it would remember all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="6fefc-192">2, 3 및 5와 같은 단순한 제 있는지도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-192">It would also check for trivial divisors like 2, 3, and 5.</span></span> <span data-ttu-id="6fefc-193">하지만이 예의 목적은 방법을 시간이 많이 걸리는 작업을 보여 주는 것 수 비동기적 실행 이러한 최적화를 연습으로 남아 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-193">The intent of this example is to demonstrate how time-consuming operations can be executed asynchronously, however, so these optimizations are left as an exercise for you.</span></span>  
  
 <span data-ttu-id="6fefc-194">`CalculateWorker` 메서드는 대리자에 겹쳐서 표시 및에 대 한 호출을 사용 하 여 비동기적으로 호출 `BeginInvoke`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-194">The `CalculateWorker` method is wrapped in a delegate and is invoked asynchronously with a call to `BeginInvoke`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fefc-195">구현 되는 진행률 보고는 `BuildPrimeNumberList` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6fefc-195">Progress reporting is implemented in the `BuildPrimeNumberList` method.</span></span> <span data-ttu-id="6fefc-196">빠른 컴퓨터 `ProgressChanged` 이벤트를 연속적으로 빠르게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-196">On fast computers, `ProgressChanged` events can be raised in rapid succession.</span></span> <span data-ttu-id="6fefc-197">에 이러한 이벤트가 발생 되 면 클라이언트 스레드가이 상황을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-197">The client thread, on which these events are raised, must be able to handle this situation.</span></span> <span data-ttu-id="6fefc-198">사용자 인터페이스 코드 수 있습니다 메시지와 함께 서비스 장애 유발 하 고, 지속할 수 없습니다 동작을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-198">User interface code may be flooded with messages and unable to keep up, resulting in hanging behavior.</span></span> <span data-ttu-id="6fefc-199">이 상황을 처리 하는 예제 사용자 인터페이스에 대 한 참조 [하는 방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-199">For an example user interface that handles this situation, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a><span data-ttu-id="6fefc-200">에 소수 계산을 비동기적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-200">To execute the prime number calculation asynchronously:</span></span>  
  
1.  <span data-ttu-id="6fefc-201">구현 된 `TaskCanceled` 유틸리티 메서드.</span><span class="sxs-lookup"><span data-stu-id="6fefc-201">Implement the `TaskCanceled` utility method.</span></span> <span data-ttu-id="6fefc-202">이 메서드는 특정된 작업 ID에 대 한 작업 수명 컬렉션 확인 하 고 반환 `true` 경우 작업 ID를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-202">This checks the task lifetime collection for the given task ID, and returns `true` if the task ID is not found.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  <span data-ttu-id="6fefc-203">`CalculateWorker` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-203">Implement the `CalculateWorker` method.</span></span> <span data-ttu-id="6fefc-204">두 개의 매개 변수를 사용: 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-204">It takes two parameters: a number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  <span data-ttu-id="6fefc-205">`BuildPrimeNumberList`를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-205">Implement `BuildPrimeNumberList`.</span></span> <span data-ttu-id="6fefc-206">두 개의 매개 변수를 사용: 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-206">It takes two parameters: the number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="6fefc-207">사용 하 여는 <xref:System.ComponentModel.AsyncOperation> 보고서 진행률 및 증분 결과를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-207">It uses the <xref:System.ComponentModel.AsyncOperation> to report progress and incremental results.</span></span> <span data-ttu-id="6fefc-208">이렇게 하면 적절 한 스레드나 응용 프로그램 모델에 대 한 컨텍스트는 클라이언트의 이벤트 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-208">This assures that the client's event handlers are called on the proper thread or context for the application model.</span></span> <span data-ttu-id="6fefc-209">때 `BuildPrimeNumberList` 소수에서 찾은 것이 증분 결과로 보고에 대 한 클라이언트의 이벤트 처리기는 `ProgressChanged` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-209">When `BuildPrimeNumberList` finds a prime number, it reports this as an incremental result to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="6fefc-210">파생 된 클래스가 필요 <xref:System.ComponentModel.ProgressChangedEventArgs>라는 `CalculatePrimeProgressChangedEventArgs`에 하나 추가할 라는 속성이 `LatestPrimeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-210">This requires a class derived from <xref:System.ComponentModel.ProgressChangedEventArgs>, called `CalculatePrimeProgressChangedEventArgs`, which has one added property called `LatestPrimeNumber`.</span></span>  
  
     <span data-ttu-id="6fefc-211">`BuildPrimeNumberList` 메서드 호출도 정기적으로 `TaskCanceled` 메서드와 메서드가 반환 하는 경우 종료 되거나 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-211">The `BuildPrimeNumberList` method also periodically calls the `TaskCanceled` method and exits if the method returns `true`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  <span data-ttu-id="6fefc-212">`IsPrime`를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-212">Implement `IsPrime`.</span></span> <span data-ttu-id="6fefc-213">세 개의 매개 변수를 걸리는: 알려진된 소수, 테스트할 숫자 및 찾은 첫 번째 제수의 대 한 출력 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-213">It takes three parameters: a list of known prime numbers, the number to test, and an output parameter for the first divisor found.</span></span> <span data-ttu-id="6fefc-214">테스트 수가 소수 인지 결정 소수의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-214">Given the list of prime numbers, it determines if the test number is prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  <span data-ttu-id="6fefc-215">파생 `CalculatePrimeProgressChangedEventArgs` 에서 <xref:System.ComponentModel.ProgressChangedEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-215">Derive `CalculatePrimeProgressChangedEventArgs` from <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span> <span data-ttu-id="6fefc-216">이 클래스는 증분 결과 대 한 클라이언트의 이벤트 처리기를 보고 하는 데 필요한는 `ProgressChanged` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-216">This class is necessary for reporting incremental results to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="6fefc-217">라는 추가 속성이 하나에 `LatestPrimeNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-217">It has one added property called `LatestPrimeNumber`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a><span data-ttu-id="6fefc-218">검사점</span><span class="sxs-lookup"><span data-stu-id="6fefc-218">Checkpoint</span></span>  
 <span data-ttu-id="6fefc-219">이 시점에서 구성 요소를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-219">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="6fefc-220">구성 요소를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="6fefc-220">To test your component</span></span>  
  
-   <span data-ttu-id="6fefc-221">구성 요소를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fefc-221">Compile the component.</span></span>  
  
     <span data-ttu-id="6fefc-222">모든 작업을 쓰면은 시작 하 고 비동기 작업을 취소 방법 `CalculatePrimeAsync` 및 `CancelAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-222">All that remains to be written are the methods to start and cancel asynchronous operations, `CalculatePrimeAsync` and `CancelAsync`.</span></span>  
  
## <a name="implementing-the-start-and-cancel-methods"></a><span data-ttu-id="6fefc-223">시작 및 취소 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-223">Implementing the Start and Cancel Methods</span></span>  
 <span data-ttu-id="6fefc-224">작업자 메서드를 호출 하 여 시작 자체 스레드에서 `BeginInvoke` 래핑하는 대리자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-224">You start the worker method on its own thread by calling `BeginInvoke` on the delegate that wraps it.</span></span> <span data-ttu-id="6fefc-225">호출 된 특정 비동기 작업의 수명을 관리 하기는 <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> 에서 메서드는 <xref:System.ComponentModel.AsyncOperationManager> 도우미 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-225">To manage the lifetime of a particular asynchronous operation, you call the <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> method on the <xref:System.ComponentModel.AsyncOperationManager> helper class.</span></span> <span data-ttu-id="6fefc-226">반환 합니다.는 <xref:System.ComponentModel.AsyncOperation>, 클라이언트의 이벤트 처리기 호출을 올바른 스레드 또는 컨텍스트로 마샬링하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-226">This returns an <xref:System.ComponentModel.AsyncOperation>, which marshals calls on the client's event handlers to the proper thread or context.</span></span>  
  
 <span data-ttu-id="6fefc-227">호출 하 여 특정 한 보류 중인 작업을 취소 하면 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 하면 해당에 <xref:System.ComponentModel.AsyncOperation>합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-227">You cancel a particular pending operation by calling <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> on its corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="6fefc-228">이렇게 호출 하 고, 해당 작업을 종료 해당 <xref:System.ComponentModel.AsyncOperation> 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-228">This ends that operation, and any subsequent calls to its <xref:System.ComponentModel.AsyncOperation> will throw an exception.</span></span>  
  
#### <a name="to-implement-start-and-cancel-functionality"></a><span data-ttu-id="6fefc-229">시작을 구현 하려면 및 취소 기능:</span><span class="sxs-lookup"><span data-stu-id="6fefc-229">To implement Start and Cancel functionality:</span></span>  
  
1.  <span data-ttu-id="6fefc-230">`CalculatePrimeAsync` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-230">Implement the `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="6fefc-231">클라이언트에서 제공한 토큰 (작업 ID)가 현재 보류 중인 작업을 나타내는 모든 토큰에 대해 고유한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-231">Make sure the client-supplied token (task ID) is unique with respect to all the tokens representing currently pending tasks.</span></span> <span data-ttu-id="6fefc-232">클라이언트 고유 하지 않은 토큰에 전달 하는 경우 `CalculatePrimeAsync` 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-232">If the client passes in a non-unique token, `CalculatePrimeAsync` raises an exception.</span></span> <span data-ttu-id="6fefc-233">그렇지 않으면 토큰 작업 ID 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-233">Otherwise, the token is added to the task ID collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  <span data-ttu-id="6fefc-234">`CancelAsync` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-234">Implement the `CancelAsync` method.</span></span> <span data-ttu-id="6fefc-235">경우는 `taskId` 매개 변수가 토큰 컬렉션에 있는지에 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-235">If the `taskId` parameter exists in the token collection, it is removed.</span></span> <span data-ttu-id="6fefc-236">이렇게 하면 실행에서이 시작 되지 않은 취소 된 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-236">This prevents canceled tasks that have not started from running.</span></span> <span data-ttu-id="6fefc-237">작업이 실행 되는 경우는 `BuildPrimeNumberList` 메서드가 작업 ID 수명 컬렉션에서 제거 된 것을 발견 하면 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-237">If the task is running, the `BuildPrimeNumberList` method exits when it detects that the task ID has been removed from the lifetime collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a><span data-ttu-id="6fefc-238">검사점</span><span class="sxs-lookup"><span data-stu-id="6fefc-238">Checkpoint</span></span>  
 <span data-ttu-id="6fefc-239">이 시점에서 구성 요소를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-239">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="6fefc-240">구성 요소를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="6fefc-240">To test your component</span></span>  
  
-   <span data-ttu-id="6fefc-241">구성 요소를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fefc-241">Compile the component.</span></span>  
  
 <span data-ttu-id="6fefc-242">`PrimeNumberCalculator` 구성 요소는 이제 완벽 하 고 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-242">The `PrimeNumberCalculator` component is now complete and ready to use.</span></span>  
  
 <span data-ttu-id="6fefc-243">사용 하는 예제 클라이언트는 `PrimeNumberCalculator` 구성 요소 참조 [하는 방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-243">For an example client that uses the `PrimeNumberCalculator` component, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6fefc-244">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6fefc-244">Next Steps</span></span>  
 <span data-ttu-id="6fefc-245">이 예제를 작성 하 여 채울 수 `CalculatePrime`, 해당 하는 동기 `CalculatePrimeAsync` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6fefc-245">You can fill out this example by writing `CalculatePrime`, the synchronous equivalent of `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="6fefc-246">이렇게 하면는 `PrimeNumberCalculator` 구성 요소는 이벤트 기반 비동기 패턴을 완벽 하 게 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-246">This will make the `PrimeNumberCalculator` component fully compliant with the Event-based Asynchronous Pattern.</span></span>  
  
 <span data-ttu-id="6fefc-247">이 예제에서는 서로 다른 테스트 숫자에 대 한 다양 한 호출에서 검색 된 모든 주요 번호 목록을 유지 하 여 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-247">You can improve this example by retaining the list of all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="6fefc-248">이 방법을 사용 하면 이전 태스크에서 수행 된 작업에서 각 태스크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-248">Using this approach, each task will benefit from the work done by previous tasks.</span></span> <span data-ttu-id="6fefc-249">이 목록으로 보호 하 `lock` 영역, 하므로 다른 스레드에서 목록에 대 한 액세스는 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-249">Be careful to protect this list with `lock` regions, so access to the list by different threads is serialized.</span></span>  
  
 <span data-ttu-id="6fefc-250">또한 2, 3 및 5와 같은 단순한 제, 테스트 하 여이 예제를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fefc-250">You can also improve this example by testing for trivial divisors, like 2, 3, and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fefc-251">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fefc-251">See Also</span></span>  
 [<span data-ttu-id="6fefc-252">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="6fefc-252">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="6fefc-253">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="6fefc-253">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="6fefc-254">빌드에 없음: Visual Basic의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="6fefc-254">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="6fefc-255">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="6fefc-255">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="6fefc-256">이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6fefc-256">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
