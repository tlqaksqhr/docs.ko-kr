---
title: 타이머
description: 다중 스레드 환경에서 사용할 .NET 타이머에 대해 알아봅니다.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: ae41c535d8bc1c0a05174b9051ba34f1a0a34638
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875068"
---
# <a name="timers"></a><span data-ttu-id="d3b4a-103">타이머</span><span class="sxs-lookup"><span data-stu-id="d3b4a-103">Timers</span></span>

<span data-ttu-id="d3b4a-104">.NET은 다중 스레드 환경에서 사용할 다음 두 개의 타이머를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="d3b4a-105"><xref:System.Threading.Timer?displayProperty=nameWithType> - <xref:System.Threading.ThreadPool> 스레드에서 단일 콜백 메서드를 정기적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="d3b4a-106"><xref:System.Timers.Timer?displayProperty=nameWithType> - 기본적으로 <xref:System.Threading.ThreadPool> 스레드에서 이벤트를 정기적으로 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b4a-107">일부 .NET 구현에는 다음과 같은 추가 타이머가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="d3b4a-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: 이벤트를 정기적으로 발생시키는 Windows Forms 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="d3b4a-109">이 구성 요소에는 사용자 인터페이스가 없으며, 단일 스레드 환경에서 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="d3b4a-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: 비동기 또는 동기 웹 페이지 포스트백을 정기적으로 수행하는 ASP.NET 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="d3b4a-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: 지정된 시간 간격 및 지정된 우선 순위로 처리되는 <xref:System.Windows.Threading.Dispatcher> 큐에 통합된 타이머입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="d3b4a-112">System.Threading.Timer 클래스</span><span class="sxs-lookup"><span data-stu-id="d3b4a-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="d3b4a-113"><xref:System.Threading.Timer?displayProperty=nameWithType> 클래스를 사용하면 대리자를 지정된 시간 간격으로 계속 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="d3b4a-114">또한 이 클래스를 사용하여 지정된 시간 간격으로 대리자에 대한 단일 호출을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-114">You also can use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="d3b4a-115">대리자는 <xref:System.Threading.ThreadPool> 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="d3b4a-116"><xref:System.Threading.Timer?displayProperty=nameWithType> 개체를 만들 때 콜백 메서드를 정의하는 <xref:System.Threading.TimerCallback> 대리자, 콜백에 전달되는 선택적 상태 개체, 콜백의 첫 번째 호출까지 지연되는 시간 및 콜백 호출 간의 시간 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="d3b4a-117">보류 중인 타이머를 취소하려면 <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d3b4a-118">다음 예제에서는 제공된 대리자를 1초(1,000밀리초) 후에 처음 호출한 다음, 2초마다 호출하는 타이머를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="d3b4a-119">이 예제의 상태 개체는 대리자를 호출한 횟수를 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="d3b4a-120">대리자가 10회 이상 호출되면 타이머가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="d3b4a-121">자세한 내용과 예제를 보려면 <xref:System.Threading.Timer?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="d3b4a-122">System.Timers.Timer 클래스</span><span class="sxs-lookup"><span data-stu-id="d3b4a-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="d3b4a-123">다중 스레드 환경에서 사용할 수 있는 또 다른 타이머는 <xref:System.Timers.Timer?displayProperty=nameWithType>이며, 기본적으로 <xref:System.Threading.ThreadPool> 스레드에서 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="d3b4a-124"><xref:System.Timers.Timer?displayProperty=nameWithType> 개체를 만들 때 <xref:System.Timers.Timer.Elapsed> 이벤트가 발생되는 시간 간격을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="d3b4a-125"><xref:System.Timers.Timer.Enabled%2A> 속성을 사용하여 타이머에서 <xref:System.Timers.Timer.Elapsed> 이벤트가 발생되어야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="d3b4a-126">지정된 간격이 지난 후에 <xref:System.Timers.Timer.Elapsed> 이벤트가 한 번만 발생해야 하는 경우 <xref:System.Timers.Timer.AutoReset%2A>을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="d3b4a-127"><xref:System.Timers.Timer.AutoReset%2A> 속성의 기본값은 `true`이며, 이는 즉 <xref:System.Timers.Timer.Elapsed> 이벤트가 <xref:System.Timers.Timer.Interval%2A> 속성에 정의된 간격으로 정기적으로 발생하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="d3b4a-128">자세한 내용과 예제를 보려면 <xref:System.Timers.Timer?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3b4a-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3b4a-129">See also</span></span>

 <xref:System.Threading.Timer?displayProperty=nameWithType>  
 <xref:System.Timers.Timer?displayProperty=nameWithType>  
 [<span data-ttu-id="d3b4a-130">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="d3b4a-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
