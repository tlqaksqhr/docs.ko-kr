---
title: invalidApartmentStateChange MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71634018e42ad66fdd2d03d0b0d496394cde801e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="192ac-102">invalidApartmentStateChange MDA</span><span class="sxs-lookup"><span data-stu-id="192ac-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="192ac-103">`invalidApartmentStateChange` MDA(관리 디버깅 도우미)는 다음 두 문제 중 하나가 발생하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
-   <span data-ttu-id="192ac-104">이미 COM에서 초기화된 스레드의 COM 아파트 상태를 다른 아파트 상태로 변경하려고 시도했습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
-   <span data-ttu-id="192ac-105">스레드의 COM 아파트 상태가 예기치 않게 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="192ac-106">증상</span><span class="sxs-lookup"><span data-stu-id="192ac-106">Symptoms</span></span>  
  
-   <span data-ttu-id="192ac-107">스레드의 COM 아파트 상태가 요청된 상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="192ac-108">이로 인해 현재 모델과 다른 스레딩 모델이 포함된 COM 구성 요소에 프록시가 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="192ac-109">이 사용으로 인해 아파트 간 마샬링에 사용하도록 설정되지 않은 인터페이스를 통해 COM 개체를 호출할 때 <xref:System.InvalidCastException>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
-   <span data-ttu-id="192ac-110">스레드의 COM 아파트 상태가 예상과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="192ac-111">이로 인해 RCW([런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md))에서 호출할 경우 <xref:System.InvalidCastException> 및 RPC_E_WRONG_THREAD의 HRESULT에서 <xref:System.Runtime.InteropServices.COMException>이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="192ac-112">또한 이로 인해 여러 스레드가 일부 단일 스레드 COM 구성 요소에 동시에 액세스할 수 있으므로 손상이나 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="192ac-113">원인</span><span class="sxs-lookup"><span data-stu-id="192ac-113">Cause</span></span>  
  
-   <span data-ttu-id="192ac-114">스레드가 이전에 다른 COM 아파트 상태로 초기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="192ac-115">스레드의 아파트 상태는 명시적으로 또는 암시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="192ac-116">명시적 작업에는 <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> 속성과 <xref:System.Threading.Thread.SetApartmentState%2A> 및 <xref:System.Threading.Thread.TrySetApartmentState%2A> 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="192ac-117">스레드가 시작되기 전에 <xref:System.Threading.Thread.SetApartmentState%2A>가 호출되지 않을 경우 <xref:System.Threading.Thread.Start%2A> 메서드를 사용하여 만든 스레드는 암시적으로 <xref:System.Threading.ApartmentState.MTA>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="192ac-118">주 메서드에서 <xref:System.STAThreadAttribute> 특성이 지정되지 않은 경우 응용 프로그램의 주 스레드는 <xref:System.Threading.ApartmentState.MTA>로 암시적으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
-   <span data-ttu-id="192ac-119">다른 동시성 모델이 포함된 `CoUninitialize` 메서드(또는 `CoInitializeEx` 메서드)는 스레드에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="192ac-120">해결</span><span class="sxs-lookup"><span data-stu-id="192ac-120">Resolution</span></span>  
 <span data-ttu-id="192ac-121">실행이 시작되기 전에 스레드의 아파트 상태를 설정하거나 <xref:System.STAThreadAttribute> 특성이나 <xref:System.MTAThreadAttribute> 특성을 응용 프로그램의 주 메서드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="192ac-122">두 번째 원인의 경우 `CoUninitialize` 메서드를 호출하는 코드를 수정하여 스레드가 종료되려고 하고 스레드에서 사용 중인 RCW 및 기본 COM 구성 요소가 없을 때까지 호출을 연기하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="192ac-123">그러나 `CoUninitialize` 메서드를 호출하는 코드를 수정할 수 없는 경우에는 이 방법으로 초기화되지 않은 스레드에서 RCW를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="192ac-124">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="192ac-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="192ac-125">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="192ac-126">출력</span><span class="sxs-lookup"><span data-stu-id="192ac-126">Output</span></span>  
 <span data-ttu-id="192ac-127">현재 스레드의 COM 아파트 상태 및 코드에서 적용하려고 시도한 상태.</span><span class="sxs-lookup"><span data-stu-id="192ac-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="192ac-128">구성</span><span class="sxs-lookup"><span data-stu-id="192ac-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="192ac-129">예제</span><span class="sxs-lookup"><span data-stu-id="192ac-129">Example</span></span>  
 <span data-ttu-id="192ac-130">다음 코드 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="192ac-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="192ac-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="192ac-131">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="192ac-132">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="192ac-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="192ac-133">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="192ac-133">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
